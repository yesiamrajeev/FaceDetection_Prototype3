# High-Level Design (HLD) - Face Detection Attendance System

## 1. Introduction

This document outlines the high-level architecture for the Face Detection Attendance System. The system is designed as a web-based application that allows for user registration via face capture and marks attendance in real-time using facial recognition.

## 2. System Architecture

The application is composed of five primary components:

![System Architecture Diagram](https://i.imgur.com/3aG3d2J.png)

*   **Frontend (UI):**
    *   **Technology:** Flask-rendered HTML templates with Bootstrap CSS.
    *   **Responsibility:** Provides the user interface for registering new users and initiating the attendance process. It communicates with the backend via standard HTTP requests.

*   **Backend (API Server):**
    *   **Technology:** Python with Flask.
    *   **Responsibility:** Exposes API endpoints to handle requests from the frontend. It orchestrates all business logic, from handling user data to managing the face recognition process.

*   **Business Logic:**
    *   **User Management:** Handles the logic for creating, storing, and retrieving user information.
    *   **Attendance Tracking:** Manages the process of marking and recording attendance.
    *   **Model Training:** Retrains the face recognition model whenever a new user is added to ensure the system can identify them.

*   **ML/CV Module:**
    *   **Technology:** OpenCV and Scikit-learn.
    *   **Responsibility:**
        *   **Face Detection:** Uses a pre-trained Haar Cascade model (`haarcascade_frontalface_default.xml`) to locate faces in a video stream.
        *   **Face Recognition:** Uses a K-Nearest Neighbors (KNN) classifier trained on the images of registered users to identify faces.

*   **Data Storage:**
    *   **Technology:** Filesystem for face images and a proposed **SQLite database** for metadata.
    *   **Responsibility:**
        *   **Face Data:** Stores captured face images, organized in folders.
        *   **Metadata:** Stores user information (Name, ID) and attendance logs. Migrating this to a database is a key part of the proposed improvements.

## 3. Data Flow

### 3.1. New User Registration

1.  **UI:** A user submits their name on the registration form.
2.  **Backend:** The backend receives the request and triggers the **User Management** logic.
3.  **Business Logic:** An automatic, unique User ID is generated.
4.  **ML/CV Module:** The application accesses the webcam, captures a series of face images, and processes them.
5.  **Data Storage:** The images are saved to the filesystem, and the user's name and ID are stored in the database.
6.  **Model Training:** The `train_model()` function is called to retrain the KNN model with the new user's face data.

### 3.2. Take Attendance

1.  **UI:** A user clicks the "Take Attendance" button.
2.  **Backend:** The backend receives the request and starts the attendance process.
3.  **ML/CV Module:** The application accesses the webcam. For each frame, it detects faces and uses the trained KNN model to identify them.
4.  **Business Logic:** If a recognized face belongs to a registered user who has not yet been marked present today, the **Attendance Tracking** logic is invoked.
5.  **Data Storage:** The user's attendance (Name, ID, Timestamp) is recorded in the database.
6.  **UI:** The frontend dynamically updates to show the list of present users for the day.
