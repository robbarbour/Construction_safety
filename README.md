# Construction Site Safety Detection with YOLOv8

This repository contains code for training and evaluating a YOLOv8 model to detect safety compliance on construction sites. The model is trained on a dataset of construction site images, and can detect the following objects:

* Hardhat
* Mask
* NO-Hardhat
* NO-Mask
* NO-Safety Vest
* Person
* Safety Cone
* Safety Vest
* machinery
* vehicle

## Dataset

The dataset used for training and evaluation is the Construction Site Safety Image Dataset from Roboflow. The dataset contains images of construction workers in various safety scenarios, and is annotated with bounding boxes for the objects listed above.

## Model

The model used is YOLOv8n, a small and efficient object detection model. The model is trained for 30 epochs with a batch size of 32.

## Evaluation

The trained model achieves a mAP of 0.753 on the test set. The model is also evaluated on a number of individual classes, and achieves high accuracy on most classes.

## Usage

To train the model, run the following command:

yolo task=detect mode=train model=yolov8n.pt data=/kaggle/working/data.yaml epochs=30 batch=32 imgsz=640 name=yolov8n_v1_train


To evaluate the model, run the following command:

yolo task=detect mode=val model=runs/detect/yolov8n_v1_train/weights/best.pt data=/kaggle/working/data.yaml


To predict on new images, run the following command:

yolo task=detect mode=predict model=runs/detect/yolov8n_v1_train/weights/best.pt source=/path/to/images


## Results

The following images show the results of the trained model on a number of test images.

![image](https://github.com/user-attachments/assets/c4a8acc7-7c46-469a-b380-92f9c551429f)



## Conclusion

The YOLOv8 model is able to effectively detect safety compliance on construction sites. T
