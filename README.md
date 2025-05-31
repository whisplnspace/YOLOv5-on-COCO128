# 🧠 YOLOv5 on COCO128

This repository demonstrates object detection using **YOLOv5** trained on the **COCO128** dataset — a small subset of the COCO dataset containing 128 images and 80 object categories. Ideal for quick experimentation, debugging, and learning.

![Detection Sample](https://github.com/user-attachments/assets/b8143923-59fb-40dd-8421-e2733ff1987b)

---

## 🚀 Features

- ⚡ Fast and accurate object detection with YOLOv5
- 🧪 Train or test on COCO128 (128 training + 128 validation images)
- 📦 Easy setup and minimal compute required
- 📈 Supports training, validation, testing, and inference

---

## 📂 Dataset — COCO128

The **COCO128** dataset is a lightweight subset of the COCO2017 dataset used for testing and benchmarking YOLO models.

- Download URL: [COCO128](https://github.com/ultralytics/yolov5/releases/download/v1.0/coco128.zip)
- Categories: 80 (same as full COCO)
- Size: ~20 MB

---

## 🛠️ Setup Instructions

1. **Clone YOLOv5 repository:**

```bash
git clone https://github.com/ultralytics/yolov5
cd yolov5
pip install -r requirements.txt
````

2. **Download COCO128 dataset:**

```bash
curl -L https://github.com/ultralytics/yolov5/releases/download/v1.0/coco128.zip -o coco128.zip
unzip coco128.zip
```

3. **Train YOLOv5 on COCO128:**

```bash
python train.py --img 640 --batch 16 --epochs 3 --data coco128.yaml --weights yolov5s.pt --cache
```

4. **Run inference:**

```bash
python detect.py --weights runs/train/exp/weights/best.pt --img 640 --source coco128/images/train2017
```

---

## 📊 Results

After a few epochs on COCO128, expect moderate accuracy—this dataset is meant for speed, not performance.

Example output:

```
Precision: 0.45
Recall:    0.42
mAP_0.5:   0.47
```

> Note: Use full COCO or custom datasets for real-world performance.

---

```bash
# Single image inference
python detect.py --weights yolov5s.pt --img 640 --source data/images/zidane.jpg
```

---

## 📁 Folder Structure

```
.
├── yolov5/                   # YOLOv5 repo
├── coco128/                  # Dataset (images, labels)
├── runs/                     # Training outputs
├── detect.py                 # Inference script
├── train.py                  # Training script
└── data/coco128.yaml         # Dataset config file
```

---

## 📌 Notes

* For custom data, modify `data.yaml`
* For better results, use full datasets (e.g., COCO2017, Pascal VOC)
* Use `yolov5m`, `yolov5l`, or `yolov5x` for higher accuracy (at cost of speed)

---

## 🤝 Acknowledgements

* [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)
* [COCO Dataset](https://cocodataset.org)

