# 🎯 AI-Cricket-Ball-Tracking-and-Trajectory-Visualization system

A computer vision project that detects, tracks, and visualizes the trajectory of a fast-moving ball using deep learning and Kalman filtering. The system generates a smooth Hawk-Eye/DRS-style trajectory overlay and exports the final annotated video.

---

## 📌 Project Overview

This project combines object detection, tracking, trajectory smoothing, and 3D-inspired rendering to create a broadcast-style ball tracking system similar to those used in cricket DRS and Hawk-Eye technologies.

The pipeline detects the ball in each frame, tracks its motion using a Kalman filter, removes outliers, smooths the trajectory, and finally overlays a visually appealing trajectory tube on the original video.

---

## ✨ Features

- ⚡ Fast ball detection using YOLO
- 🎯 Kalman Filter based object tracking
- 🧹 Automatic outlier removal
- 📈 Trajectory smoothing using Savitzky-Golay Filter and Splines
- 🎥 Frame-by-frame rendering
- 🏏 Hawk-Eye/DRS style trajectory visualization
- 🌟 Perspective-based 3D effect
- 📦 Generates final output video automatically
- 🚀 Google Colab compatible

---

## 🏗️ Pipeline

```text
Input Video
      │
      ▼
Ball Detection (YOLO)
      │
      ▼
Kalman Tracking
      │
      ▼
Outlier Removal
      │
      ▼
Trajectory Smoothing
(Savitzky-Golay + Spline)
      │
      ▼
3D Trajectory Rendering
      │
      ▼
Output Video
```

---

## 🛠️ Technologies Used

### Programming Language

- Python

### Deep Learning

- Ultralytics YOLO

### Computer Vision

- OpenCV

### Tracking

- FilterPy Kalman Filter

### Scientific Computing

- NumPy
- SciPy

### Visualization

- Matplotlib

### Environment

- Google Colab
- Jupyter Notebook

---

## 📂 Project Structure

```text
.
├── input_video.mp4
├── best.pt                 # YOLO trained weights
├── notebook.ipynb
├── output_video.mp4
├── requirements.txt
└── README.md
```

---

## ⚙️ Methodology

### 1. Ball Detection

The ball is detected frame-by-frame using a YOLO model trained specifically for ball detection.

---

### 2. Kalman Filter Tracking

A 3D Kalman Filter estimates:

- Position (x, y, z)
- Velocity (vx, vy, vz)

which helps maintain a smooth trajectory even when detections are missing.

---

### 3. Outlier Removal

Large jumps and false detections are removed using distance constraints to ensure trajectory consistency.

---

### 4. Trajectory Smoothing

The raw trajectory is refined using:

- Savitzky-Golay Filtering
- Cubic Spline Interpolation

to obtain a smooth curve.

---

### 5. Hawk-Eye Style Rendering

A perspective-aware renderer generates a smooth trajectory tube with:

- Dynamic thickness
- Depth effect
- Ball head rendering
- Anti-aliasing

---

## 📸 Sample Output
<img width="1917" height="891" alt="image" src="https://github.com/user-attachments/assets/20559603-fbc2-415f-9df8-e3fea25caf51" />


### Input

- Original sports video

### Output

- Ball trajectory visualization with Hawk-Eye style overlay

---

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/sunayana90/AI-Cricket-Ball-Tracking-and-Trajectory-Visualization.git
cd hawkeye-ball-tracking
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Usage

Run the notebook or script:

```bash
python main.py
```

or

Open the notebook in Google Colab and execute all cells sequentially.

---

## Output

The generated video will be saved as:

```text
output_video.mp4
```

---

## Applications

- Cricket DRS Visualization
- Golf Ball Tracking
- Tennis Ball Tracking
- Baseball Trajectory Analysis
- Sports Analytics
- Broadcast Graphics
- Computer Vision Research

---

## Future Improvements

- True 3D mesh rendering
- Multi-object tracking
- Real-time inference
- OpenGL-based visualization
- Depth estimation using monocular vision
- Physics-based trajectory prediction
- Camera calibration for accurate world coordinates

---

## Author

**Sunayana Yadav**
---

## License
This project is intended for educational and research purposes.
