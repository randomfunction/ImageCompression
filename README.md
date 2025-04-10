# Image Compression using Singular Value Decomposition (SVD)

This project demonstrates how **Singular Value Decomposition (SVD)** can be used to compress grayscale images by retaining only the most significant singular values. The technique is implemented in Python using NumPy and skimage.

## Overview

- Load a high-resolution RGB image from the web
- Convert it to grayscale and resize to 256x256 for simplicity
- Apply SVD to decompose the image matrix
- Reconstruct compressed versions of the image using top `k` singular values
- Automatically find the optimal `k` based on:
  - **Energy retention ≥ 95%**
  - **SSIM ≥ 0.90**
- Visualize:
  - Original vs Compressed image
  - Singular values
  - Energy retention vs number of components `k`

## Compression Metrics

- **Energy Retention**: Measures how much of the image’s information is preserved using the top `k` singular values.
- **SSIM (Structural Similarity Index)**: Measures the perceptual similarity between the original and compressed image.

## Optimal `k` Selection

The script automatically selects the smallest `k` that satisfies both:
- Energy retention ≥ 95%
- SSIM ≥ 0.90

This balances image quality and compression efficiency.

## 📷 Example Output

| Original Image | Compressed Image |
|----------------|------------------|
| ![original](https://c4.wallpaperflare.com/wallpaper/757/318/501/nasa-universe-james-webb-space-telescope-hd-wallpaper-preview.jpg) | Generated by script |

> Note: The actual image used is converted to grayscale and resized in the script.

## Project Structure

IC_AdaptiveSVD.ipynb # Main script 
README.md # This file


## Requirements

- numpy
- matplotlib
- scikit-image

Install with:

```bash
pip install numpy matplotlib scikit-image
