# FLOODNET-Track-1-Semi-supervised-Classification-and-Semantic-Segmentation-

This repository contains a complete pipeline for **semi-supervised image classification** on the FloodNet dataset, developed for Track 1 of the FloodNet Challenge. The main goal is to classify images into **flooded** and **non-flooded** categories using both **labeled** and **unlabeled** data. The project leverages **ResNet50**, data augmentation, and class rebalancing to enhance model performance.


## 📌 Project Steps

### 1.  Data Exploration

- Display and visualize flooded and non-flooded images along with their masks.
- Visualize unlabeled images for general inspection.

### 2.  Preprocessing

- **Resizing** all images to 224x224 pixels.
- **Normalization** of pixel values (0 to 1 range).
- **Data Augmentation** to improve model generalization.
- **Splitting** the dataset into training, validation, and testing sets.

### 3.  Model Selection & Training

- Used **ResNet50** (pre-trained on ImageNet) as the backbone.
- Fine-tuned with a custom classifier (GAP → Dense → Dropout → Dense).
- **Data generators** were created for both labeled and unlabeled datasets.
- Implemented two training settings:
  - **Basic Semi-supervised Learning**
  - **Enhanced Semi-supervised Learning** with:
    - Data augmentation
    - Class weighting to handle imbalance

### 4.  Inference on Unlabeled Data

- Predicted labels for 3,312 unlabeled images.
- Classified them into:
  - Flooded: 500 images
  - Non-Flooded: 2,812 images
- Saved the classified images into separate folders.

##  Results Summary

| Metric                  | Basic ResNet50 | With Class Weights + Augmentation |
|------------------------|----------------|-----------------------------------|
| Validation Accuracy     | ~89.7%         | ~87.6%                            |
| Validation Loss         | 0.30           | 0.33                              |
| IoU (placeholder)       | 0.25           | 0.25                              |
| Flooded Predicted       | 0              | 500                               |
| Non-Flooded Predicted   | 3,312          | 2,812                             |


##  Tools and Libraries

- Python, TensorFlow/Keras
- PIL, OpenCV, Matplotlib
- Google Colab, Google Drive
- Pandas, NumPy


## 🚀 How to Run

1. Upload the FloodNet dataset to your Google Drive.
2. Run the notebook in Google Colab.
3. Make sure to mount Google Drive before execution.
4. The code will automatically preprocess, train, and classify unlabeled images.


This project is for educational and research purposes .

---

**Floods are devastating — AI can help make early responses smarter.**





