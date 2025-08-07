# 🩻 COVID-19 Chest X-ray Classification using Deep Learning

This project uses advanced deep learning architectures — including **CNN+LSTM**, **Dual-Channel CNN**, and **ResNet** — to classify chest X-ray images into four categories:
- **COVID-19**
- **Normal**
- **Lung Opacity**
- **Viral Pneumonia**

It leverages both raw X-ray images and **segmentation masks** for improved performance and accuracy.

---

## 📦 Dataset

📍 **Source**: [COVID-19 Radiography Database (Kaggle)](https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database)

After extraction, the dataset folder looks like:

<pre>
COVID-19_Radiography_Dataset/
│
├── COVID/
│   ├── images/
│   └── masks/
│
├── Lung_Opacity/
│   ├── images/
│   └── masks/
│
├── Normal/
│   ├── images/
│   └── masks/
│
├── Viral Pneumonia/
│   ├── images/
│   └── masks/
│
├── COVID.metadata.xlsx
├── Lung_Opacity.metadata.xlsx
├── Normal.metadata.xlsx
├── Viral Pneumonia.metadata.xlsx
└── README.md.txt
</pre>

Each class folder contains:
- `images/`: Raw X-ray images
- `masks/`: Binary masks showing segmented lung regions (used in dual-channel model)

---

## 🧠 Model Architectures

This project compares three distinct deep learning strategies:

### 1. 🧪 CNN + LSTM (Single-Channel)
- Input: Grayscale images
- CNN extracts spatial features
- LSTM captures temporal-like dependencies
- Suitable for capturing structural flow in lung imagery

### 2. 🧪 Dual-Channel CNN (Image + Mask)
- Input: 2-channel data (X-ray image + segmentation mask)
- Channels are concatenated and passed through a custom CNN
- Improves anatomical sensitivity using spatial mask guidance

### 3. 🧪 ResNet (Transfer Learning)
- Uses pretrained **ResNet** (e.g., ResNet50) as feature extractor
- Fine-tuned on the X-ray dataset
- Achieves highest accuracy among all models

---

## 📁 Project Structure

<pre>
COVID19-Chest-Xray-Classifier/
│
├── chest.ipynb              # Main Jupyter notebook
├── requirements.txt         # Required packages
├── LICENSE                  # MIT License
└── README.md                # You're reading this
</pre>

---

## 🚀 How to Run

### ✅ Step 1: Download & Organize Dataset
Download from Kaggle and extract so your structure looks like:

COVID-19_Radiography_Dataset/
    ├── COVID/images, masks/
    ├── Lung_Opacity/images, masks/
...

### ✅ Step 2: Install Requirements
pip install -r requirements.txt

### ✅ Step 3: Run the Notebook
jupyter notebook chest.ipynb

📈 Evaluation
Loss and accuracy plots for each model
For CNN Model<img width="1246" height="486" alt="image" src="https://github.com/user-attachments/assets/eb034cf1-53d7-4401-9c60-c14e491ffb15" />


Confusion matrices
For CNN+LSTM<img width="889" height="632" alt="image" src="https://github.com/user-attachments/assets/061f397b-f27b-413a-a0f8-1687d83a6128" />


Class-wise precision, recall, F1-score
For RESNET<img width="660" height="281" alt="image" src="https://github.com/user-attachments/assets/2d5619a7-4266-4b7b-8398-ab807b335b3e" />



⚠️ GPU Recommended
For faster training, use:

NVIDIA Tesla T4 / P100 / V100

CUDA 11.2+ environment

📜 License
This project is open-sourced under the MIT License.

👨‍💻 Author
Mahin Alam
Built using deep learning and real-world diagnostic challenges.

