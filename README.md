# Low-Light Face Detection

This repository contains a Python implementation of a low-light face detection algorithm based on the paper "Single-stage Face Detection under Extremely Low-light Conditions" by Jun Yu, Xinlong Hao, and Peng He.

## Overview

The algorithm consists of three main components:

1. **Image Enhancement**: The Multi-Scale Retinex with Color Restoration (MSRCR) algorithm is used to enhance low-light images, improving contrast and visibility.

2. **Face Detection**: A PyramidBox-like model is used for face detection. It combines contextual information and facial features to handle small, blurred, and occluded faces effectively.

3. **Multi-Scale Testing and Soft-NMS**: Multi-scale testing is performed to detect faces of different scales, and Soft-NMS is applied to integrate the detection results.

## Requirements

- Python 3.x
- OpenCV
- NumPy

## Usage

1. Clone the repository or download the source code.
2. Update the `image_path` variable in the `detect_faces` function with the path to your input image.
3. Run the `detect_faces` function with the desired image path:


image_path = './dataset/5.png'  # Update with your image path
detect_faces(image_path)
The script will load the input image, perform low-light image enhancement, face detection, and display the original and enhanced images with detected faces highlighted.

## Functions
msrcr_enhancement(image, sigma_list=(15, 80, 250))
This function implements the Multi-Scale Retinex with Color Restoration (MSRCR) algorithm for low-light image enhancement. It takes an input image and a list of sigma values (default: [15, 80, 250]) for the Gaussian blur and returns the enhanced image.
soft_nms(boxes, scores, threshold=0.3, sigma=0.5)
This function performs Soft Non-Maximum Suppression (Soft-NMS) on the detected bounding boxes and their corresponding scores. It takes a list of bounding boxes, a list of scores, a threshold value (default: 0.3), and a sigma value (default: 0.5). It returns the selected bounding boxes and their corresponding scores after applying Soft-NMS.
calculate_iou(box1, box2)
This function calculates the Intersection over Union (IoU) between two bounding boxes. It takes two bounding boxes as input and returns their IoU value.
detect_faces(image_path)
This is the main function that performs low-light face detection on the input image. It loads the image, applies MSRCR enhancement, detects faces using a pre-trained face detector, applies Soft-NMS to the detected bounding boxes, and displays the original and enhanced images with the detected faces highlighted.

## Contributing
Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## Acknowledgments
This implementation is based on the research paper "Single-stage Face Detection under Extremely Low-light Conditions" by Jun Yu, Xinlong Hao, and Peng He. Please cite their work if you use this code for academic or commercial purposes.
