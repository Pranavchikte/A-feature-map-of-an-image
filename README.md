## Overview

This Python script demonstrates basic image processing techniques using NumPy, SciPy, and Matplotlib. The main tasks include applying an edge detection filter to an image and then reducing the image size by downsampling it.

The goal is to understand how filters work and how images can be transformed through manual pixel manipulation.

---

## What the Script Does

### 1. Load and Display an Image

The script starts by loading a sample image called "ascent" from the `scipy.misc` module. This is a grayscale image of a building commonly used for image processing demos. The image is then displayed using Matplotlib without any axes or gridlines for clarity.

### 2. Apply a Convolution Filter (Edge Detection)

A 3x3 Sobel filter is applied manually to the image. This filter is commonly used to detect vertical edges. Each pixel is replaced based on a weighted sum of itself and its 8 neighbors.

You can experiment with different filters by uncommenting or changing the values in the `filter` variable. Examples include:

```python
filter = [ [0, 1, 0], [1, -4, 1], [0, 1, 0] ]  # Laplacian filter
filter = [ [-1, 0, 1], [-2, 0, 2], [-1, 0, 1] ]  # Horizontal Sobel
```

### 3. Normalize and Clamp Output

The output of the filter is multiplied by a `weight` (default is 1). After that, the values are clamped between 0 and 255 to keep the pixel values valid for grayscale images.

### 4. Downsample the Image

To reduce the image size, the script takes 2x2 pixel blocks from the filtered image and selects the brightest pixel from each block. This helps retain the most prominent features (strongest edges) while reducing image dimensions by half.

---

## How to Run the Code

### Prerequisites

Make sure you have the following Python packages installed:

* numpy
* matplotlib
* scipy
* opencv-python

You can install them using pip:

```
pip install numpy matplotlib scipy opencv-python
```

### Running the Script

Save the script to a file, for example `edge_filter.py`, and run it using:

```
python edge_filter.py
```

You will see three output windows in sequence:

1. The original grayscale image
2. The edge-detected image
3. The downsampled version of the edge-detected image

---

## Key Concepts Covered

* Convolution filtering (edge detection)
* Manual manipulation of image pixels
* Downsampling (image compression)
* Visualization using matplotlib

---

## Suggestions for Practice

* Try changing the filter values to see how the output changes.
* Add horizontal and diagonal filters.
* Apply a normalization step if the filter sum is not 1 or 0.
* Convert this into a function and try using it on different images using OpenCV.

---
