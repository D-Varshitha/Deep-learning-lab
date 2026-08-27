# CS3807 — Deep Learning Laboratory
**Shiv Nadar University Chennai** | B.Tech AI & Data Science | Semester V | AY 2026–27

---

## Repository Structure

```
DL lab/
├── lab 1/          # Experiment 1 — Neural Network from Scratch
├── lab 2/          # Experiment 2 — Deep Learning with Keras/PyTorch
├── lab 3/          # Experiment 3 — Convolutional Neural Networks (CNNs)
├── lab 4/          # Experiment 4 — Transfer Learning & CNN Architectures
└── lab 5/          # Experiment 5 — CNN Training, Regularization & Optimization
```

---

## Experiments Overview

### Experiment 1 — Neural Network from Scratch

**Folder:** `lab 1/`

**Description:**  
Implementation of a fully connected neural network from scratch using NumPy (without deep learning frameworks). Covers the mathematical foundations of forward propagation, backpropagation, and gradient descent.

**Key Topics:**
- Weight and bias initialization
- Forward and backward propagation
- Learning rate comparison and its effect on training error
- Statistical analysis of data (variance, skewness, histograms, pairplots, correlation heatmaps)
- Confusion matrix evaluation

**Plots Generated:**
| Plot | Description |
|------|-------------|
| `bias_evolution.eps` | Evolution of bias values across training epochs |
| `weight_evolution.eps` | Evolution of weight values across training epochs |
| `training_error.eps` | Training error reduction over epochs |
| `learning_rate_comparison.eps` | Effect of different learning rates on convergence |
| `confusion_matrix.eps` | Classification performance on test data |
| `histogram.eps` | Data distribution analysis |
| `boxplot.eps` | Statistical spread of features |
| `Variance_Skewness.eps` | Variance and skewness analysis per feature |
| `correlation_heatmap.eps` | Feature correlation heatmap |
| `pairplot.eps` | Pairwise feature relationships |

**Deliverables:** `lab report-1.pdf`

---

### Experiment 2 — Deep Learning with Keras

**Folder:** `lab 2/`

**Description:**  
Implementation and training of a Multi-Layer Perceptron (MLP) using Keras, with hyperparameter optimization. Covers model evaluation, class distribution analysis, and comparison of baseline vs. optimized models.

**Key Topics:**
- Building MLP models with Keras
- Hyperparameter search (learning rate, batch size, epochs, units)
- Training/validation accuracy and loss curves
- Confusion matrix analysis
- Accuracy and training time comparison (baseline vs. optimized)

**Plots Generated:**
| Plot | Description |
|------|-------------|
| `class_distribution.png` | Distribution of classes in the dataset |
| `sample_images.png` | Sample images from the dataset |
| `training_accuracy.png` / `training_loss.png` | Baseline model training curves |
| `validation_accuracy.png` / `validation_loss.png` | Baseline model validation curves |
| `hyperparameter_search_results.png` | Results of hyperparameter tuning |
| `optimized_training_accuracy.png` / `optimized_training_loss.png` | Optimized model training curves |
| `optimized_validation_accuracy.png` / `optimized_validation_loss.png` | Optimized model validation curves |
| `confusion_matrix.png` / `optimized_confusion_matrix.png` | Confusion matrices for both models |
| `accuracy_comparison.png` | Accuracy comparison between baseline and optimized |
| `training_time_comparison.png` | Training time comparison |

**Deliverables:** `DL_LAB-2.pdf`, `Experiment_2_Lab_Manual-1.pdf`

---

### Experiment 3 — Convolutional Neural Networks (CNNs)

**Folder:** `lab 3/`

**Description:**  
Design, training, and evaluation of a Convolutional Neural Network for image classification. Includes feature map visualization to understand how CNNs learn hierarchical visual features.

**Key Topics:**
- CNN architecture design (Conv layers, Pooling, Fully Connected layers)
- Training and validation curves
- Feature map visualization
- Confusion matrix analysis
- Class distribution analysis

**Plots Generated:**
| Plot | Description |
|------|-------------|
| `class_distribution.png` | Class distribution in the dataset |
| `sample.png` | Sample images from the dataset |
| `training accuracy.png` | Training accuracy curve |
| `training loss.png` | Training loss curve |
| `validation accuracy.png` | Validation accuracy curve |
| `validation_loss.png` | Validation loss curve |
| `training vs validation accuracy.png` | Train/val accuracy comparison |
| `training vs validation loss.png` | Train/val loss comparison |
| `feature_maps.png` | Intermediate feature map visualizations |
| `confusion_matrix.png` | Final classification confusion matrix |

**Deliverables:** `dl_lab3.pdf`

---

### Experiment 4 — Comparative Study of CNN Architectures & Transfer Learning

**Folder:** `lab 4/`  
**Notebook:** `lab 4.ipynb`  
**Report:** `Experiment_4_updated.tex` / `exp_4.pdf`

**Description:**  
A comparative study of deep CNN architectures — LeNet-5, AlexNet, VGG16, and ResNet50 — applied to the CIFAR-10 dataset using Transfer Learning. Evaluates each architecture on classification accuracy, parameter count, and training time. Includes fine-tuning analysis.

**Dataset:** CIFAR-10 (50,000 train / 10,000 test images, 10 classes, 32×32×3)

**Architectures Compared:**
| Architecture | Depth | Parameters | Key Contribution |
|---|---|---|---|
| LeNet-5 | 7 | 83K | First practical CNN |
| AlexNet | 8 | 37M | ReLU + Dropout + GPU |
| VGG16 | 16 | 14.8M | Uniform 3×3 filters |
| ResNet50 | 50 | 23.9M | Residual/skip connections |

**Results Summary:**
| Model | Accuracy (%) | Precision (%) | Recall (%) | Training Time |
|---|---|---|---|---|
| LeNet-5 | 52.38 | 52.71 | 52.38 | 0.80 min |
| AlexNet | 10.00 | 1.00 | 10.00 | 5.35 min |
| **VGG16** | **91.05** | **91.61** | **91.05** | 44.86 min |
| ResNet50 | 90.84 | 91.00 | 90.84 | 21.59 min |

**Training Config:** Adam optimizer, LR=0.001, Batch=32, Epochs=10–20, Loss=Categorical Cross-Entropy

**Key Findings:**
- VGG16 achieves the highest test accuracy (91.05%) after fine-tuning
- Fine-tuning the last convolutional block improved VGG16 val accuracy from 85.82% → 91.14%
- AlexNet failed to converge due to architectural incompatibility with CIFAR-10 upscaling
- LeNet-5 limited by its shallow architecture designed for grayscale digits

---

### Experiment 5 — CNN Training, Regularization, Optimization, Hyperparameter Tuning, Transfer Learning & Cross-Validation

**Folder:** `lab 5/`  
**Notebook:** `lab-5.ipynb`  
**Report:** `experiment_5_updated.tex`

**Description:**  
A comprehensive study of training strategies for CNNs using MobileNetV2 on the Oxford-IIIT Pet Dataset (37 breeds). Systematically analyzes the effect of weight initialization, regularization methods, optimization algorithms, hyperparameters, and transfer learning. Final model is selected using 5-fold cross-validation.

**Dataset:** Oxford-IIIT Pet Dataset (37 cat/dog breeds, images resized to 224×224×3)

**Base Model:** MobileNetV2 (pretrained on ImageNet, ~2.31M parameters)

**Sections & Key Results:**

#### Weight Initialization
| Method | Best Val. Accuracy (%) |
|---|---|
| Zero | 92.93 |
| He | 91.98 |
| Random / Xavier | 90.90 |

#### Regularization
| Method | Best Val. Accuracy (%) |
|---|---|
| L2 | **93.07** |
| No Regularization | 92.80 |
| Dropout (0.5) | 92.80 |
| Batch Normalization | 92.39 |

#### Optimization Algorithms
| Optimizer | Best Val. Accuracy (%) |
|---|---|
| Adam | **91.71** |
| RMSProp | 90.90 |
| Momentum | 90.35 |
| SGD | 63.45 |

#### Hyperparameter Tuning
| Hyperparameter | Best Value | Best Val. Accuracy (%) |
|---|---|---|
| Learning Rate | 0.001 | 91.58 |
| Batch Size | 16 | 92.26 |
| Dropout Rate | 0.50 | 92.26 |

#### 5-Fold Cross-Validation
| Configuration | Mean ± SD (%) |
|---|---|
| C1_Baseline (LR=0.001, BS=32, Dropout=0, Adam) | **90.15 ± 0.96** |
| C2_Dropout | 90.08 ± 1.10 |
| C3_LowLR (LR=0.0001) | 76.73 ± 1.18 |
| C4_SGD | 53.33 ± 2.44 |

#### Final Model Performance
| Metric | Value |
|---|---|
| Best Configuration | C1_Baseline |
| Test Accuracy | **89.34%** |
| Precision | 89.78% |
| Recall | 89.34% |
| F1-score | 89.33% |
| Training Time | 73.92 s |

---

## Tools & Frameworks

| Tool | Usage |
|------|-------|
| Python 3.x | Primary language |
| TensorFlow / Keras | Model building and training |
| NumPy | Numerical computation (Exp 1) |
| Matplotlib / Seaborn | Visualization |
| scikit-learn | Metrics, K-Fold CV |
| LaTeX | Lab report generation |

---

## How to Run

1. Open the Jupyter notebook (`.ipynb`) in each lab folder.
2. Run all cells sequentially.
3. Generated plots are saved automatically to the `plots/` or `Graphs/` subfolder.
4. Compile the `.tex` file to generate the PDF report (requires LaTeX installation).

---

> **Note:** This repository is actively updated as new experiments are completed throughout the semester.
