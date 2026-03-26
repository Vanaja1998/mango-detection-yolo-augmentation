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
-Total Images: 516 RGB images<br>
-Mango Variety: Pusa Mallika<br>
-Image Sources: Mobile and digital cameras<br>
-Conditions: Natural orchard environments with varying lighting<br>
# Dataset Availability

The dataset is not publicly released. However, it can be made available upon reasonable request for academic and research purposes.<br>

Please contact the author for access.

# Annotation
-Tool used: LabelImg<br>
-Format: YOLO annotation format<br>
-Image size: Resized to 640 × 640 pixels
# Dataset Configurations
Three dataset variants were created to evaluate augmentation impact:<br>
-D1: Original dataset<br>
-D2: 1× augmented dataset<br>
-D3: 2× augmented dataset
# Data Split
Each dataset was split into:<br>
-Training: 80%<br>
-Validation: 10%<br>
-Testing: 10%
# Experimental Setup
Each YOLO model was trained independently on all dataset configurations<br>
YOLOv5 was implemented using its official GitHub repository, while the remaining models were trained using the Ultralytics package with a unified training pipeline to ensure consistency across experiments.<br>

Three replications were conducted using different random seeds<br>
This ensures:<br>
Robustness<br>
Reproducibility<br>
Statistical reliability<br>
## Implementation Details

This work utilizes the official implementation provided by the Ultralytics YOLO framework.<br>

* Framework: Ultralytics YOLO<br>
* Source: https://github.com/ultralytics/ultralytics<br>
* Usage: Models were trained using the built-in training pipeline without modification to the core source code<br>

Customizations in this study include:<br>

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
from ultralytics import YOLO

seeds = [42, 123, 999]

for seed in seeds:
    model = YOLO("yolov8s.pt")
    
    results = model.train(
        data="data/data.yaml",   # ✅ clean relative path
        epochs=200,
        imgsz=640,
        batch=8,
        seed=seed,
        project="runs/train",
        name=f"Mango_seed{seed}"
    )
```

---
# Statistical Analysis

To rigorously evaluate the impact of dataset augmentation and model architecture, statistical analysis was performed using Python.

* A two-way ANOVA was conducted to assess the main and interaction effects
* Tukey’s HSD post hoc test was applied for pairwise comparisons

The complete implementation is available in:

`anova_tukey_yolo.py`

This script reproduces the statistical evaluation methodology described in the paper.


# License and Acknowledgment

We acknowledge and thank the developers of the Ultralytics YOLO framework for providing an open-source and well-maintained implementation.

If you use this repository, please also consider citing the Ultralytics repository.
