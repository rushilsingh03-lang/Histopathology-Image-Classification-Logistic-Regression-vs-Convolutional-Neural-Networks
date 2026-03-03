A Comparative Study with Logistic Regression
Overview

This project presents a comparative analysis between a baseline Logistic Regression model and a Convolutional Neural Network (CNN) for multi-class histological tissue image classification.

The objective is to evaluate how linear models compare to deep learning architectures when applied to spatially structured medical image data.

By contrasting flattened-feature linear classification with convolution-based feature extraction, this study highlights the importance of spatial inductive bias in medical imaging tasks.

Clinical Context

Histopathological tissue classification plays a critical role in the diagnosis of colorectal cancer and related abnormalities. Automated classification systems can support pathologists by:

Reducing diagnostic workload

Improving triage efficiency

Assisting in early detection

Supporting large-scale screening

Understanding which modelling approaches are most appropriate for spatial medical data is essential for building reliable AI-assisted diagnostic tools.

Dataset

Image size: 28 × 28 × 3 (RGB)

Number of classes: 5

Tissue Categories:

Adipose

Lymphocytes

Normal colon mucosa

Cancer-associated stroma

Colorectal adenocarcinoma epithelium

Data Split:

Training set

Validation set (80/20 split from training)

Independent test set

Methodology
Baseline Model — Logistic Regression

Images flattened into 1D feature vectors

No spatial feature extraction

Evaluated using:

Test Accuracy

Confusion Matrix

Log Loss

This baseline illustrates the limitations of linear classifiers on spatially structured image data.

Deep Learning Model — Convolutional Neural Network (CNN)

Architecture:

Two convolutional layers

ReLU activation

Max pooling

Fully connected output layer

Training details:

Loss function: CrossEntropyLoss

Optimizer: Adam

Hyperparameter tuning on learning rate

Learning rates evaluated:

0.00001

0.001

0.01

📈 Evaluation Metrics

Models were assessed using:

Test Accuracy

Validation Accuracy

Log Loss

Confusion Matrices

Learning Curves (Loss vs Epoch, Accuracy vs Epoch)

Key Results
Model	Test Accuracy
Logistic Regression	22.8%
CNN (lr = 0.001)	77.5%

Log Loss Comparison:

Logistic Regression: ~1.72

CNN: ~0.40

The CNN significantly outperformed the linear baseline, demonstrating the importance of convolutional architectures for spatial medical image data.

Hyperparameter Analysis

Learning rate sensitivity was systematically evaluated:

0.00001 → Slow convergence, underfitting (~61% validation accuracy)

0.001 → Optimal performance (~86% validation accuracy)

0.01 → Unstable optimisation (~66% validation accuracy)

This highlights the critical role of hyperparameter tuning in deep learning workflows.

🔍 Why Logistic Regression Underperforms

Flattening images removes spatial structure, eliminating:

Local feature relationships

Translation invariance

Hierarchical feature learning

As a result, logistic regression fails to capture meaningful patterns inherent to histological imagery.

CNNs, by contrast, preserve spatial locality and learn hierarchical features, making them substantially more suitable for medical image classification tasks.

Repository Structure
histopathology-image-classification/
│
├── histopathology_classification_pipeline.ipynb
├── README.md
└── figures/
    ├── accuracy_comparison.png
    ├── loss_comparison.png
    ├── confusion_matrix.png
Tools & Libraries

Python

PyTorch

NumPy

Matplotlib

scikit-learn

Key Skills Demonstrated

Deep learning model development

Baseline model comparison

Hyperparameter optimisation

Experimental evaluation design

Medical image data handling

Performance interpretation

Model validation with an independent test set

Future Improvements

Transfer learning with pretrained architectures (e.g., ResNet)

Data augmentation for improved generalisation

Cross-validation across stratified folds

Model interpretability (Grad-CAM visualisation)

Deployment-ready inference pipeline

Conclusion

This study demonstrates that convolutional neural networks dramatically outperform linear classifiers for histopathological image classification. By preserving spatial structure and learning hierarchical features, CNNs provide a substantially more suitable framework for medical imaging tasks.

The project highlights the importance of model selection, hyperparameter tuning, and proper validation strategies in applied healthcare AI.
