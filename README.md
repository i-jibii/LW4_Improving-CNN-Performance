# LW4: Improving CNN Performance — 20-Species Moss Classifier
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NQ1T42jlJAiEBGNDrDvANJUJuhIkt6nY?usp=sharing)

## 📊 Final Multi-Stage Comparison

| Metric | Baseline Model (LW3) | Improved Model (Custom) | **Advanced Model (Master)** |
| :--- | :--- | :--- | :--- |
| **Validation Accuracy** | 74.00% | 35.82% | **88.40%** |
| **Overall AUC Score** | 0.938 | 0.778 | **0.994** |
| **Precision (Weighted)** | 0.77 | 0.43 | **0.90** |
| **Recall (Weighted)** | 0.74 | 0.36 | **0.88** |
| **F1-score (Weighted)** | 0.74 | 0.33 | **0.89** |

---

## 🧠 GUIDE QUESTIONS (Reflection & Analysis)

### **A. Model Evaluation Analysis**
*   **Weakest Classes**: In the final model, performance was balanced, with **Fire moss** being the only class below 80%.
*   **Metric Variation**: Precision reached **1.00** for species like Silver and Red-stemmed feather moss, showing the model is highly specific.
*   **AUC vs Accuracy**: The AUC (**0.994**) confirms that the model has nearly perfect class-separation capabilities, even if the raw accuracy (88%) is slightly lower due to hard augmentation.

### **B. Model Improvement**
*   **Data Augmentation**: Significantly reduced overfitting by making training "harder" than testing.
*   **Batch Normalization**: Stabilized the deep EfficientNet layers, preventing gradient explosion.
*   **Dropout**: Ensured the model learned general features rather than memorizing individual photos.
*   **Early Stopping**: Prevented over-training and saved computational resources.

### **C. Performance Comparison**
*   **Improvements**: We achieved a **14% boost** in accuracy and a **6% boost** in AUC over the baseline.
*   **Key Enhancement**: **Transfer Learning (EfficientNetB0)** provided the most significant performance jump.
*   **Generalization**: The gap between Training and Validation accuracy was kept within healthy margins, proving robustness.

### **D. Explainability (Grad-CAM)**
*   **Utility**: Grad-CAM heatmaps provided visual evidence that the AI focuses on **moss leaf textures**.
*   **Evidence**: Heatmaps were concentrated on the central moss cushions, confirming botanical feature extraction.
*   **Importance**: XAI builds trust in biological identification, ensuring decisions are based on science.
