#  ROI-Guided Dual-Stream Acne Detection System

##  Overview
This project proposes a deep learning-based acne detection system that combines ROI-guided learning, dual-stream CNN architecture, Transformer-based feature enhancement, attention-based fusion, and multi-task learning. The model focuses on both global facial features and local lesion regions to improve accuracy and reliability.

---

##  Architecture

Input Image  
↓  
DeepLabV3 (ROI Segmentation)  
↓  
Full Image + ROI  
↓  
Dual CNN Feature Extraction  
   - Full Image → ResNet50 (Global Features)  
   - ROI Image → ResNet18 (Local Features)  
↓  
Transformer (Global Context Enhancement)  
↓  
Attention-Based Feature Fusion  
↓  
Multi-Task Outputs  
   - Classification (Acne / Clear)  
   - Severity Prediction  
   - Lesion Count  

---

##  Key Features

- ROI extraction using DeepLabV3 (learned segmentation)
- Dual-stream architecture (global + local features)
- Transformer for capturing long-range dependencies
- Attention mechanism for dynamic feature weighting
- Multi-task learning for richer feature representation

---

##  Ablation Study Summary

- Removing ROI → Model focuses on background (less reliable)
- Removing Transformer → Loss of global context
- Removing Attention → Poor feature prioritization
- Removing Multi-task → Weak feature learning
- CNN-only baseline → Lowest performance

 Each component contributes significantly to final performance.

---

## 📊 Results

- High classification accuracy for acne detection
- Strong diagonal dominance in confusion matrix
- Improved focus on lesion regions using ROI
- Better generalization due to multi-task learning

---

## 🎯 Multi-Task Learning

The model predicts multiple outputs from shared features:

- Classification → Acne / Clear
- Severity → Based on lesion area
- Count → Estimated lesion count

Loss Function:
Loss = Classification + 0.7 × Severity + 0.3 × Count

---

## 💡 Why This Work is Important

- Reduces background noise using ROI-based learning
- Combines global and local features effectively
- Improves interpretability (focus on lesions)
- Can be extended to other skin diseases
- Suitable for real-world and clinical applications

---

## 🧠 Conclusion

The proposed ROI-guided dual-stream architecture with Transformer and attention-based fusion significantly improves accuracy, robustness, and interpretability compared to traditional CNN-based approaches.

---

## 👨‍💻 Technologies Used

- Python
- PyTorch
- torchvision
- timm
- OpenCV

---

## 📎 Future Work

- Improve dataset diversity
- Add real lesion count annotations
- Deploy as a web/mobile application
- Extend to multi-class skin disease detection

---
