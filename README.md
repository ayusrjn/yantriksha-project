# Gesture Detection and Live Camera Streaming System

This project uses a **Raspberry Pi** to detect a specific **gesture** via the camera. When the gesture is recognized, it triggers a **Django server** to start and **stream live footage**. The system also utilizes **Firebase** for real-time communication between the Raspberry Pi and the Django server.

## 📌 Features
- **Gesture Detection**: Recognizes specific hand gestures using OpenCV and Mediapipe.
- **Live Streaming**: Streams real-time camera footage through a Django-based web server.
- **Event Triggering**: Uses Firebase Realtime Database to manage trigger events.
- **Remote Control**: Allows triggering and stopping the stream remotely.

## 🛠️ Technology Stack
- **Raspberry Pi**: Main hardware platform
- **Python**: Core programming language
- **OpenCV & Mediapipe**: Gesture detection libraries
- **Django**: Web framework for live streaming
- **Firebase**: For real-time event communication

## 📂 Project Structure
```
├── gesture_detection/        # Gesture detection script
├── django_server/            # Django project for live streaming
├── firebase_config/          # Firebase configuration files
├── README.md                 # Project documentation
└── requirements.txt          # Required Python packages
```

## 🚀 How It Works
1. **Gesture Detection**: 
   - The Raspberry Pi camera monitors for a specific hand gesture.
   - Upon detection, an event is sent to Firebase.

2. **Trigger Django Server**:
   - When Firebase detects the trigger, the Django server starts.
   - The live camera feed becomes accessible through a web interface.

3. **Stop the Stream**:
   - Another gesture or command can stop the stream.

## 🔧 Setup Instructions
### Prerequisites
- Raspberry Pi (tested on Raspberry Pi 4)
- Python 3.x
- Internet connection

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/gesture-streaming.git
cd gesture-streaming
```

### Step 2: Set Up Virtual Environment
```bash
python -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Configure Firebase
1. Create a Firebase project and enable the **Realtime Database**.
2. Download `serviceAccountKey.json` and place it in the `firebase_config/` folder.

### Step 5: Run the System
1. Start the gesture detection script:
```bash
python gesture_detection/main.py
```
2. Ensure the Django server starts when triggered or run manually:
```bash
cd django_server
python manage.py runserver
```

## 📊 Customization
- **Gesture Recognition**: Modify `gesture_detection/main.py` to add or change gesture patterns.
- **Firebase Events**: Adjust the database schema to track different events.

## 🐞 Troubleshooting
- Ensure the camera is connected and accessible.
- Verify Firebase credentials are correct.
- Check for errors in the Django logs using:
```bash
tail -f d
