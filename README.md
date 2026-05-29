# AI_Car — Autonomous Agricultural UGV with Vision-Based Navigation

An unmanned ground vehicle (UGV) for farming environments that navigates autonomously using a vision-based navigation system. The vehicle detects crop areas and navigable paths from camera input and generates its own steering and propulsion commands.

## Overview

This repository holds the computer vision and deep learning work for an autonomous agricultural UGV. The core of the system is a semantic segmentation pipeline that identifies obstacles and navigable terrain from images, which is then used to compute a steering angle for the vehicle.

The project is being developed as a final-year research project at the Department of Electrical and Electronic Engineering, University of Peradeniya.

## Objectives

- Build an autonomous platform that can navigate agricultural terrain on its own.
- Develop a vision framework for crop detection and path recognition.
- Handle real-world field conditions: variable lighting, weed interference, and uneven ground.
- Validate navigation performance through field trials.

## Approach

The system combines image processing, machine learning, and deep learning:

1. **Data preparation** — images are annotated with LabelMe, and the JSON annotations are converted to segmentation masks.
2. **Dataset splitting** — images and masks are split into training and test sets.
3. **Model training** — a U-Net convolutional network is trained for multi-class semantic segmentation using a Dice loss and data augmentation.
4. **Deployment** — the trained model is exported to TensorFlow Lite for on-device inference.
5. **Inference** — segmentation is run on video frames, and a steering angle is computed from the predicted navigable region.

## Repository Contents

| File | Description |
|------|-------------|
| `Farm_obstacles.ipynb` | U-Net model for farm obstacle segmentation (data prep, training, Dice loss, augmentation). |
| `obstacle_segmentation_pipeline.ipynb` | Full pipeline: data preparation, U-Net training, TFLite export, and video inference with steering angle prediction. |

## Tech Stack

- **Language:** Python (Jupyter / Google Colab)
- **Deep Learning:** TensorFlow / Keras, TensorFlow Lite
- **Computer Vision:** OpenCV, Pillow
- **Annotation:** LabelMe
- **Other:** NumPy, scikit-learn, Matplotlib

## Hardware (planned)

- Camera (primary navigation sensor)
- IMU
- GPS module

## Status

Ongoing research project with weekly progress documented across 24 weeks.

## Author

**Piyumal Rathnayaka** (E/20/334)
Department of Electrical and Electronic Engineering, University of Peradeniya
Email: e20334@eng.pdn.ac.lk

Project portfolio: https://sites.google.com/eng.pdn.ac.lk/student-portfolio/home
