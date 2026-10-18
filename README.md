# Object-Detection-project
Object Detection Project

A custom object detector trained with Ultralytics YOLO. We took photos of ourselves, labelled them, and trained a model that finds and names each of us in new images, videos and live webcam footage.

Table of contents
Overview
What is object detection?
How it works
Project structure
Getting started
Dataset
Training
Results
Running the model
Privacy and ethics
Limitations
Future work
Acknowledgements
Overview

Object detection answers two questions about an image at once: what is in it and where it is. The model draws a box around each detected object and gives it a label and a confidence score.

In this project the "objects" are the members of our team. We:

Collected photos of ourselves in different places, lighting and poses.
Labelled each person with a bounding box.
Trained a YOLO model on the labelled photos using machine learning.
Tested the model on images it had never seen.

Classes detected: [name1], [name2], [name3] (replace with your own)

What is object detection?

Object detection is a computer vision task. Unlike image classification, which gives one label for a whole picture, detection finds every object, draws a box around it, and labels it.

YOLO ("You Only Look Once") is a family of fast detectors that look at the whole image in a single pass. That makes it quick enough for live video. Ultralytics provides a simple Python package and command line for training and running YOLO models.

How it works
Photos  ->  Label (boxes)  ->  Train YOLO  ->  Validate  ->  Predict on new images / webcam
Collect photos of each person.
Annotate each photo with a box and a class name (we used [Roboflow / LabelImg / CVAT / Label Studio]).
Split the data into training and validation sets.
Train a pretrained YOLO model on our data (transfer learning), so it starts from what it already knows and learns our faces and appearance.
Validate to measure how well it detects people it has not memorised.
Predict on new images, videos or a webcam.
Project structure

Adjust to match your repository.

Object-Detection-project/
├── dataset/
│   ├── images/
│   │   ├── train/        # training photos
│   │   └── val/          # validation photos
│   └── labels/
│       ├── train/        # YOLO .txt label files
│       └── val/
├── data.yaml             # dataset paths and class names
├── train.py              # training script
├── predict.py            # run the trained model
├── runs/                 # training outputs (weights, charts)
├── requirements.txt
└── README.md
Getting started
Requirements
Python 3.9 or newer
A GPU is recommended for training but not required. Google Colab's free GPU works well.
