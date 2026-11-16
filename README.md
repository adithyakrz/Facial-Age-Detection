# Facial Age & Skin Concern Detection

**AI-Facial-Aging-Detection-App** is a lightweight computer vision and deep learning project that detects **facial skin concerns associated with aging** from images.
It integrates **face detection**, **transfer learning–based image classification**, and an optional **Streamlit web interface** for interactive inference, visualization, and result export.

---

## Project Overview

* **Objective:**
  Automatically classify facial images into common skin concern categories related to aging.

* **Skin Concern Classes:**

  * `clear skin`
  * `dark spots`
  * `puffy eyes`
  * `wrinkles`

* **Core Techniques:**

  * Face detection using **OpenCV Haar Cascades**
  * Image classification using **TensorFlow / Keras**
  * Transfer learning with **ResNet**
  * Dataset splitting into `train`, `validation`, and `test`
  * Optional **Streamlit-based UI** for inference, logging, and export

---

## Repository Structure

```text
├── app.py                         
├── dataset/                       
│   ├── clear skin/
│   ├── dark spots/
│   ├── puffy eyes/
│   └── wrinkles/
├── splittedset/                   
│   ├── train/
│   ├── validation/
│   └── test/
├── models/                        
│   ├── resnet_best_model.h5
│   ├── mobilenetv2_best_model.h5
│   ├── efficientnetb2_best_model.h5
│   └── efficientnetb0_best_model.h5
├── notebooks/
│   └── preprocessandtrain.ipynb   
├── scripts/
│   ├── facedetection.py           
│   └── haarcascade_frontalface_default.xml
├── documentation/                 
├── requirements.txt               
├── LICENSE
└── README.md
```

---

## System Requirements

* **Python:** 3.9 or higher (recommended: 3.9–3.12)
* **Git** (for cloning the repository)
* **pip** (Python package manager)

Verify installation:

```bash
python --version
git --version
pip --version
```

---

## Step-by-Step Setup Guide

### Step 1: Clone the Repository

```bash
git clone https://github.com/adithyakrz/Facial-Age-Detection
cd <PROJECT_FOLDER_NAME>
```

---

### Step 2: Create a Virtual Environment

Using a virtual environment avoids dependency conflicts.

#### ▶ Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### ▶ macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

Once activated, `(venv)` should appear in your terminal.

---

### Step 3: Install Dependencies

Install all required libraries:

```bash
pip install -r requirements.txt
```

### Main Dependencies

* TensorFlow / Keras
* OpenCV (`opencv-python`)
* NumPy, Pandas
* Matplotlib
* Scikit-learn
* Streamlit

> TensorFlow installation may take a few minutes.

---

## Model Setup

Ensure at least one trained model is present in the **models/** directory.

Example:

```text
models/
 └── resnet_best_model.h5
```

If no model is available, refer to the **Training Pipeline** section below to train one.

---

## ▶ Running Inference / Demo

### Option 1: Streamlit Web Interface (Recommended)

Run the following command:

```bash
streamlit run app.py
```

* A local URL (usually `http://localhost:8501`) will open automatically
* Upload a facial image
* View detected face and predicted skin concern

---

### Demo Features

* Upload facial images
* Automatic face detection
* Skin concern classification
* Estimated age display (if enabled)
* Confidence score per prediction
* Download annotated images
* Export prediction logs as CSV

---

## Training Pipeline

The notebook **`notebooks/preprocessandtrain.ipynb`** contains the full training workflow:

* Image loading and preprocessing (resize, normalization)
* Dataset splitting (train / validation / test)
* Data augmentation for improved generalization
* Transfer learning using pre-trained CNN backbones
* Training with early stopping and model checkpointing
* Evaluation on the test set
* Saving best-performing models to `models/`

To train a model:

1. Open the notebook
2. Run all cells sequentially or run the section of desired model
3. Best model will be saved automatically

---

## Evaluation & Results

* Training and validation performance visualized using accuracy and loss curves
* Evaluated architectures:

  * ResNet
  * MobileNetV2
  * EfficientNetB2
  * EfficientNetB0
* Best-performing models are stored in the `models/` directory

Results are fully reproducible by running the training notebook.

### ResNet50 Confusion Matrix

The matrix shows the true labels on the vertical axis and the predicted labels on the horizontal axis.

![ResNet50 confusion matrix](images/Screenshot%202026-11-16%20204226.png)

---

## Notes & Possible Improvements

* Dataset follows a **folder-per-class** structure compatible with Keras utilities
* Potential enhancements:

  * Landmark-based face alignment
  * Separate and more accurate age estimation model
  * Class imbalance handling
  * Larger and more diverse datasets
  * Model quantization and optimization for faster inference

---


## 📄 License

This project is distributed under the terms specified in the **LICENSE** file.

---

