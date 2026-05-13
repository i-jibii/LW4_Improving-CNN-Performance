# Laboratory Work 4 — Improving CNN Performance
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NQ1T42jlJAiEBGNDrDvANJUJuhIkt6nY?usp=sharing)

**Status: SUCCESS (Final Accuracy: 88.40%)**

## 📊 Three-Stage Performance Comparison

| Metric | Baseline Model (LW3) | Improved Model (Custom) | **Advanced Model (EfficientNet)** |
| :--- | :--- | :--- | :--- |
| **Validation Accuracy** | 74.00% | 35.82% | **88.40%** |
| **Training Accuracy** | ~80.00% | 25.54% | **96.37%** |
| **Precision (Weighted)** | 0.77 | 0.43 | **0.90** |
| **Recall (Weighted)** | 0.74 | 0.36 | **0.88** |
| **F1-score (Weighted)** | 0.74 | 0.33 | **0.89** |

---

## 🧠 GUIDE QUESTIONS (Reflection & Analysis)

### **A. Model Evaluation Analysis**
1.  **Weakest-performing classes**: In the baseline, **Silver moss** was the weakest. In the final Advanced Model, all classes performed above 70%, with **Fire moss** being the most challenging.
2.  **Score Variation**: Precision reached **1.00** for several classes (Silver, Red-stemmed feather, Yew-leaved pocket), meaning the model was 100% certain when it identified those species.
3.  **Low Recall Significance**: Low recall indicates the model is "missing" instances of a species (False Negatives). Our final model fixed this, raising recall from ~30% to **88%**.
4.  **AUC vs Accuracy**: The AUC score reflected the model's high potential early on. Even when accuracy was low, the high AUC showed the model was learning the right categories.

### **B. Model Improvement**
5.  **Data Augmentation**: Forced the model to learn shapes and textures that are invariant to rotation or lighting, making it robust for real-world field photos.
6.  **Batch Normalization**: Stabilized the internal gradients of the CNN, allowing us to use a much higher performance architecture (EfficientNet) without it "crashing."
7.  **Dropout**: Acted as a regularizer, ensuring the model didn't just "memorize" the training set but instead learned generalizable features.
8.  **Early Stopping**: Prevented overfitting by halting training if the validation loss stopped improving, ensuring the model remained "flexible."

### **C. Performance Comparison**
9.  **Improvements**: We achieved a **14% jump** over the baseline accuracy and a total elimination of "blind spots" (0.00 scores) in the classification report.
10. **Most Contributed**: **Transfer Learning (EfficientNetB0)**. Using a pre-trained "Master Brain" allowed the model to leverage millions of pre-learned visual features.
11. **Gap Decrease**: The generalization gap narrowed to a healthy **7%**, which is excellent for a 20-class botanical dataset.

### **D. Explainability (Grad-CAM Integration)**
12. **Grad-CAM Utility**: It revealed the "Heatmap" of the AI's attention, proving it focuses on moss leaf clusters rather than the background soil.
13. **Relevant Regions**: Yes. The hotspots were concentrated on the central moss cushions, providing visual evidence of botanical feature extraction.
14. **Real-World Importance**: Explainability builds trust. It ensures that an AI used for biological research is making decisions based on actual science, not coincidental background pixels.
