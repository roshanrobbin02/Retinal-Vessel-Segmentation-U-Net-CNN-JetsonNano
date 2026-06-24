# Retinal Blood Vessel Segmentation and Disease Prediction using Deep Learning on NVIDIA Jetson Nano

## Abstract

Retinal diseases such as Diabetic Retinopathy and Glaucoma are among the major causes of visual impairment and blindness worldwide. Early diagnosis and timely treatment are crucial for preventing permanent vision loss. Manual examination of retinal fundus images is time-consuming and highly dependent on clinical expertise. Therefore, automated retinal image analysis systems have become an important area of research in medical image processing and artificial intelligence.

This project presents an intelligent retinal image analysis system that performs retinal blood vessel segmentation and retinal disease prediction using deep learning techniques. A U-Net architecture is employed for accurate extraction of retinal vascular structures, while a Convolutional Neural Network (CNN) is used for disease classification. The developed system is deployed on an NVIDIA Jetson Nano platform to enable real-time edge AI inference, making it suitable for portable healthcare applications.

The proposed framework was trained and evaluated using benchmark retinal datasets obtained from Kaggle, namely DRIVE and FIVES, along with a real-time hospital-collected dataset named R4V2025. Experimental results demonstrate the effectiveness of the proposed system in accurately segmenting retinal vessels and classifying retinal diseases.

---

# Introduction

Retinal blood vessels provide critical information regarding the health condition of the human eye. Abnormalities in retinal vascular structures often indicate diseases such as Diabetic Retinopathy, Glaucoma, Hypertensive Retinopathy, and other ocular disorders.

Traditional diagnosis methods rely heavily on ophthalmologists, requiring significant time and expertise. With advancements in Artificial Intelligence, Deep Learning, and Embedded Systems, automated retinal image analysis has emerged as a promising solution for supporting medical professionals.

This project integrates Medical Image Processing, Deep Learning, and Edge Computing to develop an automated retinal disease screening system capable of operating on resource-constrained embedded hardware.

---

# Problem Statement

Manual retinal disease diagnosis suffers from several challenges:

* Time-consuming examination procedures
* Dependence on expert ophthalmologists
* Limited accessibility in rural healthcare facilities
* Human errors during diagnosis
* High cost of specialized diagnostic equipment

To address these limitations, an automated and portable retinal image analysis system is required for early disease detection and screening.

---

# Objectives

The primary objectives of this project are:

* To segment retinal blood vessels from retinal fundus images using U-Net.
* To classify retinal diseases using a CNN model.
* To evaluate the system using both benchmark and real-world datasets.
* To deploy the trained models on NVIDIA Jetson Nano.
* To develop a low-cost Edge AI healthcare solution for retinal disease screening.

---

# System Architecture

![System Block Diagram](images/architecture/system_block_diagram.jpg)

## Workflow

```text
Retinal Fundus Image
          ↓
Image Preprocessing
          ↓
U-Net Segmentation
          ↓
Retinal Blood Vessel Extraction
          ↓
CNN Classification
          ↓
Disease Prediction
          ↓
Jetson Nano Deployment
```

The system follows a two-stage deep learning pipeline. The first stage extracts retinal blood vessels using U-Net segmentation, while the second stage performs disease classification using a CNN model.

---

# Datasets Used

The project utilizes both public benchmark datasets and real-world hospital-collected data.

## 1. DRIVE Dataset (Kaggle)

The Digital Retinal Images for Vessel Extraction (DRIVE) dataset is one of the most widely used benchmark datasets for retinal vessel segmentation.

### Purpose

* U-Net training
* Vessel segmentation evaluation
* Model validation

### Features

* Retinal fundus images
* Ground truth vessel masks
* Expert annotations

---

## 2. FIVES Dataset (Kaggle)

The Fundus Image Vessel Segmentation (FIVES) dataset was used for disease prediction and classification.

### Purpose

* CNN training
* Disease classification
* Performance evaluation

### Disease Classes

* Normal
* Diabetic Retinopathy
* Glaucoma

---

## 3. R4V2025 Dataset (Hospital-Collected)

R4V2025 is a real-time retinal image dataset collected from a collaborating hospital as part of this project.

### Purpose

* Real-world validation
* Clinical testing
* Model generalization evaluation

### Significance

The use of hospital-collected retinal images improves the practical reliability of the system by evaluating performance beyond benchmark datasets.

---

# Dataset Comparison

![Dataset Comparison](images/results/dataset_comparison.png)

| Dataset | Source             | Purpose                |
| ------- | ------------------ | ---------------------- |
| DRIVE   | Kaggle             | Vessel Segmentation    |
| FIVES   | Kaggle             | Disease Classification |
| R4V2025 | Hospital-Collected | Clinical Validation    |

---

# Image Preprocessing

Before training, retinal images undergo preprocessing to improve model performance.

### Preprocessing Steps

* Image Resizing
* Grayscale Conversion
* Normalization
* Contrast Enhancement
* Label Encoding
* Data Augmentation

The preprocessing stage ensures uniform image quality and improves feature extraction.

---

# Retinal Blood Vessel Segmentation using U-Net

## U-Net Architecture

![U-Net Architecture](images/architecture/unet_architecture.png)

U-Net is a fully convolutional neural network specifically designed for biomedical image segmentation.

### Encoder Path

* Convolution Layers
* ReLU Activation
* Max Pooling

### Bottleneck

* Deep Feature Learning

### Decoder Path

* Up-Sampling Layers
* Skip Connections
* Feature Reconstruction

### Output

* Binary Vessel Segmentation Mask

The skip connections preserve spatial information and significantly improve segmentation accuracy.

---

# Disease Prediction using CNN

After vessel segmentation, the extracted retinal features are provided to a CNN model for disease classification.

## CNN Components

* Convolution Layers
* Activation Layers
* Pooling Layers
* Fully Connected Layers
* Softmax Output Layer

## Predicted Classes

| Class | Disease              |
| ----- | -------------------- |
| 0     | Normal               |
| 1     | Diabetic Retinopathy |
| 2     | Glaucoma             |

---

# Hardware Implementation

![Jetson Nano Setup](images/hardware/jetson_nano_hardware_setup.jpg)

## Hardware Platform

The trained deep learning models were deployed on NVIDIA Jetson Nano to enable edge AI-based retinal diagnosis.

### Specifications

| Component | Description        |
| --------- | ------------------ |
| Processor | ARM Cortex-A57     |
| GPU       | 128-Core Maxwell   |
| RAM       | 4 GB               |
| Platform  | NVIDIA Jetson Nano |

### Advantages

* Low Power Consumption
* Real-Time Inference
* Portable Deployment
* Cost-Effective Healthcare Solution

---

# Experimental Results

## Diabetic Retinopathy Prediction

![Diabetic Retinopathy Prediction](images/results/diabetic_retinopathy_prediction.png)

The CNN model successfully identifies retinal abnormalities associated with Diabetic Retinopathy.

---

## Glaucoma Prediction

![Glaucoma Prediction](images/results/glaucoma_prediction.png)

The system accurately classifies Glaucoma cases using retinal image features.

---

# Performance Evaluation

## Evaluation Metrics

![Evaluation Metrics](images/results/evaluation_metrics.png)

## Confusion Matrix

![Confusion Matrix](images/results/confusion_matrix.png)

### Metrics Used

* Accuracy
* Precision
* Recall
* F1 Score
* Dice Coefficient
* IoU

The obtained results demonstrate strong performance in both segmentation and disease classification tasks.

---

# Repository Structure

```text
Retinal-Vessel-Segmentation-U-Net-CNN-JetsonNano/
│
├── README.md
├── requirements.txt
│
├── images/
│   ├── architecture/
│   │   ├── system_block_diagram.jpg
│   │   └── unet_architecture.png
│   │
│   ├── hardware/
│   │   └── jetson_nano_hardware_setup.jpg
│   │
│   └── results/
│       ├── diabetic_retinopathy_prediction.png
│       ├── glaucoma_prediction.png
│       ├── confusion_matrix.png
│       ├── evaluation_metrics.png
│       └── dataset_comparison.png
│
├── code/
│   └── source_code.py
```

---

# Applications

* Automated Retinal Screening
* Diabetic Retinopathy Detection
* Glaucoma Detection
* Clinical Decision Support Systems
* Telemedicine
* AI-Based Healthcare Solutions

---

# Future Scope

* Real-Time Camera Integration
* Mobile Application Development
* Explainable AI (XAI)
* Multi-Disease Classification
* Cloud-Based Healthcare Platform
* Large-Scale Clinical Deployment

---

# Technologies Used

* Python
* TensorFlow
* Keras
* OpenCV
* NumPy
* Scikit-Learn
* NVIDIA Jetson Nano
* Deep Learning
* Computer Vision

---

# Author

**Roshan Robbin**


---

# Acknowledgements

* DRIVE Dataset
* FIVES Dataset
* NVIDIA Jetson Nano Developer Community
* TensorFlow and Keras Communities
* Hospital collaborators for providing the R4V2025 retinal image dataset

