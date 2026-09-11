# Computer Vision Assignments

Welcome to the Computer Vision course repository. This repository contains the implementations, experiments, and analysis for two major coursework assignments focusing on fundamental and advanced image processing and computer vision techniques.

## Repository Overview

The purpose of this repository is to practically implement theoretical computer vision concepts ranging from basic image filtering, interpolation, and edge detection to more advanced feature extraction methods like the Hough Transform and Otsu's thresholding. 

The implementations rely on a mix of standard libraries (like OpenCV and NumPy) and **from-scratch** implementations of foundational algorithms (e.g., custom convolutions, Otsu's method, nearest-neighbor interpolation, and Laplacian filters) as required by the assignment constraints.

## Assignments

| Assignment | Topic | Main Concepts |
|------------|-------|---------------|
| [Assignment 1](./Assignment_01) | Image Processing & Filtering | Image Resizing & Interpolation, Spatial & Frequency Domain Smoothing, Hybrid Images (Pyramids, FFT), Edge Detection (Sobel, Laplacian, Canny, LoG). |
| [Assignment 2](./lab2) | Feature Extraction & Segmentation | Line and Circle Detection (Hough Transform, LoG zero-crossings), Noise Analysis in Thresholding, Global Thresholding (Otsu's Method from scratch). |

## Repository Structure

```text
.
├── Assignment_01/
│   ├── Question 1/
│   │   ├── 01.ipynb
│   │   └── Lenna_(test_image).png
│   ├── Question 2/
│   │   ├── 02.ipynb
│   │   ├── Camerman.webp
│   │   └── Mandrill.webp
│   ├── Question 3/
│   │   ├── 03.ipynb
│   │   ├── cat.jpeg
│   │   ├── dog.webp
│   │   ├── einstein.webp
│   │   └── marilyn.jpeg
│   ├── Question 4/
│   │   ├── 04.ipynb
│   │   ├── collectible-coins.jpg
│   │   └── marilyn.jpeg
│   └── README.md
├── lab2/
│   ├── CV_2026_ASSIGNMENT_2 Updated.pdf
│   ├── Computer_Vision_Assignment_2.ipynb
│   ├── circle_image.jpg
│   ├── clean_image.jpg
│   ├── line_image.jpg
│   ├── otsu_image.jpg
│   └── README.md
└── README.md
```