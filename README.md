🧬 Histological Tissue Classification Using CNNs
A Comparative Study with Logistic Regression
📌 Overview

This project presents a comparative analysis between a baseline Logistic Regression model and a Convolutional Neural Network (CNN) for multi-class histological tissue image classification. The objective is to evaluate how linear models compare to deep learning approaches when applied to spatially structured medical image data.

🗂 Dataset

Image size: 28 × 28 × 3 (RGB)

Number of classes: 5

Tissue categories:

Adipose

Lymphocytes

Normal colon mucosa

Cancer-associated stroma

Colorectal adenocarcinoma epithelium

The dataset was split into:

Training set

Validation set (80/20 split from training)

Independent test set

🛠 Methods
1️⃣ Baseline Model – Logistic Regression

Images flattened into 1D vectors

No spatial feature extraction

Evaluated using:

Test Accuracy

Confusion Matrix

Log Loss

2️⃣ Deep Learning Model – CNN

Two convolutional layers

ReLU activation

Max pooling

Fully connected output layer

Trained using CrossEntropyLoss and Adam optimizer

Hyperparameter tuning performed on learning rate

Learning rates tested:

0.00001

0.001

0.01

📊 Evaluation Metrics

Models were evaluated using:

Test Accuracy

Validation Accuracy

Log Loss

Confusion Matrices

Learning Curves (Loss vs Epoch, Accuracy vs Epoch)

🔍 Key Results
Model	Test Accuracy
Logistic Regression	22.8%
CNN (lr = 0.001)	77.5%

Log Loss Comparison:

Logistic Regression: ~1.72

CNN: ~0.40

The CNN significantly outperformed the linear baseline, demonstrating the importance of convolutional architectures for spatial image data.

📈 Hyperparameter Analysis

The effect of learning rate was systematically evaluated:

0.00001 → Slow convergence, underfitting (~61% validation accuracy)

0.001 → Optimal performance (~86% validation accuracy)

0.01 → Unstable optimisation (~66% validation accuracy)

This confirms the critical role of hyperparameter tuning in model optimisation.

🧠 Key Insights

Logistic regression struggles with flattened image representations.

CNN preserves spatial relationships and captures hierarchical features.

Learning rate significantly impacts convergence behaviour.

Deep learning models are substantially more suitable for medical image classification tasks.

📂 Repository Structure
├── 14340103_Assignment1.ipynb
├── README.md
└── figures/
    ├── accuracy_comparison.png
    ├── loss_comparison.png
    ├── confusion_matrix.png
🚀 Conclusion

This study demonstrates that convolutional neural networks dramatically outperform linear classifiers for histopathological image classification. Proper hyperparameter tuning further enhances performance, highlighting the importance of experimental optimisation in deep learning workflows.
