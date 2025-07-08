# Image-painting-using-Gan-and-Unet
We built an image inpainting system for high-resolution images using a hybrid deep learning model—U-Net as the generator for structure and GAN as the discriminator for texture realism. A web app was also developed, enabling users to upload damaged images and receive real-time restorations, useful for old photo recovery and image repair.


## 🛠️ Development Environment

* Platform: **Google Colab**
* Language: **Python**
* Framework: **PyTorch**
* Web Deployment: **Flask** + **Ngrok**
* Data storage and checkpoints: **Google Drive**

---

## 📂 Dataset
We used the **CelebA-HQ (256×256 resolution)** dataset, downloaded via **KaggleHub** in Google Colab. 
This dataset includes high-quality human face images, ideal for training image inpainting models.
---

## 🧠 Model Architecture

* **Generator**: U-Net based architecture to reconstruct missing regions.
* **Discriminator**: CNN-based model with **Spectral Normalization** to help generate realistic textures.
* Loss Functions used:

  * **Adversarial Loss (BCELoss)**
  * **Pixel-wise L1 Loss**
  * **Gradient Penalty** for GAN stability.

---

## 🚀 Training Details

* **Environment**: Google Colab with GPU support.
* **Custom Dataset Loader**: Applies **random square masks** on images to simulate missing areas during training.
* **Training Strategy**:

  * Generator learns to fill gaps.
  * Discriminator learns to differentiate between real and generated images.
  * Both models trained together using **GAN training loop**.
* **Output Checkpoints** and **Generated Results** saved in Google Drive.

---

## 🌐 Web Application Deployment

We integrated the trained model into a **Flask-based web application**.
Using **Ngrok**, we exposed the app to the internet from Google Colab, allowing users to:

* Upload broken images.
* Get real-time inpainted results.

#### 📸 Web App Homepage:
![](webinterface.jpg)

#### 📸 Image Upload Section:
![](inputinterface.jpg)

#### 📸 Sample Inpainting Result:
![](outputinterface.jpg)

---

## 📈 Performance Comparison

We compared our model's performance with existing inpainting techniques to check **visual quality** and **realism** on different image types.

---

## 🎯 Applications

* Damaged image repair.
