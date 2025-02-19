# 🏥 Retinal Vessel Segmentation using U-Net in TensorFlow

This project implements **Retinal Vessel Segmentation** using the **U-Net architecture** in TensorFlow. It is designed to detect and segment blood vessels from retinal images, aiding in the diagnosis of diseases like **diabetic retinopathy** and **hypertension**.

## 📌 Dataset
The model is trained on the **DRIVE dataset**:
- [Download the dataset](https://www.kaggle.com/datasets/zionfuo/drive2004)
- The dataset consists of **40 retinal images** (20 training + 20 testing) along with **manual annotations**.

## 📁 Project Structure
📂 Retinal-Vessel-Segmentation/ │
── 📜 data.py # Loads and augments the dataset │
── 📜 model.py # Defines the U-Net model 
│── 📜 train.py # Training script │
── 📜 eval.py # Model evaluation & metrics calculation │
── 📜 metrics.py # Custom metrics (IoU, Dice Coefficient) │
── 📜 README.md # Project documentation │
── 📜 requirements.txt # Python dependencies │
── 📂 new_data/ # Processed images and masks │
── 📂 results/ # Model predictions and results
