# dual_stream acne detection using roi and deep learning
## 🔍 What Happens in This Project

This project implements a **multi-stage deep learning pipeline** for skin/acne analysis using PyTorch.

### 🧠 Step-by-Step Pipeline

1. **Dataset Processing**

   * Loads images, segmentation masks, and labels
   * Performs resizing, normalization, and tensor conversion
   * Prepares data for both segmentation and classification tasks

2. **Preprocessing Network (AMBAP-Net)**
   The input image is enhanced using a custom pipeline:

   * **Skin Tone Estimation** → learns skin variations
   * **Adaptive Color Normalization** → adjusts lighting and color
   * **Illumination Correction** → separates lighting from texture
   * **Artifact Removal** → removes noise and unwanted patterns
   * **Texture Enhancement** → improves fine skin details
   * **ROI Prior** → highlights important regions (acne areas)

3. **Segmentation (U-Net++)**

   * Predicts lesion regions at pixel level
   * Helps the model focus on acne areas

4. **Classification (ConvNeXt)**

   * Classifies the image into categories (e.g., Acne / Clear)
   * Uses deep CNN features for accurate prediction

5. **Multi-Task Learning**

   * The model performs **segmentation + classification simultaneously**
   * Improves performance and robustness

6. **Loss Function**
   The model is trained using a combination of:

   * Dice Loss → segmentation accuracy
   * Cross Entropy Loss → classification accuracy
   * Illumination Loss → lighting consistency
   * Mask Regularization → cleaner region focus

---

### 🚀 Final Pipeline

Input Image
→ Enhancement (AMBAP-Net)
→ Segmentation (U-Net++)
→ Classification (ConvNeXt)

---

### 🔥 Key Highlights

* ROI-focused learning improves accuracy
* Handles lighting and skin tone variations
* Combines preprocessing + segmentation + classification
* Designed for real-world robustness

---

### 🧪 Output

The model produces:

* Segmentation mask (lesion detection)
* Classification result (skin condition)
* Additional outputs (illumination, ROI mask)

---

📌 Code implementation available here: 
