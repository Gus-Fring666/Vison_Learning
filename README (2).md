# VocabLearn

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.30+-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-00FFFF?style=for-the-badge)](https://ultralytics.com)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.8+-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org)

---

# 📚 VocabLearn
AI-Powered real-time vocabulary trainer — point your webcam at everyday objects and learn their English names instantly using state-of-the-art object detection.

VocabLearn uses YOLOv8 to detect objects from your webcam or uploaded images and builds an interactive vocabulary list for learning and review.

---

## ✨ Key Features

- 🎥 Real-time detection with a live webcam feed (Frame-by-frame YOLOv8 inference)
- Stylish detection boxes with confidence scores
- Support for multiple camera sources (built-in/external/USB)
- 📖 Automatic vocabulary tracking (word collection, counts, visual progress)
- 📊 Session statistics (words learned, total detections, most detected, session duration)
- 📸 Screenshot capture, gallery, and per-image downloads
- 📁 Image upload mode for offline/image-based detection
- 💾 Export vocabulary as JSON for use with flashcard tools
- ⚙️ Adjustable settings: confidence threshold, camera source, model selection

---

## 🧩 What it Detects
VocabLearn uses the YOLOv8 Nano model (`yolov8n.pt`) and recognizes the 80 object classes from the COCO dataset (everyday object categories). You can change the model to `yolov8s`, `yolov8m`, `yolov8l`, or `yolov8x` for different accuracy/speed trade-offs.

---

## 🚀 Quick Start

### Requirements
- Python 3.9 or higher
- Webcam (for live detection) or images for upload mode
- pip package manager

### Clone the repository
```bash
git clone https://github.com/Gus-Fring666/Vison_Learning.git
cd Vison_Learning
```

### Install dependencies
Install from requirements:
```bash
pip install -r requirements.txt
```
Or install manually:
```bash
pip install streamlit ultralytics opencv-python-headless numpy Pillow
```
Note: Use `opencv-python` instead of `opencv-python-headless` if you plan to run the OpenCV desktop app with native windows.

### Model weights
The `yolov8n.pt` weights will be automatically downloaded by the Ultralytics library on first run. If you prefer, place a model file in the project root.

---

## 🖥️ Running the App

Streamlit (recommended):
```bash
streamlit run streamlit_app.py
```
OpenCV desktop app (original):
```bash
python app.py
```

Streamlit will open at `http://localhost:8501` by default.

---

## 🎮 Usage Guide

### Live Detection
1. Click "Start Detection" to enable the webcam.
2. Point the camera at everyday objects.
3. Watch detections appear and be added to your vocabulary list automatically.
4. Click "Stop Detection" to pause.

### Image Upload Mode
1. Use "Upload Image" to analyze local images (JPG, PNG, BMP, WebP).
2. Results are shown with the same detection overlays and added to vocabulary.

### Screenshots
- Click "Screenshot" while the camera is running to save the current annotated frame to `screenshots/`.
- View and download screenshots from the gallery.

### Export Vocabulary
- Click "Download Vocabulary (JSON)" to export detected words and counts.

---

## ⚙️ Configuration & Settings

- MODEL_NAME: `yolov8n.pt` by default — change for better/worse speed/accuracy.
- Confidence threshold: adjustable (10%–95%) — default recommended ~0.45.
- Camera index: default `0`. Use the Camera Source dropdown to switch.

Recommended presets:
- High accuracy: `yolov8l` or `yolov8x` with higher confidence threshold (0.6–0.75).
- Highest speed: `yolov8n` with moderate threshold (0.35–0.5).

---

## 🐛 Troubleshooting

- Camera not opening: ensure no other app is using the camera; try different index (0, 1, 2).
- Slow performance: use `yolov8n.pt`, reduce resolution, or close other heavy apps.
- No detections: lower confidence threshold, improve lighting, ensure objects fill the frame.
- Model download fails: verify internet connection or manually place `yolov8n.pt` in the project root.
- Import errors: run `pip install -r requirements.txt`.

---

## 🧭 Project Structure (example)
```
Vison_Learning/
├── streamlit_app.py        # Streamlit web app (main)
├── app.py                  # OpenCV desktop app
├── requirements.txt        # Dependencies
├── README.md               # Project documentation
├── yolov8n.pt              # Model weights (auto-download)
└── screenshots/            # Saved screenshots
```

---

## 📈 Ideas for Improvements / Contributing
Contributions welcome! Suggested enhancements:
- Multi-language support (translate detected terms)
- Quiz mode (user names the object before reveal)
- Analytics dashboard (progress across sessions)
- Text-to-speech for pronunciations
- Custom model training for domain-specific objects
- Mobile/browser optimizations

If you'd like to contribute, fork the repo, open a branch, and submit a PR. Include tests and update the README where appropriate.

---

## 📄 License
This project is released under the MIT License. See the LICENSE file for details.

---

Built with ❤️ using Streamlit + YOLOv8 — VocabLearn © 2026