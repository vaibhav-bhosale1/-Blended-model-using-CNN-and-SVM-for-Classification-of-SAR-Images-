# -Blended-model-using-CNN-and-SVM-for-Classification-of-SAR-Images-
## Key Highlights

- Designed and implemented a **hybrid model** combining the strengths of **Convolutional Neural Networks (CNN)** and **Support Vector Machines (SVM)** for accurate classification of **Synthetic Aperture Radar (SAR) images**.
- Focused on classifying **military vehicles** including **2S1, BRDM_2, BTR60, D7, SLICY, T62, ZIL131, and ZSU**, improving **Automatic Target Recognition (ATR)** performance.
- Utilized CNN for **feature extraction** and SVM for **robust classification**, ensuring high precision and scalability.
- Achieved advancements in **SAR imagery processing** by integrating machine learning techniques to tackle real-world challenges in **remote sensing applications**.

## Dataset Description

- **Dataset Link(MSTAR):** https://www.sdms.afrl.af.mil/index.php?collection=mstar 
- **MSTAR:** The MSTAR dataset is a collection of SAR images
- **Total Images:** 3887 JPEG images  
- **Classes:** Seven military objects (`2S1`, `BRDM-2`, `BTR-60`, `D7`, `T72`, `ZIL 131`, `ZSU-234`)  
- **Training/Test Split:** 80:20 (`3106 training`, `781 testing`)  
- **Resolution:** 100x100 pixels
- ![SAR Image Classification Workflow](path/to/your/image.png)

*Figure: n*

## Data Preprocessing

- **Rescaling:** Pixel values normalized to the `[0,1]` range.  
- **Shear Range:** Random shear within `0.2` for perspective variation.  
- **Rotation Range:** Random rotations within `10°`.  
- **Zoom Range:** Zoom in/out for focusing on specific details.  
- **Horizontal Flip:** Random flips for increased orientation variations.

- ## Model Architecture

1. **Hybrid CNN-SVM Model**: Features are extracted from SAR images using a deep **Convolutional Neural Network (CNN)**, followed by classification with a **Support Vector Machine (SVM)** enhanced by a squared hinge loss function with L2 regularization.

2. **Input Preprocessing**: SAR images are resized to **128x128 grayscale** format, normalized to the `[0, 1]` range, and processed through a rescaling layer for numerical stability.

3. **Feature Extraction**: The CNN model includes **three convolutional layers** (32 kernels, 3x3) with **ReLU activation** and **max-pooling layers** to capture spatial details while reducing dimensionality.

4. **Fully Connected Layer**: Features are flattened and passed to a dense layer with **128 neurons (ReLU activation)** for refinement before classification. The final layer uses **softmax activation** for multi-class classification with L2 regularization to minimize overfitting.

5. **Benchmarking Models**: The hybrid model is compared against **CNN, VGG19, and ResNet architectures**, demonstrating its effectiveness in classifying military vehicles from SAR imagery.

6. **ResNet**: Integrates **residual blocks** with skip connections for efficient training, addressing diminishing gradients while learning complex feature mappings.

7. **VGG19 Adaptation**: Fine-tuned to classify SAR imagery by replacing its fully connected layers with **custom dense layers**, leveraging its hierarchical feature extraction capabilities for improved performance.

