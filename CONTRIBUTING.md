# Contributing to Face Detection Attendance System

First off, thank you for considering contributing to this project! It's people like you that make the open-source community such a great place to learn, inspire, and create.

This project is perfect for beginners, especially during **Hacktoberfest**. The following is a set of guidelines for contributing.

## 🎯 How Can I Contribute?

### Reporting Bugs
- Ensure the bug was not already reported by searching on GitHub under [Issues](https://github.com/yesiamrajeev/FaceDetection_Prototype3/issues).
- If you're unable to find an open issue addressing the problem, [open a new one](https://github.com/yesiamrajeev/FaceDetection_Prototype3/issues/new).

### Suggesting Enhancements
- Open a new issue with a clear title and a detailed description of the enhancement.

### Code Contributions
1.  **Fork the Repository**
    Click the "Fork" button at the top-right of the [repository page](https://github.com/yesiamrajeev/FaceDetection_Prototype3).

2.  **Clone Your Fork**
    ```bash
    git clone https://github.com/<your-username>/FaceDetection_Prototype3.git
    cd FaceDetection_Prototype3
    ```

3.  **Create a Branch**
    Create a descriptive branch for your changes.
    ```bash
    git checkout -b feature/your-amazing-feature
    # or: git checkout -b fix/your-bug-fix
    ```

4.  **Make Your Changes**
    Here are some ideas:
    - **Add features or fix bugs** in `app.py`.
    - **Enhance the UI** by modifying files in the `templates/` folder.
    - **Improve styling** by working on files in the `static/` folder.
    - **Add your own face detection logic** in the `Attendance/` folder.
    - **Improve documentation** (like this file!) or fix typos.

5.  **Stage and Commit**
    ```bash
    git add .
    git commit -m "Describe your changes clearly here"
    ```

6.  **Push to Your Fork**
    ```bash
    git push origin feature/your-amazing-feature
    ```

7.  **Open a Pull Request (PR)**
    - Go to the original repository on GitHub.
    - You should see a prompt to open a PR from your new branch.
    - Fill in the PR template with all the required information.

## ✅ Mandatory for PR Approval

To ensure your contribution is verified and can be merged, you **must** provide the following:

1.  **Screenshot(s):** At least one screenshot showing:
    - Your code changes running successfully.
    - The Flask app’s UI or output (e.g., detected faces, attendance mark screen).

2.  **Screen Recording:** A short video (10–30 seconds) demonstrating your changes working live in the application.

    You can provide the video by:
    - Uploading the `.mp4` file inside the `/static/demo/` folder and linking it in your PR description.
    - **OR** providing a public link (e.g., Google Drive, Loom, YouTube) in your PR description.

### Example PR Description

```markdown
## What does this PR do?
- Added enhanced error handling in `app.py`
- Improved the button styling in `home.html`

## Screenshot
![Description of screenshot](link-to-screenshot)

## Video Demo
[Link to video demonstration]