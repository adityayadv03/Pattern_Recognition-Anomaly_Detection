# Anomaly Detection in MNIST Dataset using Autoencoders

This project demonstrates how to use a Convolutional Autoencoder for detecting anomalies in the MNIST dataset. The MNIST dataset consists of handwritten digits from 0 to 9.

## 🧑‍🤝‍🧑 Team

- **Aditya Yadav** - 500107292 - [adityayadv03](https://github.com/adityayadv03)
- **Harshdeep Shakya** - 500107422 - [HDS07](https://github.com/HDS07)
- **Vinayak Singh** - 500109572 - [vinayak820](https://github.com/Vinayak820)

---

## 🛠 Work Contribution

- **Pattern Recognition:** Vinayak Singh
- **Anomaly Detection:** Aditya Yadav , Harshdeep Shakya

---

# Model Descriptions

## 🔹 1. Pattern Recognition using CNN

A custom Convolutional Neural Network (CNN) architecture is used for digit classification. The architecture consists of:

- **3 Convolutional Layers**
- **3 Max Pooling Layers**
- **2 Fully Connected Layers**
- **Final Dense Layer** with 10 units (for digits 0–9)

This model learns to recognize and classify handwritten digits in grayscale MNIST images (28×28).

---

## 🔹 2. Anomaly Detection using Autoencoder

We use a deep autoencoder to detect abnormal (synthetic) images that differ from real handwritten digits.

### 🛠 How anomalies are created:
We modify test images using:

- **Gaussian Noise:** Add pixel-level noise.
- **Rotation:** Rotate digits randomly (±30°).
- **Noise + Rotation:** Apply both types of distortion.

We sample clean and distorted images to build a combined test set containing both normal and anomalous examples.

### 🚦 Anomaly Detection Logic:
- The autoencoder is trained only on clean (normal) MNIST digits.
- When tested on the combined set:
  - Images are reconstructed.
  - We calculate the Mean Squared Error (MSE) between the input and reconstructed image.
  - A threshold (e.g., 95th percentile of clean MSEs) is set.
  - If an image has MSE > threshold → **Anomaly**
  - Else → **Normal**

---

## 📊 Evaluation

The system reports classification metrics and a confusion matrix for anomaly detection.

A **visualization section** shows the most anomalous samples along with their reconstructions.

---

## 📎 Dataset

- **MNIST Handwritten Digits**

---
