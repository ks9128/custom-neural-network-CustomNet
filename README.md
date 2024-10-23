# Comparative Analysis of Custom Neural Network Model and VGG-16 for Multi-class Image Classification

## Overview
This study compares the performance of **CustomNet**, a lightweight neural network model, and **VGG-16** on three datasets: **MNIST**, **Fashion MNIST**, and **Virus MNIST**. The goal was to evaluate accuracy, parameter efficiency, and model performance.

## Datasets
### 1. MNIST
A collection of **70,000** 28x28 grayscale images representing handwritten digits (0-9). It contains **60,000** training and **10,000** test images.

### 2. Fashion MNIST
Similar to MNIST, this dataset consists of **70,000** grayscale images of clothing items, used for image classification tasks.

### 3. Virus MNIST
This dataset contains **50,000** images in **32x32** format, representing 9 virus families and 1 benign category. It is designed for malware classification.

## Models
### VGG-16
A **16-layer CNN** known for its accuracy but with **44 million parameters**, making it computationally expensive. It is often used for image classification tasks requiring high performance.

**VGG-16 Model Summary**:
- Total Parameters: **44,545,760**
- Optimizer: **SGD**
- Activation Function: **ReLU** and **Softmax**

### CustomNet (Proposed Model)
A simpler, more efficient neural network with **6 hidden layers**. Regularization is achieved through **L2 regularization** and **dropout**, with **LeakyReLU** for activation.

**CustomNet Model Summary**:
- Total Parameters: **575,160**
- Optimizer: **Mini-batch gradient descent**
- Activation Function: **LeakyReLU** and **Softmax**

## Evaluation Metrics
### 1. Accuracy
Measures the proportion of correctly predicted instances.
``` 
Accuracy = (TP + TN) / Total Instances
```
### 2. Precision
Represents the proportion of correctly predicted positive cases.
``` 
Precision = TP / (TP + FP)
```
### 3. Recall
Proportion of actual positives that are correctly identified.
``` 
Recall = TP / (TP + FN)
```
### 4. F1 Score
Harmonic mean of Precision and Recall.
``` 
F1 Score = 2 × (Precision × Recall) / (Precision + Recall)
```

## Results

### MNIST Dataset
| Model        | Parameters   | Precision | Recall  | F1 Score | Accuracy |
|--------------|--------------|-----------|---------|----------|----------|
| VGG-16       | 44,545,760   | 0.9749    | 0.9734  | 0.9736   | 97.34%   |
| CustomNet    | 575,160      | 0.9629    | 0.9629  | 0.9628   | 96.29%   |

### Fashion MNIST Dataset
| Model        | Parameters   | Precision | Recall  | F1 Score | Accuracy |
|--------------|--------------|-----------|---------|----------|----------|
| VGG-16       | 44,545,760   | 0.9069    | 0.9069  | 0.9057   | 90.69%   |
| CustomNet    | 575,160      | 0.8590    | 0.8602  | 0.8588   | 86.02%   |

### Virus MNIST Dataset
| Model        | Parameters   | Precision | Recall  | F1 Score | Accuracy |
|--------------|--------------|-----------|---------|----------|----------|
| VGG-16       | 44,545,760   | 0.8696    | 0.8826  | 0.8654   | 88.26%   |
| CustomNet    | 698,040      | 0.8476    | 0.8826  | 0.8691   | 88.26%   |

### Accuracy Comparison
The comparison of accuracy across all datasets shows:
- **MNIST**: CustomNet (96.29%) vs. VGG-16 (97.34%)
- **Fashion MNIST**: CustomNet (86.02%) vs. VGG-16 (90.69%)
- **Virus MNIST**: Both models (88.26%)

## Conclusion
CustomNet delivers **96.29% accuracy** on MNIST using only **1.29% of VGG-16's parameters**, demonstrating significant parameter efficiency. CustomNet is an effective solution for **resource-constrained environments** like mobile devices or embedded systems, despite slightly lower accuracy.

## Future Work
Future enhancements for CustomNet could include:
- **Advanced optimizers** (e.g., Adam or RMSprop)
- **Transfer learning** for improved performance on complex datasets.
- **Quantization and model pruning** to reduce resource usage further.
