# Handwritten Digit Recognition: CNN vs Bidirectional LSTM

A Deep Learning project that implements and compares **Convolutional Neural Networks (CNN)** and **Bidirectional Long Short-Term Memory (BiLSTM)** networks for handwritten digit recognition using the MNIST dataset.

The project explores two different approaches to image classification: spatial feature extraction using CNN and sequential pattern learning using Bidirectional LSTM. Both models are trained and evaluated to understand their performance, learning behavior, and classification capabilities.

## Project Overview

Handwritten digit recognition is a fundamental computer vision task with applications in:
- Automated postal address recognition.
- Bank cheque processing.
- Digitization of handwritten documents.
- Automatic form processing.
- Optical Character Recognition (OCR) systems.

The objective of this project is to understand how different deep learning architectures learn features from handwritten images and compare their classification performance.

## Models Implemented

### 1. Convolutional Neural Network (CNN)

CNN is designed to extract spatial features from images automatically.

**Architecture:**
- Convolutional layers for extracting visual features.
- Batch Normalization for stabilizing training.
- ReLU activation for introducing non-linearity.
- Max Pooling for reducing spatial dimensions.
- Dropout for reducing overfitting.
- Fully Connected layers for digit classification.

The CNN learns visual patterns such as edges, curves, shapes, and other important structures present in handwritten digits.

### 2. Bidirectional LSTM (RNN)

The second model uses a Bidirectional LSTM to process handwritten images as sequential data.

Instead of treating an image as a conventional 2D input, each 28 × 28 image is converted into a sequence of 28 rows, where each time step contains 28 pixel values.

**Architecture:**
- Two-layer Bidirectional LSTM.
- Hidden size of 128.
- Forward and backward sequence processing.
- Concatenation of forward and backward hidden states.
- Fully Connected layers for classification.
- ReLU activation and Dropout.

The model learns sequential dependencies and patterns across image rows to classify handwritten digits.

## Dataset: MNIST

The project uses the MNIST (Modified National Institute of Standards and Technology) handwritten digit dataset.

| Property | Description |
|---|---|
| Dataset | MNIST |
| Training images | 60,000 |
| Testing images | 10,000 |
| Image dimensions | 28 × 28 |
| Image type | Grayscale |
| Number of classes | 10 |
| Classes | Digits 0–9 |
| Pixel representation | 0–255 (before normalization) |

The dataset is downloaded automatically using `torchvision.datasets.MNIST`.

**Preprocessing:**
- Convert images into PyTorch tensors.
- Normalize images using mean = 0.1307 and standard deviation = 0.3081.
- Load data using DataLoader.
- Batch size: 64.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| PyTorch | Deep learning framework |
| Torchvision | Dataset loading and transformations |
| NumPy | Numerical operations |
| Pandas | Data handling |
| Matplotlib | Data visualization |
| Scikit-learn | Model evaluation and classification metrics |

## Model Training Configuration

Both models use the following common training configuration:

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Loss Function | CrossEntropyLoss |
| Batch Size | 64 |
| Epochs | 8 |
| Output Classes | 10 |

The models are trained independently using the same MNIST training dataset.

## Model Evaluation

The performance of both models is evaluated using multiple evaluation techniques.

**1. Accuracy Comparison**
- Calculate CNN classification accuracy.
- Calculate Bidirectional LSTM classification accuracy.
- Compare both models to identify the better-performing architecture.

**2. Confusion Matrix**

Visualize the classification results for all ten digit classes and identify correctly and incorrectly classified digits.

**3. Classification Report**

Evaluate each model using:
- Precision
- Recall
- F1-score
- Support

**4. Training Loss Comparison**

Visualize the training loss across epochs to understand and compare the learning behavior of both architectures.

**5. Performance Visualization**

Generate graphical comparisons of CNN and LSTM accuracy and training loss.

## Project Workflow

1. Import required libraries.
2. Load and preprocess the MNIST dataset.
3. Create training and testing DataLoaders.
4. Visualize sample handwritten images.
5. Build the CNN architecture.
6. Train and evaluate the CNN model.
7. Generate the CNN confusion matrix.
8. Build the Bidirectional LSTM architecture.
9. Train and evaluate the LSTM model.
10. Generate the LSTM confusion matrix.
11. Compare both models using accuracy and training loss.
12. Generate classification reports and performance visualizations.

## Installation and Setup

**1. Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/Handwritten-Digit-Recognition-CNN-vs-LSTM.git
```

**2. Navigate to the project directory**

```bash
cd Handwritten-Digit-Recognition-CNN-vs-LSTM
```

**3. Install the required dependencies**

```bash
pip install torch torchvision numpy pandas matplotlib scikit-learn jupyter
```

**4. Launch Jupyter Notebook**

```bash
jupyter notebook
```

**5. Open the notebook**

Open `RNN AND CNN (MINOR PROJECT).ipynb` and execute the cells sequentially.

The MNIST dataset will be downloaded automatically when the dataset-loading cells are executed.

The implementation automatically detects whether CUDA is available and otherwise uses the CPU.

## Project Structure

```text
Handwritten-Digit-Recognition-CNN-vs-LSTM/
│
├── RNN AND CNN (MINOR PROJECT).ipynb
│
├── data/
│   └── MNIST dataset (downloaded automatically)
│
└── README.md
```

## Key Learning Outcomes

Through this project, I explored:

- Understanding CNN architecture and spatial feature extraction.
- Understanding RNNs and LSTM-based sequential learning.
- Implementing Bidirectional LSTM networks using PyTorch.
- Image preprocessing and normalization.
- Model training, optimization, and loss calculation.
- Evaluating classification models using multiple metrics.
- Understanding confusion matrices and classification reports.
- Comparing different deep learning architectures on the same dataset.

## Future Improvements

- Implement image prediction on custom handwritten digits.
- Add visualization of CNN feature maps and learned representations.
- Experiment with different CNN and LSTM architectures.
- Introduce data augmentation to improve generalization.
- Develop a user interface for uploading handwritten digit images.
- Explore hybrid CNN-LSTM architectures.

## Conclusion

This project provides a comparative understanding of two deep learning approaches for handwritten digit recognition.

CNN focuses on extracting spatial features directly from images, whereas Bidirectional LSTM processes image rows as sequential data and learns dependencies in both directions.

By implementing, training, and evaluating both architectures, the project demonstrates how different neural network architectures can approach the same image classification problem.

---

**Developed as a Minor Project | Deep Learning | Computer Vision | PyTorch**
