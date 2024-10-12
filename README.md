# Object Detection and Tracking

This project implements a real-time object detection and tracking system using deep learning model and OpenCV. The primary focus is on detecting people in a video file and tracking their movement within a defined region of interest (ROI).

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)

## Introduction

This project utilizes a pre-trained object detection model to identify and track people in a video stream. The system draws bounding boxes around detected individuals, assigns unique IDs, and counts the number of people present in a specified area. It can be applied in various scenarios, such as monitoring crowded spaces or counting attendees in events.

## Features

- Real-time object detection using different deep learning models such as Faster RCNN, SSD, RetinaNet, YOLO model.
- Tracking of detected individuals with unique IDs.
- Visualization of detected objects and their IDs on the video feed.
- Counting of individuals within a defined region of interest (ROI).
- Display of warnings when the count exceeds a specified threshold.

## Requirements

To run this project, ensure you have the following packages installed:

- Python 3.x
- OpenCV
- PyTorch
- NumPy

You can install the required packages using pip:

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
- View results: The program will open a window showing the video with detected objects and their tracking IDs, along with a warning if the count exceeds a specified limit.

## How It Works
The script loads a pre-trained such as Faster R-CNN model from TorchVision.
It captures frames from the specified video file.
The model detects objects in each frame, and the Tracker class assigns unique IDs to the detected objects.
The detected objects are tracked based on the proximity of their center points, and the tracking information is displayed on the video frames.
### Key Components
- Model Initialization: The model is initialized using fasterrcnn_resnet50_fpn with pre-trained weights.
- Object Detection: The model processes video frames to detect objects.
- Tracking: The Tracker class keeps track of detected objects by calculating the center points of their bounding boxes.
## Code Explanation 
### Tracker Class
The Tracker class is responsible for tracking detected person objects based on the proximity between their center points. It maintains a dictionary of center points and assigns unique IDs to each detected individual.
- Initialization:
  center_points: Stores the center coordinates of tracked objects.
  id_count: A counter for generating unique IDs.
- Update Method:
  Takes a list of bounding boxes, calculates their center points, and updates or assigns IDs based on proximity.

### Object Detection and Tracking Loop
- Region of Interest: Defined as a polygon to focus tracking efforts.
- Video Processing: Continuously reads frames, performs object detection, and updates the tracker.
- Counting: Maintains a count of detected individuals within the ROI and displays results in the video feed.
