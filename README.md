# Overloaded-passenger-detection-tracking
# Object Detection and Tracking

This project implements real-time object detection and tracking using Faster R-CNN with a ResNet50 backbone. It utilizes the PyTorch library along with OpenCV for video processing.

## Table of Contents
- [Overview](#overview)
- [Requirements](#requirements)
- [Usage](#usage)
- [How It Works](#how-it-works)

## Overview

The code captures video input and detects objects (specifically people) in real-time using different pre-trained object detection-based model such as Faster R-CNN, YOLO, RetineNet, SSD model. It tracks detected objects based on their bounding boxes and maintains unique IDs for each detected object.

## Requirements

To run this project, you'll need the following libraries:

- Python 3.x
- OpenCV
- PyTorch
- TorchVision
- NumPy

You can install the required libraries using pip:

```bash
pip install opencv-python torch torchvision numpy
```

## Usage
- Clone the repository.
- Prepare your video: Ensure you have a video file for detection. Update the path in the code where it reads the video:
```bash
cap = cv2.VideoCapture('path_to_your_video.mp4')
```
- Run the script: Execute the script in your Python environment.
- View results: The program will open a window showing the video with detected objects and their tracking IDs.

## How It Works
The script loads a pre-trained such as Faster R-CNN model from TorchVision.
It captures frames from the specified video file.
The model detects objects in each frame, and the Tracker class assigns unique IDs to the detected objects.
The detected objects are tracked based on the proximity of their center points, and the tracking information is displayed on the video frames.
### Key Components
- Model Initialization: The model is initialized using fasterrcnn_resnet50_fpn with pre-trained weights.
- Object Detection: The model processes video frames to detect objects.
- Tracking: The Tracker class keeps track of detected objects by calculating the center points of their bounding boxes.
