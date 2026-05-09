# Lightweight Edge Detection Using Cellular Automata

## Overview

This project presents a lightweight edge detection model based on Cellular Automata (CA). The proposed approach uses XOR-based local neighborhood rules for detecting edges in digital images while maintaining low computational complexity.

The project compares the proposed Hybrid Cellular Automata model with traditional edge detection methods such as:

* Canny
* Sobel
* Prewitt

The work focuses on:

* Computational efficiency
* Noise robustness
* Real-time suitability
* Quantitative evaluation using BSDS500 ground truth dataset

---

# Key Features

* Lightweight XOR-based edge detection
* Hybrid CA model using Rule 150, Rule 170, and Rule 90
* Faster execution compared to traditional methods
* Noise robustness analysis
* Quantitative evaluation using standard metrics
* Comparison with Canny, Sobel, and Prewitt operators

---

# Technologies Used

* Python
* OpenCV
* NumPy
* Matplotlib
* SciPy
* Google Colab

---

# Cellular Automata Concept

In this project:

* Each image pixel is treated as a CA cell
* Binary values (0 or 1) represent cell states
* A 3×3 Moore Neighborhood is used
* XOR-based local rules generate edge outputs

The Hybrid CA model combines:

* Rule 150 → Strong edges
* Rule 170 → Structural edges
* Rule 90 → Diagonal edges

Fusion Formula:

```python
Hybrid = (r150 + r170 + r90) >= 1
```

---

# Workflow

## Step 1: Input Image

The input image is loaded from the dataset.

## Step 2: Grayscale Conversion

The image is converted into grayscale.

## Step 3: Gaussian Smoothing

Noise reduction is performed using Gaussian filtering.

## Step 4: Thresholding

The grayscale image is converted into binary form.

## Step 5: Sliding Window

A 3×3 sliding window moves across the image.

## Step 6: Moore Neighborhood

Neighboring pixels are extracted.

## Step 7: CA Rule Application

Rule 150, Rule 170, and Rule 90 are applied using XOR operations.

## Step 8: Hybrid Fusion

Outputs of all rules are combined to generate the final edge map.

---

# Dataset Used

## BSDS500 Dataset

The BSDS500 dataset was used for quantitative evaluation.

The dataset contains:

* Natural images
* Human-annotated ground truth edge maps

Evaluation was performed using pixel-wise comparison with ground truth images.

---

# Evaluation Metrics

The following metrics were used:

| Metric    | Description                          |
| --------- | ------------------------------------ |
| Accuracy  | Overall correctness                  |
| Precision | Correct detected edges               |
| Recall    | Ability to detect real edges         |
| F1 Score  | Balance between Precision and Recall |
| IoU       | Overlap with ground truth            |

---

# Experimental Results

## Quantitative Results

| Metric    | Hybrid CA | Canny  | Sobel  | Prewitt |
| --------- | --------- | ------ | ------ | ------- |
| Accuracy  | 82.65%    | 86.58% | 58.66% | 80.19%  |
| Precision | 5.33%     | 6.07%  | 4.37%  | 5.20%   |
| Recall    | 35.07%    | 28.00% | 76.88% | 40.60%  |
| F1 Score  | 8.80%     | 9.33%  | 8.13%  | 8.89%   |
| IoU       | 4.67%     | 4.97%  | 4.29%  | 4.72%   |

---

# Execution Time Analysis

| Method    | Average Execution Time |
| --------- | ---------------------- |
| Hybrid CA | 0.000303 sec           |
| Rule 170  | 0.000507 sec           |
| Rule 150  | 0.000506 sec           |
| Rule 90   | 0.000694 sec           |
| Prewitt   | 0.001108 sec           |
| Canny     | 0.003341 sec           |
| Sobel     | 0.004407 sec           |

The Hybrid CA model is approximately 11× faster than the Canny edge detector.

---

# Noise Robustness Analysis

Gaussian noise was added to test images.

Observations:

* Canny produced many false edges under noise
* Sobel and Prewitt showed significant degradation
* Hybrid CA preserved major structural edges effectively

---

# Advantages of Proposed Model

* No convolution required
* Low computational complexity
* XOR-based lightweight operations
* Inherently parallel architecture
* Suitable for FPGA and embedded systems
* Real-time processing capability

---

# Future Scope

* Adaptive CA rule generation
* Integration with deep learning models
* FPGA/GPU implementation
* Video and color image processing
* Improved precision optimization

---

# Project Structure

```text
project/
│
├── dataset/
├── results/
├── notebooks/
├── ca_edge_detection.py
├── evaluation.py
├── README.md
└── requirements.txt
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Run the Project

```bash
python ca_edge_detection.py
```

---

# Applications

* Medical image analysis
* Autonomous vehicles
* Remote sensing
* Surveillance systems
* Object recognition
* Embedded vision systems

---

# Author

David Shalom Sarvepalli

---

# Acknowledgement

I sincerely thank Dr. Mamata Dalui Chakraborty for her valuable guidance and support throughout this project.

---

# License

This project is intended for academic and research purposes.
