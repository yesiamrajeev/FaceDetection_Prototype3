
# 🤖 Real-Time Face Detection Attendance System (Flask + OpenCV) ✨

[![Hacktoberfest 2025](https://img.shields.io/badge/Hacktoberfest-2025-blueviolet)](https://hacktoberfest.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Technology](https://img.shields.io/badge/Stack-Python%20%7C%20Flask%20%7C%20OpenCV-informational)](https://www.python.org/)

---

<p align="center">
<img width="1878" height="894" alt="image" src="https://github.com/user-attachments/assets/f6359636-b606-4820-ba36-626e1a3cd590" />
</p>

## 🚀 Welcome to Your First AI/ML Open Source Contribution!

This repository is an excellent starting point for anyone looking to merge **Machine Learning** with **Web Development**. We've built a real-time **Face Detection Attendance System** using **Python**, the **Flask** web framework, and the **OpenCV** library.

Join us to learn how to build a practical AI application from the ground up, all while participating in Hacktoberfest 2025! 🤝


 <a href="https://github.com/yesiamrajeev" ><img src="https://img.shields.io/badge/Contributions-welcome-violet.svg?style=flat&logo=git" alt="Contributions" /></a>
<a href="https://github.com/yesiamrajeev/Hacktoberfest2024/pulls"><img src="https://img.shields.io/github/issues-pr/yesiamrajeev/FaceDetection_Prototype3" alt="Pull Requests Badge"/></a>
<a href="https://github.com/yesiamrajeev/Hacktoberfest2024/graphs/contributors"><img alt="GitHub contributors" src="https://img.shields.io/github/contributors/yesiamrajeev/FaceDetection_Prototype3?color=2b9348"></a>


---

## 🌲 Hacktoberfest 2025 is LIVE! (Beginner Friendly)

Make your **first open-source contribution** here! We have issues tagged specifically for beginners (Look for the `good first issue` label).

> Aim to submit 6 high-quality pull/merge requests between **October 1 and October 31**, with project maintainers accepting your pull/merge requests for them to count toward your total and get an official Hacktoberfest T-shirt(early grabs for first 10k People) AND get a tree planted in your name! 🌳


### Why Contribute to This Project?

| Skill You'll Learn | Feature You'll Touch | Relevant File |
| :--- | :--- | :--- |
| **Full-Stack ML Deployment** | Set up and run a Flask web application | `app.py` |
| **Computer Vision** | Integrate OpenCV for real-time face detection | `app.py` |
| **Data Handling** | Read and write attendance data to CSV files | `app.py` |
| **Frontend/UI** | Customize the attendance dashboard interface | `templates/home.html` |

---

## 🎯 Project Features & Core Technologies

This system uses a combination of classic CV techniques and simple machine learning for efficient, real-time attendance marking.

### Key Features:
* **Real-Time Face Recognition:** Uses the host machine's webcam to instantly detect and recognize users.
* **Simple User Registration:** Captures a set of face images (50 frames) for a new user to train the recognition model.
* **Daily Attendance Records:** Automatically logs attendance with Name, Roll ID, and Time into a timestamped CSV file (e.g., `Attendance/Attendance-10_08_25.csv`).
* **Web Dashboard:** Displays today's attendance sheet on the web interface.

### Tech Stack:
| Component | Technology | Role |
| :--- | :--- | :--- |
| Web Framework | **Flask** | Routing and serving the web dashboard. |
| Computer Vision | **OpenCV** | Video streaming, face extraction (`extract_faces`), and Haar Cascade face detection. |
| Face Recognition | **K-Nearest Neighbors (KNN)** | Classifies the detected face using a trained model (`face_recognition_model.pkl`). |
| Data Processing | **Pandas** | Managing attendance data in CSV files. |

---

## 🛠️ Run This Project Locally (Quick Setup)

Follow these steps to get your local development environment ready:

### 1. Install Dependencies
Ensure you have Python installed (Python 3.x recommended)
```bash
pip install -r requirements.txt
```

2. Run the Flask Application
```Bash

python app.py
```
3. Open your browser and navigate to:
```
http://127.0.0.1:5000
```

> **Note:** Make sure you have the required **`haarcascade_frontalface_default.xml`** file and a pre-trained model **`static/face_recognition_model.pkl`** (or run user registration to generate one) for the system to function.

-----

## 💡 How to Contribute (A Beginner's Guide)

We welcome all contributions\! Here are the simple steps to make your first Pull Request:

### Contribution Steps

1.  **Fork** this repository.
2.  **Clone** your fork:
    ```bash
    git clone [https://github.com/](https://github.com/)<your-username>/yesiamrajeev.git
    cd yesiamrajeev
    ```
3.  **Create a New Branch**:
    ```bash
    git checkout -b fix/your-issue-name
    ```
4.  **Make Your Changes** (See contribution ideas below).
5.  **Commit** your changes and **Push** to your fork.
6.  Open a **Pull Request** to the `main` branch of the original repository.

### Beginner Contribution Ideas:

  * **Frontend Magic (HTML/CSS):** Improve the layout, styling, and responsiveness of the dashboard in `templates/home.html`.
  * **Documentation:** Enhance this `README.md` or add comments/docstrings to complex functions in `app.py` (e.g., `train_model`, `identify_face`).
  * **Feature Enhancement (Python):** Add a feature to delete registered users/folders (e.g., improve the `deletefolder` function).
  * **Error Handling:** Add more robust `try...except` blocks, especially around OpenCV camera calls or file operations.
  * **Refactoring:** Optimize the data retrieval/attendance functions like `extract_attendance`.

-----

## ✅ Mandatory for PR Approval

To ensure your contribution is verified and can be merged, you **must** provide the following:

1.  **Screenshot(s):** At least one screenshot showing:
    - Your code changes running successfully.
    - The Flask app’s UI or output (e.g., detected faces, attendance mark screen).

2.  **Screen Recording:** A short video (10–30 seconds) demonstrating your changes working live in the application.

    You can provide the video by:
    - Uploading the `.mp4` file inside the `/static/demo/` folder and linking it in your PR description.
    - **OR** providing a public link (e.g., Google Drive, Loom, YouTube) in your PR description.


-----

## 📂 Project Structure

```
yesiamrajeev/
├── app.py                         # Main Flask application and all logic (routes, ML functions)
├── Attendance/                    # Daily Attendance CSV files are stored here
├── static/                        # Images, CSS, JS, trained model (.pkl), and demo videos
│   ├── faces/                     # Folders for registered user images
│   └── face_recognition_model.pkl # Trained KNN model for recognition
├── templates/                     # HTML templates (e.g., home.html)
├── haarcascade_frontalface_default.xml # OpenCV pre-trained face detection model
├── requirements.txt               # Required Python dependencies
└── README.md                      # You are here!
```

-----

## 🌟 Contributors

Thanks to these **wonderful people** 👨🏻‍💻 who made this project better with their contributions\!

[![Contributors](https://contrib.rocks/image?repo=yesiamrajeev/FaceDetection_Prototype3&cacheBuster=321656)](https://github.com/yesiamrajeev/FaceDetection_Prototype3/graphs/contributors)


✨ *Want to see your name here?*
Start contributing now — your PR will add you to the list automatically after merge\!

-----

## 📣 Connect With Me

👤 **Maintainer:** [@yesiamrajeev](https://github.com/yesiamrajeev)
📧 **Email:** rajeev.220077@gmail.com
🌍 **Location:** Bhubaneswar, India

Follow and ⭐ the repo to stay updated with new contribution ideas\!

-----

## 🪴 Let's Code. Collaborate. Contribute.

> “Every pull request plants a seed — let’s grow together.” 🌱

-----