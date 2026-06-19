# 🎯 AI Cricket Ball Tracking and Trajectory Visualization System

A computer vision project that detects, tracks, and visualizes the trajectory of a fast-moving cricket ball using deep learning and Kalman filtering. The system generates a smooth Hawk-Eye/DRS-style trajectory overlay and exports the final annotated video.

---

## 📌 Project Overview

This project combines object detection, tracking, trajectory smoothing, and 3D-inspired rendering to create a broadcast-style ball tracking system similar to those used in Hawk-Eye and DRS technologies.

The pipeline detects the ball in each frame, tracks its motion using a Kalman filter, removes outliers, smooths the trajectory, and overlays a visually appealing trajectory tube onto the original video.

---

## ✨ Features

- ⚡ Cricket ball detection using YOLO
- 🎯 Kalman Filter based tracking
- 🧹 Automatic outlier removal
- 📈 Trajectory smoothing using Savitzky-Golay filtering and spline interpolation
- 🏏 Hawk-Eye / DRS style trajectory visualization
- 🌟 Perspective-based 3D effect
- 🎥 Generates annotated output video automatically
- 🚀 Designed for Google Colab
- 🔥 GPU accelerated inference

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
├── SportsVision_HawkEye.ipynb
├── best.pt
├── cricket clips 10.mp4
├── output_drs_final.mp4
└── README.md
```

---

## ⚙️ Methodology

### 1. Ball Detection

The cricket ball is detected frame-by-frame using a YOLO model trained specifically for ball detection.

### 2. Kalman Filter Tracking

A 3D Kalman Filter estimates:

- Position (x, y, z)
- Velocity (vx, vy, vz)

This allows the tracker to maintain smooth trajectories even when detections are temporarily lost.

### 3. Outlier Removal

Large jumps and false detections are filtered out to ensure trajectory consistency.

### 4. Trajectory Smoothing

The raw trajectory is refined using:

- Savitzky-Golay Filtering
- Cubic Spline Interpolation

to generate a smooth curve.

### 5. Hawk-Eye Style Rendering

A perspective-aware renderer generates a broadcast-style trajectory with:

- Dynamic thickness
- Depth effect
- Ball head rendering
- Anti-aliasing

---

## 📸 Sample Output

<img width="1917" height="891" src="https://github.com/user-attachments/assets/20559603-fbc2-415f-9df8-e3fea25caf51">

---

## 🚀 Running on Google Colab

This notebook is designed to run on **Google Colab with GPU acceleration**.

### Enable GPU

Go to:

```text
Runtime → Change runtime type → T4 GPU → Save
```

Verify GPU availability:

```python
import torch

print(torch.cuda.is_available())
print(torch.cuda.get_device_name(0))
```

---

## ▶️ Usage

1. Open `SportsVision_HawkEye.ipynb` in Google Colab.
2. Enable GPU.
3. Upload:

- `best.pt`
- Input cricket video

4. Run all notebook cells sequentially.
5. Download the generated output video.

---

## 📦 Output

The final annotated video is saved as:

```text
output_drs_final.mp4
```

---

## Applications

- Cricket DRS Visualization
- Ball Tracking
- Sports Analytics
- Broadcast Graphics
- Computer Vision Research

---

## Future Improvements

- True 3D mesh rendering
- Multi-object tracking
- Real-time inference
- OpenGL-based rendering
- Monocular depth estimation
- Physics-based trajectory prediction
- Camera calibration for world-coordinate reconstruction

---

## Author

**Sunayana Yadav**

B.E. EXTC, Lokmanya Tilak College of Engineering  
AI & Computer Vision Enthusiast

---

## License

This project is intended for educational and research purposes.
