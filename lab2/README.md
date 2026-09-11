# Assignment 2: Feature Extraction & Segmentation

This directory contains the implementations for Assignment 2 of the Computer Vision course. The assignment focuses on intermediate computer vision tasks involving line and circle detection using the Hough Transform, as well as global thresholding techniques and noise analysis.

All parts of the assignment are implemented in the `Computer_Vision_Assignment_2.ipynb` Jupyter Notebook.

## Structure

- **Notebook:** `Computer_Vision_Assignment_2.ipynb`
- **Images Used:**
  - `line_image.jpg` (Line Structure Detection)
  - `circle_image.jpg` (Robust Circle Detection)
  - `clean_image.jpg` (Noise and Thresholding Analysis)
  - `otsu_image.jpg` (Global Thresholding using Otsu's Method)

## Implementation Details

### Q1: Line Structure Detection using LoG and Hough Transform
- **Laplacian of Gaussian (LoG):** Implements a `log_response` function that applies Gaussian smoothing followed by a Laplacian filter.
- **Zero-Crossing Detection:** Detects edges via a custom `zero_crossing` function that searches for sign changes in a 3x3 neighborhood. The effect of applying two different thresholds (a low vs. high threshold) is compared to suppress weak responses.
- **Hough Transform:** Applies OpenCV's Probabilistic Hough Transform (`cv2.HoughLinesP`) to the generated edge maps, overlaying the detected linear structures onto the original image. Discusses the trade-off between dense edge maps and false detections.

### Q2: Robust Circle Detection using Hough Transform
- **Circle Detection:** Applies `cv2.HoughCircles` (using the Gradient method) to identify multiple circular objects of varying sizes.
- **Parameter Tuning:** Investigates the impact of varying the radius range (`min_radius`, `max_radius`) and the `param2` detection threshold. 
- **Evaluation:** Overlays the detected circles onto the original image and discusses the trade-offs of the parameter settings regarding false positives and missed detections.

### Q3: The Role of Noise in Image Thresholding
- **Simulating Noise:** Uses a custom `add_gaussian_noise` function to simulate image degradation on a clean image by adding Gaussian noise with a mean of 0 and varying standard deviations (e.g., $\sigma = 10$ and $\sigma = 50$).
- **Histogram Analysis:** Displays the spatial-domain images alongside their intensity histograms, visualizing how noise broadens and overlaps intensity peaks.
- **Global Thresholding:** Applies a standard global threshold to the noisy images and discusses the degradation of binarized segmentation output as noise increases.

### Q4: Global Thresholding using Otsu's Method
- **Otsu's Method from Scratch:** Implements Otsu's variance-based global thresholding algorithm entirely **from scratch** (`otsu_from_scratch`). 
- **Variance Calculation:** Computes the normalized histogram to extract probability distributions and iteratively calculates the between-class variance $\sigma_B^2(T)$ for all possible threshold values $T \in [0, 255]$.
- **Optimization:** Plots the between-class variance as a function of $T$, visually verifying the optimal threshold that maximizes $\sigma_B^2(T)$.
- **Segmentation & Evaluation:** Applies the optimal threshold to binarize the image, returning the foreground-background segmentation. Discusses the algorithm's performance on unimodal histograms and its sensitivity to significant illumination variations.
