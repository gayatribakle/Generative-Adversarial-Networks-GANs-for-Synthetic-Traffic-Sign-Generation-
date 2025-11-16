# Generative-Adversarial-Networks-GANs-for-Synthetic-Traffic-Sign-Generation-
This project uses GANs to generate realistic synthetic traffic sign images from the Belgium Traffic Sign dataset. The synthetic data augments real images to improve autonomous driving model accuracy. Evaluation includes FID score for image quality and classifier performance comparison with and without synthetic data.

## Project Overview

Real-world traffic sign datasets often suffer from limitations such as:

Class imbalance

Insufficient samples

High data collection cost

To address this, this project uses a DCGAN-based generator–discriminator setup to produce high-quality synthetic traffic sign images.

## Dataset

Belgium Traffic Sign Dataset
Contains real-world traffic sign images captured under varying conditions.
Download link: (as per dataset source)

#### Folder structure after extraction:
```
belgium_traffic_signs/
    ├── Training/
    ├── Testing/
    └── Annotations/
```

#### Features Implemented

- Unzipping and preprocessing dataset
- DCGAN architecture (Generator + Discriminator)
- GAN training pipeline
- Image generation & visualization
- FID score evaluation
- CNN classifier training
- Performance comparison (Real vs Real+Synthetic)

#### Model Architecture
Generator

-Dense + Reshape

-Conv2DTranspose layers

-BatchNorm + ReLU

- Output: 64×64×3 image (tanh)

Discriminator

-Conv2D layers

-LeakyReLU

-Dropout

-Output: Real/Fake prediction

## 📊 Evaluation
1. FID Score

-Measures similarity between real and generated image distributions.

-Lower FID → better quality & diversity.

2. Classifier Performance

-A CNN is trained on:

-Real data only

-Real + GAN-generated synthetic data

-This helps determine whether synthetic data improves accuracy.
```
📁 Project Structure
├── data/                         # Dataset folder
├── models/                       # Generator/Discriminator saved models
├── outputs/                      # Generated images
├── fid/                          # FID score results
├── classifier/                   # CNN classifier results
└── GAN_Traffic_Signs.ipynb       # Full Jupyter Notebook
```
## 🛠 Technologies Used

Python

TensorFlow / Keras

TensorFlow Hub

TensorFlow-GAN

NumPy

Matplotlib

Belgium Traffic Sign Dataset

## ▶️ How to Run

Clone the repo:
```
git clone https://github.com/yourusername/traffic-sign-gan.git
```

Install dependencies:
```
pip install -r requirements.txt
```

Run the Jupyter Notebook:
```
jupyter notebook GAN_Traffic_Signs.ipynb
```
## 📌 Future Enhancements

Conditional GAN (cGAN) for label-specific generation

StyleGAN/StyleGAN-lite for higher-quality images

Diffusion models for advanced augmentation

Integration with object detection datasets
