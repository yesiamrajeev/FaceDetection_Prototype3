# Project Status & Roadmap

This document details the current status of the project, outlines necessary modifications and new features, and presents a target codebase structure.

---

### 1. Work Already Done

-   **Web Interface:** A functional UI exists using Flask and a Bootstrap HTML template.
-   **Face Capture:** The system can access a webcam and capture images for new users.
-   **Model Training:** A KNN model is trained on existing user faces.
-   **Face Recognition:** The system can identify registered users in a live video stream.
-   **Attendance Logging:** Basic attendance is recorded in daily CSV files.

---

### 2. Modifications Required

-   [ ] **Fix Critical Security Vulnerability (Path Traversal)**
    *   **Problem:** User-provided input (`newusername`) is used directly to create a directory path, allowing an attacker to write files to unintended locations.
    *   **Solution:** Sanitize the username before using it in any filesystem operations.

-   [ ] **Prevent Duplicate Attendance Entries**
    *   **Problem:** A user's attendance is marked every time their face is detected, leading to multiple entries for the same person in a single session.
    *   **Solution:** Before writing to the attendance log, check if the user has already been marked present for the day.

-   [ ] **Refactor Inefficient Model Training**
    *   **Problem:** The entire model is retrained every time a single user is added, which is slow and will not scale.
    *   **Solution:** While a full refactor can be part of a later phase, an initial improvement would be to only retrain when necessary.

-   [ ] **Improve General Error Handling**
    *   **Problem:** The application crashes if a webcam is not found or if critical files like `haarcascade_frontalface_default.xml` are missing.
    *   **Solution:** Add `try-except` blocks and conditional checks to handle these scenarios gracefully and provide feedback to the user.

---

### 3. New Implementations

-   [ ] **Implement Automatic User ID Generation**
    *   **Problem Solved:** Removes the need for manual ID entry, preventing errors and duplicate IDs. Simplifies the registration process.
    *   **Implementation:** The backend will automatically generate a new 4-digit, zero-padded ID by finding the last highest ID in the database.

-   [ ] **Migrate Data Storage to SQLite**
    *   **Problem Solved:** Replaces fragile and insecure CSV files and filename parsing with a robust database. This fixes the CSV injection vulnerability, improves data integrity, and makes the application more scalable and efficient.
    *   **Implementation:** Create a simple SQLite database with `users` and `attendance` tables. All functions that currently read/write to CSVs or parse filenames will be updated to use the database.

---

### 4. Proposed Codebase Structure (Post-Implementation)

```
.FaceDetection_Prototype3/
├── app.py                 # Main Flask application logic
├── database.py            # (New) All SQLite database functions (CRUD operations)
├── attendance.db          # (New) The SQLite database file
├─ⷨ docs/
│   ├── HLD.md
│   └── PROJECT_STATUS.md
├─ⷨ static/
│   └─ⷨ faces/
│       └── USERNAME_0001/
├─ⷨ templates/
│   └── home.html
├── haarcascade_frontalface_default.xml
├── requirements.txt
└── ...
```

---

### 5. Problems Solved by These Implementations

*   **Security:** Eliminates critical vulnerabilities like Path Traversal and CSV Injection.
*   **Reliability:** Prevents data corruption from duplicate attendance entries and improves overall stability with better error handling.
*   **Scalability:** Migrating to a database and optimizing training logic ensures the application can handle a growing number of users without significant performance degradation.
*   **Maintainability:** Centralizing data logic into a database and a dedicated Python module makes the code cleaner, more organized, and easier to manage.
*   **User Experience:** Automating ID generation simplifies the registration process for the end-user.
