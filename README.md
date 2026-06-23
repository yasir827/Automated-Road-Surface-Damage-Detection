# 🛣️ AI-Powered Road Damage Detection System using YOLOv8

## 📌 Overview

This project presents an AI-Powered Road Damage Detection System developed using YOLOv8 and Computer Vision techniques. The system automatically detects road surface damage from images, helping transportation authorities and infrastructure agencies monitor road conditions efficiently.

The project includes dataset preparation, model training, validation, inference, and performance evaluation using modern object detection techniques.

---

## 🎯 Objectives

* Detect road surface damage automatically from images.
* Apply deep learning techniques for infrastructure monitoring.
* Reduce manual road inspection efforts.
* Develop a deployment-ready AI solution for smart transportation systems.

---

## 🏗️ Project Pipeline

```text
Road Damage Detection System (YOLOv8)

        │
        ▼
Dataset Collection
        │
        ▼
Dataset Download
(KaggleHub)
        │
        ▼
Image & Annotation Inspection
        │
        ▼
YOLO Dataset Configuration
(data.yaml)
        │
        ▼
Model Initialization
(YOLOv8n)
        │
        ▼
Model Training
(15 Epochs)
        │
        ▼
Feature Learning
& Object Detection
        │
        ▼
Model Validation
        │
        ▼
Best Weights Selection
(best.pt)
        │
        ▼
Road Damage Detection
on New Images
        │
        ▼
Performance Evaluation
        │
        ▼
Deployment Ready Model
```

---

# 📂 Dataset

## Dataset Name

Road Damage Detection Dataset

## Dataset Source

Downloaded from Kaggle using KaggleHub:

```python
import kagglehub

path = kagglehub.dataset_download(
    "matijaraovi/road-damage-detection"
)
```

## Dataset Description

The dataset contains road images with annotations identifying damaged road regions. The dataset is formatted for object detection tasks and can be directly used with YOLO models.

## Dataset Structure

```text
dataset/
│
├── train/
│   ├── images/
│   └── labels/
│
├── val/
│   ├── images/
│   └── labels/
│
└── data.yaml
```

## Class Information

| Class ID | Class Name  |
| -------- | ----------- |
| 0        | road_damage |

### Total Classes

* 1 Object Detection Class

## Annotation Format

YOLO format:

```text
class_id x_center y_center width height
```

Example:

```text
0 0.542 0.488 0.163 0.215
```

## Data Preparation

* Dataset downloaded using KaggleHub
* Image folders verified
* Annotation files inspected
* Training and validation paths identified
* Custom YOLO data.yaml file generated
* Dataset prepared for YOLOv8 training

---

# 🛠️ Technologies Used

* Python
* YOLOv8
* Ultralytics
* OpenCV
* KaggleHub
* PyYAML
* Matplotlib
* Deep Learning
* Computer Vision

---

# ⚙️ Model Configuration

| Parameter  | Value              |
| ---------- | ------------------ |
| Model      | YOLOv8n            |
| Task       | Object Detection   |
| Epochs     | 15                 |
| Image Size | 320 × 320          |
| Batch Size | 4                  |
| Device     | CPU                |
| Framework  | Ultralytics YOLOv8 |

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/AI-Powered-Road-Damage-Detection-System-using-YOLOv8.git

cd AI-Powered-Road-Damage-Detection-System-using-YOLOv8
```

## Install Dependencies

```bash
pip install ultralytics kagglehub opencv-python matplotlib pyyaml
```

---

# 🏋️ Model Training

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

model.train(
    data="data.yaml",
    epochs=15,
    imgsz=320,
    batch=4
)
```

---

# 📊 Model Evaluation

The model was evaluated using standard object detection metrics:

* Precision
* Recall
* mAP@50
* mAP@50-95

Example:

```python
metrics = model.val()

print(metrics.box.map50)
print(metrics.box.map)
print(metrics.box.mp)
print(metrics.box.mr)
```

---

# 🔍 Inference

## Load Trained Model

```python
from ultralytics import YOLO

model = YOLO("best.pt")
```

## Predict on New Images

```python
results = model.predict(
    source="test_images/",
    conf=0.25,
    save=True
)
```

---

# 📁 Repository Structure

```text
Road-Damage-Detection-System/
│
├── dataset/
│
├── runs/
│   └── detect/
│       └── train/
│           └── weights/
│               └── best.pt
│
├── data.yaml
├── train.py
├── predict.py
├── requirements.txt
├── README.md
│
└── assets/
    ├── pipeline.png
    ├── results.png
    └── predictions.png
```

---

# 🎯 Applications

* Smart Road Inspection
* Infrastructure Monitoring
* Road Maintenance Planning
* Smart City Solutions
* Transportation Safety Analysis
* Automated Damage Assessment

---

# ✅ Project Results

✔ Dataset successfully processed

✔ YOLOv8 model trained successfully

✔ Road damage regions detected accurately

✔ Validation and inference completed

✔ Detection visualizations generated

✔ Deployment-ready model produced

---

# 🔮 Future Improvements

* Multi-class road damage detection
* Real-time video analysis
* Drone-based road inspection
* Mobile application integration
* Cloud deployment
* Smart city monitoring dashboard



# ⭐ Acknowledgements

* Ultralytics YOLOv8
* KaggleHub
* OpenCV Community
* Computer Vision Research Community
* Road Damage Detection Dataset Contributors
