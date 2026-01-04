# 🧪 Malaria Cell Classification using CNN

## 1. Problem Description
Malaria is a life-threatening disease caused by parasites transmitted through mosquito bites. 
Diagnosis is commonly performed by manually examining blood smear images under a microscope, 
which is time-consuming and prone to human error.

The objective of this project is to automatically classify blood cell images as **Parasitized** 
or **Uninfected** using a Convolutional Neural Network (CNN), in order to assist medical diagnosis 
and reduce misclassification.

---

## 2. Dataset Analysis
The dataset consists of microscopic images of blood cells divided into two classes:
**Parasitized** and **Uninfected**.  
Before training, the dataset was analyzed to verify the number of samples per class and ensure 
that the data is approximately balanced, reducing the risk of bias during training.

A visual inspection shows clear structural differences between infected and healthy cells, 
indicating that spatial features can be effectively learned by a CNN.

---

## 3. Data Preprocessing
All images are resized to 224×224 pixels to ensure uniform input size.  
Pixel values are normalized using ImageNet mean and standard deviation to stabilize training.

Data augmentation (random flips, rotations, and color jitter) is applied only to the training 
set to improve generalization. Validation and test sets are kept unchanged to reflect real-world conditions.

---

## 4. Model Architecture
A custom CNN is designed with three convolutional layers followed by Batch Normalization, 
ReLU activation, and MaxPooling to extract hierarchical spatial features.

Adaptive Average Pooling is used to remove dependency on input image size, making the model 
more flexible and reusable. Dropout is applied before the fully connected layers to reduce 
overfitting.

---

## 5. Training Strategy
The model is trained using **CrossEntropyLoss**, which is suitable for multi-class classification tasks.
The **Adam optimizer** is chosen for its fast convergence and adaptive learning rate.

Training is monitored using a validation set to track generalization performance and prevent overfitting.
The best model is saved based on validation accuracy.

---

## 6. Evaluation and Results
The model is evaluated on a held-out test set. Performance is measured using accuracy, 
confusion matrix, precision, recall, and F1-score.

The confusion matrix shows a high number of correctly classified samples, with limited false 
positives and false negatives. The overall test accuracy reaches approximately **94.5%**, 
indicating strong generalization.

---

## 7. Overfitting Analysis
Training and validation accuracies remain close throughout training, suggesting that the model 
learns meaningful features rather than memorizing the data. The use of dropout and validation 
monitoring helps prevent overfitting.

---

## 8. Baseline Comparison
A simpler baseline model (e.g., logistic regression or shallow classifier) would be unable to 
capture complex spatial patterns in images. The CNN significantly outperforms such baselines, 
justifying the use of deep learning for this task.

---

## 9. Future Work
Future improvements could include transfer learning with pre-trained models, increasing dataset 
diversity, and deploying the model in real clinical environments. Additional evaluation on 
external datasets would further validate robustness.



