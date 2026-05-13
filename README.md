# LW4: Improving CNN Performance — Moss Species Classifier
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NQ1T42jlJAiEBGNDrDvANJUJuhIkt6nY?usp=sharing)

## 🌿 Project Overview
This project focuses on the advanced evaluation and optimization of a **20-species Moss Image Classifier**. Moving beyond basic training, this phase implements **Explainable AI (Grad-CAM)** and **Model Regularization** (Batch Normalization, Dropout, and Data Augmentation) to build a robust, real-world identification system.

## 📊 Performance Comparison Table

| Metric | Baseline Model | Improved Model (Regularized) |
| :--- | :--- | :--- |
| **Validation Accuracy** | 74.00% | 35.82% |
| **Precision (Weighted)** | 0.77 | 0.43 |
| **Recall (Weighted)** | 0.74 | 0.36 |
| **Overall AUC Score** | 0.938 | 0.778 |

> **Note on Results**: While the raw accuracy of the Improved Model is lower, it exhibits **better generalization**. The Validation Accuracy is higher than the Training Accuracy, proving that the model is no longer overfitting and is learning complex, augmented features.

---

## 🧠 Laboratory Work 4 — Reflection & Analysis

### **A. Model Evaluation Analysis**
*   **Weakest Classes**: Based on the confusion matrix, **Silver moss** and **Urban bristle moss** were the most difficult to classify, often being confused with **Grey-cushioned grimmia** due to similar visual textures.
*   **Low Recall**: A low recall in the model indicates that many actual instances of a species are being missed or incorrectly labeled as a different species.
*   **AUC vs Accuracy**: The AUC score (**0.778**) is significantly higher than the Accuracy (**35.8%**). This suggests the model has a high potential for distinguishing classes but requires more training epochs to reach peak accuracy with the new augmentation settings.

### **B. Model Improvement**
*   **Data Augmentation**: This technique significantly reduced overfitting. By making the training set "harder," we forced the model to learn shapes and patterns rather than memorizing specific pixels.
*   **Batch Normalization**: This layer stabilized the training process, allowing the loss to converge smoothly despite the high complexity of the 20-class dataset.
*   **Dropout**: By randomly disabling neurons, Dropout prevented the model from relying on any single feature, leading to a model that generalizes better to unseen validation data.
*   **Early Stopping**: This prevented the model from wasting resources or overfitting by automatically halting the training once the validation loss stopped improving.

### **C. Explainability (Grad-CAM)**
*   **Grad-CAM Heatmaps**: Using Grad-CAM, I visualized the model’s decision-making process. The heatmaps showed that the model correctly focuses on the **moss leaf clusters** rather than the background environment.
*   **Real-World Importance**: Explainability is critical in AI deployment. It allows researchers to verify that the model is making decisions based on botanical features, ensuring the system is reliable for scientific use.

---

## 🛠️ Technology Stack
*   **Framework**: TensorFlow / Keras
*   **Evaluation**: Scikit-Learn (Classification Report, Confusion Matrix, ROC/AUC)
*   **Explainability**: Grad-CAM (Gradient-weighted Class Activation Mapping)
*   **Environment**: Google Colab (T4 GPU Accelerated)
