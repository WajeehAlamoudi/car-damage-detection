# 🚗 Car Damage Detection with YOLOv11 🚨



## 🛠️ Project Overview

This project uses **YOLOv11** for **car damage detection**.\
It identifies 6 types of damages:

- 🔹 **Dent**
- 🔹 **Scratch**
- 🔹 **Crack**
- 🔹 **Shattered Glass**
- 🔹 **Broken Lamp**
- 🔹 **Flat Tire**

**Dataset:** **[Car Damage Detection Dataset (CarDD)](https://cardd-ustc.github.io/)**

---

## 🌐 Colab Notebook Link

Run the model directly in Google Colab:\
👉 **[Open in Colab](https://colab.research.google.com/drive/1r2FSsgA0bVukHbe_9vOxQNAnFK44m7Sv?usp=sharing)**

---

## 🔍 Dataset Overview

**Dataset Source:** **[CarDD (USTC)](https://cardd-ustc.github.io/)**

**Dataset Structure:**

```plaintext
📂 car_damage_dataset
    ├── 📂 images
    │       ├── train (2816 images)
    │       ├── val   (810 images)
    │       └── test  (374 images)
    └── 📂 labels
            ├── train (YOLO format)
            ├── val
            └── test
```

**Classes (6 total):**

| ID | Class         | Description                      |
| -- | ------------- | -------------------------------- |
| 0  | Dent          | Car dents                        |
| 1  | Scratch       | Scratches on the car body        |
| 2  | Crack         | Cracks on the surface            |
| 3  | Shatter Glass | Broken or cracked car glass      |
| 4  | Broken Lamp   | Damaged headlights or taillights |
| 5  | Flat Tire     | Deflated or punctured tires      |

---

## 🛠️ Model Training & Configuration

**Model:** YOLOv11 (Segmentation)\
**Base Weights:** `yolo11l-seg.pt`\
**Augmentation:** Albumentations (Blur, MedianBlur, CLAHE)

### 🔧 **Training Configuration**

```yaml
train: /content/drive/MyDrive/CARS DATA/Abdulrahman/car_damage_dataset/images/train
val: /content/drive/MyDrive/CARS DATA/Abdulrahman/car_damage_dataset/images/val
test: /content/drive/MyDrive/CARS DATA/Abdulrahman/car_damage_dataset/images/test

nc: 6
names: ["dent", "scratch", "crack", "shatter glass", "broken lamp", "flat tire"]
```

---

## 🚀 Model Performance

### 🏆 **Test Set Metrics**

- 🧠 **Precision (Boxes)**: `62.0%`
- 🧠 **Recall (Boxes)**: `66.7%`
- 🧠 **mAP\@50 (Boxes)**: `67.2%`
- 🎨 **Precision (Masks)**: `52.8%`
- 🎨 **Recall (Masks)**: `43.7%`
- 🎯 **mAP\@50 (Masks)**: `45.7%`

---

## 🧪 Sample Test Images & Predictions

### 📷 **Original Test Samples**

Here are **4 random samples** from the **test set**:

\
\
\


---

### 🛠️ **Predicted Test Images**

\
\
\


---

## 🚀 How to Run Inference Locally

### 🔧 **Install Required Packages**

```bash
pip install ultralytics opencv-python matplotlib
```

### 🧠 **Run Inference**

```python
from ultralytics import YOLO

# Load the model
model = YOLO("/path/to/best.pt")

# Run inference
model.predict(source="/path/to/test/image.jpg", imgsz=640, conf=0.5, save=True)
```

---

## 📊 Results Summary

- **Inference Speed:** \~ **12.56 ms/image**
- **Dataset Size:** 4000 images
- **Model:** YOLOv11-Large (Segmentation)

---

### 🌐 **References**

- **[CarDD Dataset (USTC)](https://cardd-ustc.github.io/)**
- **[Ultralytics YOLO Documentation](https://docs.ultralytics.com/)**
- **[Colab Notebook](https://colab.research.google.com/drive/1r2FSsgA0bVukHbe_9vOxQNAnFK44m7Sv?usp=sharing)**

---

👨‍💻 **Developed By:** **Abdulrahman** 🛠️\
🎯 **Project Focus:** **Car Damage Detection** with **YOLOv11** 🚗

