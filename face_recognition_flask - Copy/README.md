# Face Recognition Attendance System

A Flask-based web application for automated attendance using face recognition. The system uses OpenCV for face detection, scikit-learn for face recognition, and stores attendance records in CSV files. Users can register their faces and mark attendance via webcam.

## Features
- Register new users with face images via webcam
- Real-time face recognition and attendance marking
- Attendance records saved as daily CSV files
- User-friendly web interface (Bootstrap styled)
- Stores user face data for future recognition

## Folder Structure
```
face_recognition_flask/
├── app.py                  # Main Flask application
├── requirements.txt        # Python dependencies
├── Attendance/             # Daily attendance CSV files
├── static/
│   ├── faces/              # User face images (per user folder)
│   └── face_recognition_model.pkl  # Trained KNN model
├── templates/
│   └── home.html           # Main web UI
├── haarcascade_frontalface_default.xml # Face detection model
├── background.png          # Background image for UI
```

## Setup Instructions
1. **Clone the repository**
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Download required files**:
   - Place `haarcascade_frontalface_default.xml` in the project root (download from [OpenCV GitHub](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml))
   - Place a `background.png` image in the project root (any 640x480+ image)
4. **Run the application**:
   ```bash
   python app.py
   ```
5. **Open your browser** and go to `http://127.0.0.1:5000/`

## Usage
- **Add New User**: Enter a name and ID, then capture face images via webcam.
- **Take Attendance**: Click "Take Attendance" to start face recognition and mark attendance for recognized users.
- **View Attendance**: Today's attendance is displayed on the home page. CSV files are saved in the `Attendance/` folder.

## Notes
- Requires a webcam for capturing and recognizing faces.
- The first time you add a user, the model is trained automatically.
- Attendance is marked only once per user per day.

## Dependencies
- Flask
- OpenCV (opencv-python)
- scikit-learn
- pandas
- joblib
- numpy

## License
MIT License 