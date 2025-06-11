# 🧠 FacialRecNo – Face Recognition Attendance System

**FacialRecNo** is a Python-based facial recognition system for identifying known individuals and optionally recording unknown faces. It's useful in controlled environments like classrooms, offices, or drone-based surveillance.

This project combines OpenCV, face encoding, and attendance logging with support for known and unknown face separation.

---

## 🚀 Features

- 👤 Recognizes faces from the `ImagesRecord/` directory
- ❓ Detects and logs unknown individuals in `unknown.csv`
- 📷 Real-time webcam support using OpenCV
- 📁 Modular code structure with `services/` logic
- ✍️ Records new faces into dataset if unrecognized

---

## 🗂️ Project Structure

```
facialrecno/
├── face-recognition/
│   ├── ImagesRecord/               # Known face images
│   │   └── *.jpg / *.jpeg
│   ├── services/
│   │   ├── Face_recognition.py     # Main logic for matching known faces
│   │   ├── extract.py              # Helper functions (image preprocessing, etc.)
│   │   ├── main.py                 # Entry point (calls other services)
│   │   ├── opencv.py               # Camera access and video capture
│   │   ├── record_unknown.py       # CSV logging of unknown faces
│   │   ├── unknown_Face.py         # Logic for handling unknown faces
│   │   └── unknown.csv             # CSV to track unknown faces
├── Mask detection/
│   └── Github face mask detection.txt   # Notes (possibly deprecated)
└── .gitattributes, .DS_Store, ...
```

---

## 🛠️ Tech Stack

- Python 3.9+
- OpenCV
- face_recognition (dlib-based)
- NumPy
- Pandas (for CSV logging)

---

## ▶️ Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/shubhamhalvadia/facialrecno.git
cd facialrecno/face-recognition
```

### 2. Install Dependencies

```bash
pip install opencv-python face_recognition numpy pandas
```

> ✅ Optional: Use a virtual environment for isolation

### 3. Prepare Image Dataset

Add face images to `ImagesRecord/` folder. Each file name (without extension) will be used as the identifier.

```bash
ImagesRecord/
├── Satvik.jpg
├── mayur.jpeg
└── jagdish.jpg
```

### 4. Run the Main App

```bash
python services/main.py
```

- It will start your webcam.
- Detect and label known faces.
- Log any unknowns to `unknown.csv`.

---

## 📋 Example Output

### ✅ Console Logs

```
[INFO] Recognized: mayur
[INFO] Unknown face detected – logging to CSV
```

### 📝 unknown.csv

| Name     | Time     | Date       |
|----------|----------|------------|
| Unknown  | 15:12:45 | 2025-06-10 |

---

## 🧩 Modular Design

- `Face_recognition.py`: Face encoding and matching
- `extract.py`: Image loading and preprocessing
- `record_unknown.py`: Writes unknowns to CSV
- `opencv.py`: Handles camera capture
- `main.py`: Orchestrates it all

---

## 🧪 To-Do / Improvements

- [ ] Add GUI for image registration
- [ ] Enable cloud-based storage of attendance
- [ ] Face mask detection (under `/Mask detection/`)
- [ ] Integrate with access control systems

---

## 🤝 Contribution

Got ideas for improvements? PRs and issues are welcome!

---

## 📜 License

Not specified — feel free to use for educational/non-commercial purposes or open an issue to request licensing.
