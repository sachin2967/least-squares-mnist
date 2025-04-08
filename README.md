# MNIST Classification Using Least Squares  

**Date:** November 10, 2024  
**Author:** Sachin Yadav (21CE3AI15)  

This project implements a Least Squares Classifier to recognize handwritten digits from the MNIST dataset. It provides insights into the model's performance, discusses misclassifications, and highlights the limitations of using Least Squares for MNIST classification.  

---

## 📌 Features  
- **Dataset:** MNIST handwritten digits dataset fetched using `scikit-learn`.  
- **Model:** Least Squares Classifier implemented using `numpy.linalg.lstsq`.  
- **Evaluation Metrics:** Training and test accuracy, along with analysis of misclassified examples.  
- **Visualization:** Displays correctly classified and misclassified images for better interpretability.  

---

## 🛠 Explanation  

### **1. Training and Test Accuracy Results**  
- **Training Set Accuracy:** 85.9%  
- **Test Set Accuracy:** 85.4%  

The model achieves moderate accuracy on both training and test sets, indicating that it generalizes reasonably well but struggles with certain aspects of the dataset's complexity.  

---

### **2. Discussion of Misclassified Examples**  
Misclassifications occur due to several reasons:  

1. **Similar Structures Between Digits:**  
   - Example: Digit '9' misclassified as '4'.  
   - Reason: Digits with overlapping features are challenging for a linear classifier to distinguish.  

2. **Diverse Handwriting Styles:**  
   - Example: Digit '8' misclassified as '7'.  
   - Reason: Variations in handwriting styles make some digits harder to classify accurately.  

3. **Noise in Images:**  
   - Example: Faint strokes or extra pixels can confuse the model, leading to errors like '3' misclassified as '1'.  

4. **Linear Model Limitations:**  
   - The least squares method cannot capture non-linear features in the data, which are essential for distinguishing complex patterns in MNIST.  

5. **Global Weight Matrix Constraint:**  
   - The model uses a single global weight matrix, which lacks flexibility to account for local variations within each digit class.

---

### **3. Why Least Squares Classifier May Perform Worse on MNIST**  
The limitations of the Least Squares Classifier on MNIST can be summarized as follows:  

1. **Linear Decision Boundaries:**  
   - The least squares method is a linear classifier, which cannot handle the non-linear decision boundaries required for separating complex patterns in MNIST (e.g., '4' vs. '9', '3' vs. '8').  

2. **Lack of Flexibility for Local Variations:**  
   - A single weight matrix is used for all classes, making it difficult to adapt to diverse handwriting styles within each digit class.  

3. **Sensitivity to Noise and Outliers:**  
   - The least squares method minimizes the sum of squared errors, making it sensitive to noise or mislabeled data points, which can lead to significant prediction errors.  

4. **Overfitting to Outliers:**  
   - The model may overfit noisy or mislabeled examples, reducing its ability to generalize effectively across the dataset.  

5. **No Hierarchical Feature Learning:**  
   - Unlike neural networks or other advanced models, the least squares classifier does not learn abstract features such as edges or shapes that are critical for digit recognition.

These factors contribute to its lower performance compared to non-linear classifiers like Support Vector Machines (SVMs) or deep learning models.

---

## 🔍 Results Summary  

- **Training Accuracy:** 85.9%  
- **Test Accuracy:** 85.4%  

### Visualizations:  
1. Correctly classified images:  
   ![Correct Predictions](pe1.png)  

2. Misclassified images:  
   ![Misclassified Images](pe2.png)  

---

For detailed code and implementation, refer to my [Google Colab notebook](#). *(Replace `#` with your actual link)*
