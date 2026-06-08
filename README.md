# Intelligent Door Unlock System

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-brightgreen?logo=opencv)
![DeepFace](https://img.shields.io/badge/DeepFace-Face%20Recognition-blue)
![IoT](https://img.shields.io/badge/Raspberry%20Pi-IoT-red?logo=raspberrypi)
![License](https://img.shields.io/badge/License-MIT-green)

> Biometric door unlock system combining face recognition (DeepFace + OpenCV Haar cascades) and voice authentication (MFCC + DTW). Designed for Raspberry Pi with real-time detection and access logging.

## Architecture
```
Camera (Raspberry Pi / USB webcam)
        ↓
Face Detection — Haar Cascade Classifier
        ↓
Face Recognition — DeepFace (VGG-Face model)
  └── Compare against enrolled faces DB
        ↓  PARALLEL
Microphone Input
        ↓
Voice Verification — MFCC + Dynamic Time Warping
        ↓
Access Decision Engine
  ├── BOTH factors match → UNLOCK + log event
  └── Either fails       → DENY  + alert
        ↓
Access Log (CSV / SQLite)
```

## Features

| Feature | Implementation |
|---|---|
| Face detection | OpenCV Haar cascade (`haarcascade_frontalface_default.xml`) |
| Face recognition | DeepFace with VGG-Face embeddings |
| Voice verification | MFCC feature extraction + DTW distance matching |
| Enrolment | `voice_face_record.py` — capture and store user profile |
| Access logging | Timestamped logs with result and confidence score |
| Raspberry Pi ready | GPIO relay control for door lock mechanism |

## Setup
```bash
git clone https://github.com/jaiminbabariya7/Intelligent-door-unlock-system
cd Intelligent-door-unlock-system
pip install -r requirement.txt

# Enrol a new user
python voice_face_record.py --name "John"

# Start the access system
python voice_face_recognize.py
```

## Skills Demonstrated
`Python` · `OpenCV` · `DeepFace` · `Face Recognition` · `MFCC` · `IoT` · `Raspberry Pi` · `Biometric Authentication`
