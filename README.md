# mango-detection-yolo-augmentation
This study systematically evaluates the impact of dataset augmentation on the performance of advanced You Only Look Once (YOLO) architectures for mango fruit detection under natural orchard conditions.

The models evaluated include:

YOLOv5,
YOLOv8,
YOLOv9,
YOLOv10,
YOLO11,
YOLO12
# Dataset Description
-Total Images: 516 RGB images
-Mango Variety: Pusa Mallika
-Image Sources: Mobile and digital cameras
-Conditions: Natural orchard environments with varying lighting
# Annotation
-Tool used: LabelImg
-Format: YOLO annotation format
-Image size: Resized to 640 × 640 pixels
# Dataset Configurations
Three dataset variants were created to evaluate augmentation impact:
-D1: Original dataset
-D2: 1× augmented dataset
-D3: 2× augmented dataset
# Data Split
Each dataset was split into:
-Training: 80%
-Validation: 10%
-Testing: 10%
# Experimental Setup
Each YOLO model was trained independently on all dataset configurations
Three replications were conducted using different random seeds
This ensures:
Robustness
Reproducibility
Statistical reliability
## Implementation Details

This work utilizes the official implementation provided by the Ultralytics YOLO framework.

* Framework: Ultralytics YOLO
* Source: https://github.com/ultralytics/ultralytics
* Usage: Models were trained using the built-in training pipeline without modification to the core source code

Customizations in this study include:

* Dataset preparation and augmentation strategies
* Model configuration selection (YOLOv5–YOLO12 variants)
* Experimental design with multiple dataset configurations (D1, D2, D3)
* Evaluation and statistical analysis

---

## ⚙️ Installation

```bash
pip install ultralytics
```

---

## 🚀 Training Command

```bash
yolo detect train model=yolo11.yaml data=data.yaml epochs=100 imgsz=640 batch=16
```

---

## 📜 License and Acknowledgment

We acknowledge and thank the developers of the Ultralytics YOLO framework for providing an open-source and well-maintained implementation.

If you use this repository, please also consider citing the Ultralytics repository.
