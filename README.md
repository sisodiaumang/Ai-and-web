Vision‑Language Scene Geometry Analysis

A deep learning–based system for single-image scene understanding using monocular depth estimation and semantic motion cue inference.

This project analyzes a single RGB image to:

Estimate dense depth maps

Perform relative depth reasoning between regions

Infer semantic motion cues from spatial depth gradients

Provide a web-based interface for interactive analysis



---

📌 Overview

Understanding 3D scene structure from a single image is a fundamental challenge in computer vision.

This system combines:

MiDaS for monocular depth estimation

Relative depth reasoning algorithms

Semantic motion cue inference from depth gradients

FastAPI backend for inference

Frontend UI for interactive visualization


The system does not perform real motion tracking.
It estimates motion cues based on spatial depth variations and posture heuristics.


---

🚀 Features

Dense depth estimation from a single image

Relative distance comparison between selected regions

Motion cue inference using depth gradient analysis

REST API backend (FastAPI)

Web-based frontend interface

Visualization of depth maps



---

🏗️ System Architecture

Frontend (HTML/CSS/JS)
        ↓
FastAPI Backend
        ↓
VisionLanguageDepthEstimator
        ↓
MiDaS (Depth Model)


---

🛠️ Technologies Used

Python 3.10+

PyTorch

MiDaS (Intel-ISL)

Transformers (DistilBERT – optional semantic encoding)

FastAPI

Uvicorn

OpenCV

NumPy

Matplotlib



---

📂 Project Structure

vision-language-app/
│
├── backend/
│   ├── main.py
│   ├── estimator.py
│   └── uploads/
│
├── frontend/
│   ├── index.html
│   ├── styles.css
│   └── app.js
│
└── README.md


---

⚙️ Installation

1️⃣ Clone the Repository

git clone https://github.com/umangsisodia/vision-language-scene-geometry.git
cd vision-language-scene-geometry/backend

2️⃣ Create Virtual Environment (Recommended)

python -m venv venv
venv\Scripts\activate  # Windows

3️⃣ Install Dependencies

pip install torch torchvision torchaudio
pip install fastapi uvicorn
pip install transformers
pip install opencv-python matplotlib numpy


---

▶️ Running the Backend

From the backend directory:

python -m uvicorn main:app --host 127.0.0.1 --port 8000

Open API docs:

http://127.0.0.1:8000/docs


---

🌐 Running the Frontend

Open:

frontend/index.html

Or use Live Server in VS Code.

Make sure app.js points to:

http://127.0.0.1:8000/analyze


---

📊 API Endpoint

POST /analyze

Form Data:

image (JPEG/PNG)

prompt (string)

region_fg (left/right/center)

region_bg (left/right/center)


Returns:

{
  "avg_depth_foreground": float,
  "avg_depth_background": float,
  "distance_result": "string",
  "motion_cue": "string",
  "depth_map_image": "base64 image"
}


---

🧠 How Motion Cue Estimation Works

The system:

1. Computes depth map


2. Extracts region depth statistics


3. Calculates horizontal depth gradients


4. Infers possible motion tendency based on spatial disparity



This is semantic inference, not physical motion detection.


---

🎓 Academic Context

This project was developed as a 4th semester academic project focusing on:

Monocular depth estimation

Scene geometry reasoning

Vision-language integration concepts

Explainable AI inference pipelines



---

⚠️ Limitations

Not real-time motion tracking

Motion inference is heuristic-based

Depends on pretrained depth model

Performance limited on CPU-only systems



---

📌 Future Improvements

True vision-language grounding

Region detection from prompt text

Object detection integration

GPU acceleration

Real-time video support



---

📜 License

Academic Use Only


---
