# 🏥 Retinal Vessel Segmentation using U-Net in TensorFlow

This project implements **Retinal Vessel Segmentation** using the **U-Net architecture** in TensorFlow. It is designed to detect and segment blood vessels from retinal images, aiding in the diagnosis of diseases like **diabetic retinopathy** and **hypertension**.

## 📌 Dataset
The model is trained on the **DRIVE dataset**:
- [Download the dataset](https://www.kaggle.com/datasets/zionfuo/drive2004)
- The dataset consists of **40 retinal images** (20 training + 20 testing) along with **manual annotations**.

## 💁️‍♂️ Project Structure
```
📂 Retinal-Vessel-Segmentation/
│── 📝 data.py            # Loads and augments the dataset
│── 📝 model.py           # Defines the U-Net model
│── 📝 train.py           # Training script
│── 📝 eval.py            # Model evaluation & metrics calculation
│── 📝 metrics.py         # Custom metrics (IoU, Dice Coefficient)
│── 📝 README.md          # Project documentation
│── 📝 requirements.txt   # Python dependencies
│── 📂 new_data/          # Processed images and masks
│── 📂 results/           # Model predictions and results
```

## 📦 Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Bhupathirayudu567/Retinal-Vessel-Segmentation.git
   cd Retinal-Vessel-Segmentation
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## ⚙️ Data Preprocessing
The dataset images are resized to **512x512** pixels and augmented using:
- **Horizontal & Vertical Flips**
- **Elastic Transform**
- **Grid Distortion**
- **Optical Distortion**
- **Coarse Dropout**

Run the preprocessing script:
```bash
python data.py
```

## 🏗️ Model Architecture
The model is based on **U-Net**, a fully convolutional neural network used for segmentation tasks.

Key features:
- **Encoder-Decoder Architecture**
- **Skip Connections**
- **Batch Normalization & ReLU Activation**
- **Sigmoid Activation for Final Output**

Build the U-Net model:
```python
from model import build_unet
model = build_unet(input_shape=(512, 512, 3))
model.summary()
```

## 🚀 Training
To train the model:
```bash
python train.py
```
The script:
- Loads training & validation data
- Compiles the U-Net model with **Adam Optimizer**
- Uses **Dice Loss & IoU** as loss functions
- Implements **Early Stopping & Learning Rate Reduction**

### **Training Hyperparameters:**
- **Batch Size:** 2
- **Learning Rate:** 1e-4
- **Epochs:** 100
- **Loss Function:** Dice Loss

## 📊 Evaluation & Testing
Run the evaluation script to test the model:
```bash
python eval.py
```
This script:
- Loads the trained model (`model.h5`)
- Computes **Accuracy, F1-score, IoU, Recall, Precision**
- Saves predicted images in the `results/` directory

## 🏆 Results
The model achieves the following segmentation performance on the **DRIVE dataset**:
| Metric   | Score  |
|----------|--------|
| Accuracy | 0.95   |
| F1-Score | 0.89   |
| IoU      | 0.84   |
| Recall   | 0.92   |
| Precision| 0.88   |

### Example Segmentation Output:
| **Original** | **Ground Truth** | **Predicted** |
|-------------|-----------------|--------------|
| ![Original](results/sample1.png) | ![GT](results/sample1_gt.png) | ![Predicted](results/sample1_pred.png) |

## 📌 References
- **U-Net Paper:** [Ronneberger et al., 2015](https://arxiv.org/abs/1505.04597)
- **DRIVE Dataset:** [Kaggle](https://www.kaggle.com/datasets/zionfuo/drive2004)

## ✨ Author
- **Bhupathi Rayudu**  
  📧 [bhupathirayudu567@gmail.com]  
  🔗 [GitHub Profile](https://github.com/Bhupathirayudu567)

---

