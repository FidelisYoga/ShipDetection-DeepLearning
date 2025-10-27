# 🚢 Ship Detection using Deep Learning

This project focuses on **detecting ships in aerial and satellite images** using **YOLO architectures (YOLOv8s, YOLOv8m, YOLOv11)**.  
It covers the full deep learning workflow from **data preprocessing** and **exploratory data analysis (EDA)** to **model training**, **evaluation**, and **performance comparison** across multiple YOLO variants.

---

## Overview
The main objective of this project is to develop a robust deep learning model capable of detecting ships from aerial imagery, which can be applied to real-world use cases such as **maritime surveillance**, **coastal monitoring**, and **port traffic analysis**.

---

## Dataset
The dataset contains **26.9k annotated aerial images** of ships with YOLO-formatted bounding boxes.

**Dataset split:**
- Train: 72.18%  
- Validation: 16.11%  
- Test: 11.71%  

**Key details:**
- Single class: `ship`  
- Images sourced from satellite and aerial data  
- Bounding boxes vary widely in size and aspect ratio  

---

## Exploratory Data Analysis (EDA)
Performed detailed data exploration to understand image and annotation patterns:
- Visualized random samples with bounding boxes  
- Checked image dimensions, formats, and file consistency  
- Analyzed bounding box width, height, and aspect ratios  
- Counted number of ships per image  

**Insights:**
- Most images contain only 1–2 ships  
- Bounding box dimensions are highly varied, requiring normalization  
- Some extremely small boxes (<2 px) were removed during cleaning  

---

## Data Preprocessing
- Resized all images to **512×512** pixels for training consistency  
- Removed invalid or extremely small bounding boxes  
- Normalized coordinates to YOLO format  
- Ensured aspect ratio 1:1 for uniform input  
- Limited to a maximum of 50 bounding boxes per image  

---

## Model Training
Trained and compared 3 YOLO variants:
- **YOLOv8s:** lightweight and fast, suitable for real-time inference  
- **YOLOv8m:** balanced model between speed and accuracy  
- **YOLOv11:** latest version achieving highest accuracy, but heavier computationally  

Training and validation were performed using GPU acceleration for efficient model convergence.

---

## Evaluation & Results
Evaluation metrics:
- **Precision**, **Recall**, **mAP50**, **mAP50-95**, and **Inference Time**

**Summary:**
- YOLOv11 achieved **highest detection accuracy**, ideal for precision-critical tasks  
- YOLOv8s provided **fastest inference**, suitable for real-time deployment  
- YOLOv8m offered a **balanced trade-off** between accuracy and speed  

---

## Tech Stack
- Python  
- PyTorch  
- Ultralytics YOLO  
- OpenCV, NumPy, Pandas  
- Matplotlib, Seaborn  

---
