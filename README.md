# 🧬 Cancer Detection Dataset for YOLOv8

This dataset is prepared for training a **YOLOv8 object detection model** to detect cancer regions in medical images.

---

## 📁 Dataset Structure

dataset/
├── train/
│ ├── images/ # Training images
│ └── labels/ # YOLO-format label files for training
├── valid/
│ ├── images/ # Validation images
│ └── labels/ # YOLO-format label files for validation
└── test/
├── images/ # Test images
└── labels/ # YOLO-format label files for testing


> ⚠️ All `label/` folders have been renamed to `labels/` to comply with YOLOv8 structure.

---

## 📝 Annotation Format

The dataset uses the **YOLO format**:

<class_id> <x_center> <y_center> <width> <height>


- Coordinates are **normalized** (values between 0 and 1).
- `class_id` is `0` for all annotations (indicating "cancer").

**Example:**
0 0.532 0.482 0.156 0.210


---

## 🖼 Image Requirements

- Supported formats: `.jpg`, `.png`
- For each image, there must be a corresponding `.txt` file in the `labels/` folder.

---

## ⚙️ YAML Configuration for YOLOv8

Here is the sample `cancer_data.yaml` file used for training:

```yaml
path: /absolute/path/to/dataset
train: train/images
val: valid/images
test: test/images

nc: 1
names: ['cancer']
