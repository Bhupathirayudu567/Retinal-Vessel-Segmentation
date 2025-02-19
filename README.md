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

## 📦 Installation
1. Clone the repository:
   git clone https://github.com/Bhupathirayudu567/Retinal-Vessel-Segmentation.git
   cd Retinal-Vessel-Segmentation
2.Install dependencies:
   pip install -r requirements.txt
   
## ⚙️ Data Preprocessing
The dataset images are resized to 512x512 pixels and augmented using:

Horizontal & Vertical Flips
Elastic Transform
Grid Distortion
Optical Distortion
Coarse Dropout
Run the preprocessing script:
  python data.py

## 🏗️ Model Architecture
The model is based on U-Net, a fully convolutional neural network used for segmentation tasks.

Key features:

Encoder-Decoder Architecture
Skip Connections
Batch Normalization & ReLU Activation
Sigmoid Activation for Final Output
Build the U-Net model:
  from model import build_unet
  model = build_unet(input_shape=(512, 512, 3))
  model.summary()

