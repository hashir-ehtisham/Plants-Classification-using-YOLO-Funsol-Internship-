# Plants Classification Model

## 1. Overview
[cite_start]The **Plants Classification Model** is a deep learning-based image classifier trained to identify 10 different plant species[cite: 257]. [cite_start]It is implemented using the **YOLO11n-cls.pt** model variant[cite: 258]. [cite_start]This model is designed for agricultural, research, and educational applications, assisting in automated plant recognition[cite: 261].

## 2. Supported Plant Classes
[cite_start]The model can classify the following 10 species[cite: 264]:
* [cite_start]**Triticum Aestivum** – Wheat Plant [cite: 265]
* [cite_start]**Oryza Sativa** – Rice Plant [cite: 266]
* [cite_start]**Zea mays** – Maize (Corn) [cite: 267]
* [cite_start]**Capsicum Annuum** – Bell Pepper Plant [cite: 268]
* [cite_start]**Solanum lycopersicum** – Tomato Plant [cite: 269]
* [cite_start]**Ocimum basilicum** – Basil Plant [cite: 270]
* [cite_start]**Rosa indica** – Common White Rose [cite: 271]
* [cite_start]**Cocos Nucifera** – Coconut Tree [cite: 272]
* [cite_start]**Mangifera indica** – Mango Tree [cite: 273]
* [cite_start]**Helianthus Annuus** – Sunflower Plant [cite: 274]

## 3. Dataset Structure
[cite_start]The dataset is organized into `train/` and `val/` folders, with subfolders for each class[cite: 276].
* [cite_start]**Training Images**: 200 images per class (2,000 total)[cite: 285, 286].
* [cite_start]**Validation Images**: 20 images per class (200 total)[cite: 295, 296].

```text
/Plants/
├── train/
│   ├── Capsicum Annuum - Bell Pepper Plant/
│   ├── ... (other plant classes)
└── val/
    ├── Capsicum Annuum - Bell Pepper Plant/
    └── ... (other plant classes)
