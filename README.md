# Sketch-AI: Mimicking Hand-Drawn Sketches with GAN

In **Sketch-AI**, we aim to mimic hand-drawn sketches using a Generative Adversarial Network (GAN) model. By leveraging image quantization and advanced GAN architecture, we achieve high-quality, sketch-like representations of input images. 

## Project Overview

### Objectives
- **Image Quantization**: Reduce the number of colors in an image to closely resemble human perception of colors by employing K-means clustering.
- **Color Model**: Use an extended color model, **RGBY (Gauche color)**, which incorporates an additional yellow channel for more accurate human-like color representation compared to the traditional RGB model.
- **GAN Training**: Train a **pix2pix GAN** model on both normal and quantized images to generate hand-drawn-style sketches from regular images. The model trained on quantized images produced superior results compared to training with standard images.

## Key Components

### 1. **Image Quantization**
We performed color quantization on input images using **K-means clustering**. The clustering technique reduces the color space to a manageable number of clusters (k). This step simplifies the color distribution, making it easier for the GAN model to mimic hand-drawn sketch lines. 

To improve accuracy and better match human perception, we use the **RGBY** color model:
- **R** (Red)
- **G** (Green)
- **B** (Blue)
- **Y** (Yellow): Formed as an average of the red and green channels.

This additional **yellow** channel helps to capture more subtle color variations often missed by traditional RGB models.

### 2. **GAN Architecture (pix2pix)**
We used the **pix2pix architecture**, a conditional GAN model, for sketch generation. The network consists of two parts:
- **Generator**: Attempts to create a sketch-like image from the input image.
- **Discriminator**: Tries to distinguish between real hand-drawn sketches and the generated images.

We trained the model in two configurations:
- **On regular images**: The GAN was trained on normal, unmodified input images.
- **On quantized images**: We also trained the GAN on images after quantization, finding that this approach produced more realistic sketches.

### 3. **Results**
The model trained with quantized images using the RGBY color model demonstrated better results than training with unquantized images. The reduced and more focused color palette allowed the generator to produce clearer, more distinct sketch lines that more closely resembled hand-drawn sketches.

## Usage

To use Sketch-AI, follow the steps below:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/Sketch-AI.git
'''
2. **Dependencies**:
```bash
  pip install tensorflow matplotlib ipython scikit-learn opencv-python-headless numpy scipy pillow
```
3. **FILES**:
   -**colorQuantized.ipynb** : for color quantization and saving file
   -**GAN.ipynb** and **GAN2.ipynb** : GAN model
   -**pix2pix** : pix2pix example
   -**image** , **sketch** : dataset
## DataSet
-Mid training

![Screenshot 2024-09-20 100116](https://github.com/user-attachments/assets/8eb6e90b-31c7-40a4-8bf6-d05934610863)

-after training

![00000292_03](https://github.com/user-attachments/assets/648eae0e-d9c5-41c6-976d-3b2739b3eb04)
