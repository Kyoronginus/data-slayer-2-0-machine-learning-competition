Data Slayer 2.0: Machine Learning Competition
Overview
This repository contains the code and resources developed for Data Slayer 2.0, a machine learning competition focused on creating a robust fall detection system. The project combines techniques in computer vision, data augmentation, and machine learning to train and evaluate models capable of detecting and classifying fall-related activities from images.

Objectives
The primary objective of this project is to develop a fall detection system that accurately identifies fall-related activities using image data. The system is intended to assist in applications like healthcare monitoring, elder care, and public safety by detecting critical events.

The project uses a combination of:

YOLOv8 (You Only Look Once): A state-of-the-art object detection model used for keypoint detection and pose estimation.
XGBoost Classifier: A gradient-boosting algorithm used to classify images based on extracted keypoints.
Albumentations Library: A high-performance data augmentation library to improve model generalization and performance.
Key Features
1. Data Preprocessing and Augmentation
Dataset Organization: The dataset is organized by subject and activity type, where each activity is labeled as either fall (1) or non-fall (0).
Augmentation: Extensive use of the Albumentations library to increase the diversity of training data. The augmentation pipeline includes:
Horizontal flips
Brightness and contrast adjustments
Small rotations, scaling, and translations
Augmented images are stored to disk or processed in-memory based on the workflow.
2. YOLOv8 Keypoint Detection
YOLOv8 is used to extract pose keypoints from input images. These keypoints represent the spatial positions of human joints, which are critical for fall detection.
A lightweight YOLOv8n-pose model is employed for efficient and accurate keypoint detection.
The keypoints serve as input features for downstream classification.
3. Machine Learning Model (XGBoost Classifier)
The keypoints extracted by YOLOv8 are fed into an XGBoost classifier to distinguish between fall and non-fall activities.
Features are scaled and normalized as part of the preprocessing pipeline for optimal model performance.
The classifier is trained on a train-test split of the dataset, with an emphasis on stratified sampling to maintain class balance.
