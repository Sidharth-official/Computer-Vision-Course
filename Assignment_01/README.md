# Assignment 1: Image Processing & Filtering

This directory contains the implementations for Assignment 1 of the Computer Vision course. The assignment explores fundamental image processing techniques across four distinct questions, heavily emphasizing mathematical implementations from scratch alongside standard OpenCV functions.

## Structure

- **Question 1:** Image Resizing, Interpolation, and Edge Analysis (`01.ipynb`)
- **Question 2:** Image Smoothing (`02.ipynb`)
- **Question 3:** Hybrid Images (`03.ipynb`)
- **Question 4:** Edge Detection and Analysis (`04.ipynb`)

## Implementation Details

### Q1: Image Resizing, Interpolation, and Edge Analysis
Implemented in `Question 1/01.ipynb`.
- **Image Resizing:** Loads a standard image (Lenna), downsamples it to 256×256 and 128×128.
- **Interpolation Techniques:** Upsamples the images back to 512×512 using three methods:
  - **Nearest-Neighbour:** Implemented **from scratch**.
  - **Bilinear & Bicubic:** Implemented using OpenCV (`cv2.INTER_LINEAR`, `cv2.INTER_CUBIC`).
- **Evaluation:** Evaluates the reconstructions using Mean Squared Error (MSE) and Peak Signal-to-Noise Ratio (PSNR). Visualizes the pixel-wise absolute-error and squared-error maps.

### Q2: Image Smoothing
Implemented in `Question 2/02.ipynb`.
- **Noise Addition:** Applies Salt-and-Pepper noise to an image with fine details, and Gaussian noise to a smoother image.
- **Filtering:** Implements smoothing filters (Box, Weighted-average, Gaussian, and Median). The `apply_filter_scratch` function implements a custom 2D convolution from scratch for the Box and Weighted-average kernels, applied across multiple kernel sizes.
- **Evaluation:** Extracts absolute-difference images and calculates MSE and PSNR for all filter configurations.
- **Mixed-Noise Smoothing:** Creates a combined image with Salt-and-Pepper noise on the left and Gaussian noise on the right, applying a region-wise approach (Median filter for the left, Gaussian filter for the right) to optimally denoise it.

### Q3: Hybrid Images
Implemented in `Question 3/03.ipynb`.
- **Image Alignment:** Applies rigid affine transformations (rotation, scaling, translation) to align features (e.g., facial features) of two images.
- **Spatial Domain Hybrid:** Generates hybrid images using a Gaussian Low-Pass Filter (LPF) and extracts High-Pass Filter (HPF) components by subtracting the LPF from the original image.
- **Frequency Domain Hybrid:** Implements hybrid image generation in the frequency domain using the 2D Fast Fourier Transform (FFT), custom Gaussian masks, and IFFT. Compares execution times between the spatial and frequency domains.
- **Pyramids Blending:** Constructs Gaussian and Laplacian pyramids to seamlessly blend the high and low-frequency components of the images. Optionally uses a Bilateral Filter for pyramid construction.

### Q4: Edge Detection and Analysis
Implemented in `Question 4/04.ipynb`.
- **First-Order Derivatives (Sobel):** Computes $x$ and $y$ gradients, magnitude, and direction using a **fast from-scratch 2D convolution** (`convolve_3x3_fast`). Evaluates three different threshold values to generate binary edge maps.
- **Second-Order Derivatives (Laplacian):** Computes the Laplacian of the image using an 8-neighbor discrete kernel implemented from scratch. 
- **Advanced Edge Detectors:** Compares the from-scratch implementations against Laplacian of Gaussian (LoG) and Canny edge detectors.
- **Evaluation:** Discusses the effectiveness of each edge detection technique regarding edge localization, continuity, and response to fine details.
