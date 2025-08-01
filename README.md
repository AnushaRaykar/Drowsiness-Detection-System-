
---

## 📄 Abstract

This project implements a real-time driver drowsiness detection system optimized for embedded platforms. It addresses key challenges in eye image acquisition and head tilt variations, leveraging image processing techniques for face and eye detection, object tracking, and eye state classification using PERCLOS (Percentage of Eyelid Closure).

---

## ⚙️ System Overview

The proposed method follows this sequence:

1. **Face Detection** using Haar-like features and AdaBoost.
2. **Eye Initialization** using horizontal projection curves.
3. **Eye Tracking** using CAMSHIFT with YCrCb color space.
4. **Eye State Identification** using binary complexity and corner features.
5. **PERCLOS Calculation** for final drowsiness detection.

---

## 🔁 System Flow

### 🕵️ Former Flowchart
- Image Capture → Face Detection → Eye Detection → Eye State Identification → Drowsiness Judgment

### 🚀 Proposed Real-Time Flowchart
- Erect Face Detection → Eye Initialization → CAMSHIFT Eye Tracking → Eye State Identification → PERCLOS → Drowsiness Detection

This approach increases speed and accuracy by avoiding repetitive full-face detection in each frame.

---

## 🧠 Methodology

### 1. Face & Eye Detection
- **Face Detection**: Haar-like features with AdaBoost cascade classifiers.
- **Eye Localization**: Horizontal projection analysis identifies eye regions within the face.

### 2. Eye Tracking
- Uses the **CAMSHIFT** algorithm in the **YCrCb** color space.
- Tracks eyes across frames after initial detection.

### 3. Eye State Recognition
- Eye region is binarized and analyzed using:
  - **Complexity functions**
  - **Corner detection** (eigenvalue analysis)
- Combined metrics determine eye state (open/closed).

### 4. PERCLOS Calculation
- PERCLOS is derived from frame-by-frame analysis of eye states to determine drowsiness.

---

## 💻 Embedded Platform

- **Target Board**: GENE-8310
- **CPU**: 600MHz
- **RAM**: 256MB
- **Resolution**: 320×240
- **Real-time Performance**: ~12 FPS
- **Accuracy**: ~90% (under fixed camera and consistent face distance)

---

## 📊 Sample Results

| Test Subject | Accuracy (%) |
|--------------|--------------|
| Person 1     | 91.2         |
| Person 2     | 89.7         |
| Person 3     | 90.1         |
| ...          | ...          |
| **Average**  | **90.0%**    |

> Note: Accuracy drops with significant head movement or varying camera distance.

---

## 🛠️ Requirements

- OpenCV (for image processing)
- C++ or Python (depending on implementation)
- Embedded Linux support
- Optional: Git LFS (for large datasets)

---



