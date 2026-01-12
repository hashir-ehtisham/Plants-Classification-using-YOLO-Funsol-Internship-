# 🌿 Plants Classification Model

A deep learning-based image classifier trained to identify **10 different plant species** using **YOLO11n-cls**, a classification variant of the YOLO model.

## 📌 Overview

The **Plants Classification Model** is designed for agricultural, research, and educational applications. It was trained for **5 epochs** using a custom dataset organized into training and validation folders, with all images in **JPG format**.

**Colab Notebook Link:** [Plants Classification Model](https://colab.research.google.com/drive/1cbuKrH7SfAQKuqqFA2JbSvIv39tZtSp-?usp=sharing)

## 🌱 Supported Plant Classes

The model classifies the following **10 plant species**:

1. **Triticum Aestivum** – Wheat Plant  
2. **Oryza Sativa** – Rice Plant  
3. **Zea mays** – Maize (Corn)  
4. **Capsicum Annuum** – Bell Pepper Plant  
5. **Solanum lycopersicum** – Tomato Plant  
6. **Ocimum basilicum** – Basil Plant  
7. **Rosa indica** – Common White Rose  
8. **Cocos Nucifera** – Coconut Tree  
9. **Mangifera indica** – Mango Tree  
10. **Helianthus Annuus** – Sunflower Plant

## 📁 Dataset Structure
```text
/Plants/
├── train/
│   ├── Capsicum Annuum - Bell Pepper Plant/
│   ├── ... (other plant classes)
└── val/
    ├── Capsicum Annuum - Bell Pepper Plant/
    └── ... (other plant classes)
```
### Training Dataset
- **Location:** `train/`
- **Classes:** 10
- **Images per class:** 200
- **Total images:** 2,000
- **Naming:** `<plant-name>-trainXXX.jpg`

### Validation Dataset
- **Location:** `val/`
- **Classes:** 10
- **Images per class:** 20
- **Total images:** 200
- **Naming:** `<plant-name>-valXXX.jpg`

## 🧠 Model Training

- **Base Model:** `yolo11n-cls.pt`
- **Epochs:** 5
- **Input Size:** 416 × 416 pixels
- **Batch Size:** 16
- **Optimizer:** Adam
- **Loss Function:** Classification loss
- **Framework:** Ultralytics YOLO

## 📊 Performance Metrics

- **Average Top-1 Accuracy:** **97.2%**
- **Average Top-5 Accuracy:** **100%**
- **Inference Time:** 28–35 ms per image
- **Preprocessing Time:** ~5–10 ms per image
- **Postprocessing Time:** Negligible

### Training Progress (per epoch)
- **Epoch 1:** Training loss = 1.35 | Validation loss = 0.19 | Top-1 Acc = 95.5%
- **Epoch 2:** Training loss = 0.31 | Validation loss = 0.075 | Top-1 Acc = 97.5%
- **Epoch 3:** Training loss = 0.21 | Validation loss = 0.085 | Top-1 Acc = 97.5%
- **Epoch 4:** Training loss = 0.14 | Validation loss = 0.10 | Top-1 Acc = 97%
- **Epoch 5:** Training loss = 0.116 | Validation loss = 0.047 | Top-1 Acc = 98.5%

## 📈 Validation Results (Average Confidence)

| Plant Class | Avg. Confidence |
|-------------|-----------------|
| Bell Pepper | 97.1% |
| Coconut Tree | 99.9% |
| Sunflower | 100% |
| Mango Tree | 96.7% |
| Basil | 97.75% |
| Rice Plant | 95.5% |
| Common White Rose | 99.7% |
| Tomato | 96.85% |
| Wheat Plant | 89% |
| Maize (Corn) | 99.1% |

Detailed results for each class are available in the `Validation result images/` folder.

## ⚙️ Model Weights

After training, the following weight files are saved:
```text
runs/classify/train/weights/
├── best.pt # Best-performing model
└── last.pt # Latest checkpoint (for resuming training)
```
Inference Example
```text
python
from ultralytics import YOLO
model = YOLO('path/to/best.pt')
results = model('path/to/test_image.jpg')
results[0].show()
```
Resume Training
```text
python
from ultralytics import YOLO
model = YOLO('path/to/last.pt')
results = model.train(data='path/to/dataset', epochs=5, imgsz=416)
```
✅ Conclusion
The Plants Classification Model demonstrates strong performance with 97.2% Top-1 accuracy and 100% Top-5 accuracy. It generalizes well to unseen validation images and can be used reliably for automated plant identification.
Future improvements can be made by expanding the dataset and resuming training with last.pt.
