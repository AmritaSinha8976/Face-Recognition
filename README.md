# Face Recognition Attendance System

A real-time face recognition-based attendance system built using Python, OpenCV, and Flask. This project captures faces using a webcam, identifies them using a pre-trained machine learning model, and automatically logs attendance into CSV files with timestamps.

---

## 🧠 Overview

This system is designed for educational institutions, offices, and organizations where automated attendance tracking is desired. It leverages `face_recognition` for accurate face identification and OpenCV for real-time webcam access and processing.

---

## ✨ Features

- 🔍 **Real-time face detection** using Haar Cascade Classifier
- 🧠 **Face recognition** with `face_recognition` and a trained model
- 📁 **Attendance logging** into date-stamped CSV files
- 🧑‍💼 **Support for multiple users**
- 🖼️ GUI with OpenCV windows or optionally Flask-based interface
- 💾 Persistent storage of face images and trained model
- 🕒 Timestamped attendance records
- 🧪 Easily extendable for new users

---

## 📁 Project Structure

Face recognition/
│
├── app.py                               # Main Python script to start the app
├── haarcascade\_frontalface\_default.xml # XML file for face detection
├── background.png                       # Background image for UI (optional)
│
├── Attendance/                          # Contains CSV logs of attendance
│   ├── Attendance-04\_06\_24.csv
│   └── ...
│
├── static/
│   ├── face\_recognition\_model.pkl       # Trained face recognition model
│   └── faces/                           # Folder containing subfolders of user face images
│       ├── amri\_8/
│       │   ├── amri\_0.jpg
│       │   ├── ...
│
└── README.md                            # This file


---

## 🛠️ Requirements

Install the dependencies using `pip`:

pip install opencv-python face_recognition numpy pandas flask


### Additional Notes:

* `face_recognition` depends on `dlib`. On some systems, you may need to install CMake and Visual Studio Build Tools (Windows) or `build-essential` (Linux).

---

## 🚀 Getting Started

### 1. Clone the repository

git clone https://github.com/your-username/face-recognition-attendance.git
cd face-recognition-attendance/Face\ recognition


### 2. Add Face Data

Organize face images in this format:

static/faces/
├── john_doe/
│   ├── john_1.jpg
│   ├── john_2.jpg
│   └── ...
└── jane_smith/
    ├── jane_1.jpg
    ├── ...


At least 5–10 images per person are recommended for better accuracy.

### 3. Run the App

python app.py

If it’s a Flask app, it will start a web server; if it’s an OpenCV GUI, a webcam window will open.

---

## 🔍 How It Works

1. The system uses OpenCV to capture frames from the webcam.
2. Faces are detected using a Haar cascade classifier.
3. Detected faces are compared with known faces using `face_recognition` encodings.
4. If a face matches a known user, the name and timestamp are recorded in a CSV file under `Attendance/`.
5. If the same user is detected multiple times, it avoids duplicate entries for the same session.

---

## 🧪 Training the Model

If you add new users or update existing face images:

1. Make sure images are saved in `static/faces/<username>/`.
2. Retrain the model (if there's a separate training script or logic in `app.py` that allows this).

---

## 🧾 Sample Attendance CSV

Each attendance file is named like `Attendance-DD_MM_YY.csv` and looks like:

| Name      | Time     | Date       |
| --------- | -------- | ---------- |
| Amri\_8   | 10:21:53 | 04-06-2024 |
| John\_Doe | 10:22:11 | 04-06-2024 |

---

## 🛡️ Security Considerations

* This is a demo/educational system; do not deploy it for secure environments without additional hardening.
* Consider adding authorization if exposed over a network.

---

## ✅ To Do

* [ ] Add email notifications for late/absent users
* [ ] Add admin dashboard
* [ ] Export attendance in PDF or Excel
* [ ] Add support for face re-training from the UI
* [ ] Add face registration via webcam

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for more information.

---

## 🙌 Acknowledgements

* [OpenCV](https://opencv.org/)
* [face\_recognition](https://github.com/ageitgey/face_recognition)
* [dlib](http://dlib.net/)

