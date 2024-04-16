# object detection using AI

## Project Overview:
### This project focuses on performing object detection using AI techniques. The goal is to detect and localize objects within images and videos using the YOLO (You Only Look Once) algorithm. The project utilizes Google Colab for its computational resources and leverages the Ultralytics library for implementing the YOLO algorithm.

## Instructions:
## 1.Mount Google Drive: 
#### Mount the Google Drive to access and save project files.
```
from google.colab import drive
drive.mount('/content/drive')
```

## 2.Install Ultralytics: 
#### Install the Ultralytics library to facilitate object detection tasks.

```
!pip install ultralytics

```


## 3.Navigate to Project Directory: 
#### Change the current directory to the location of the project files.

```
%cd /content/drive/MyDrive/kaggle/Kaggal_1

```

## 4.Train the Model: 
#### Train the YOLOv8s model using the specified configuration file (data_.yaml), with 2 epochs and an image size of 500x500 pixels. Optionally, plots can be generated during training for visualization.

```
!yolo task=detect mode=train model=yolov8s.pt data=data_.yaml epochs=25 imgsz=500 plots=True

```

## 5.Validate the Model: 
#### Validate the trained model using the specified validation data and model weights.

```
!yolo task=detect mode=val model=/content/drive/MyDrive/kaggle/Kaggal_1/runs/detect/train13/weights/best.pt data=data_.yaml

```

## 6.Perform Prediction: 
#### Perform object detection prediction using the trained model and specified configuration. Objects with a confidence threshold of 0.25 or higher will be detected in the provided test images.

```
!yolo task=detect mode=predict model=/content/drive/MyDrive/kaggle/Kaggal_1/runs/detect/train13/weights/best.pt conf=0.25 source=/content/drive/MyDrive/kaggle/Kaggal_1/test/test/images data=data_.yaml

```

## 7.Alternate Prediction Method: 
#### Alternatively, perform object detection prediction using a different YOLO model (yolov8n.pt) and a video source.

```
%cd /content/drive/MyDrive/kaggle/
!yolo task="detect" mode=predict model=yolov8n.pt conf=0.25 source="/content/drive/MyDrive/kaggle/WhatsApp Video 2024-02-05 at 15.34.05.mp4"

```

<img width="601" alt="Screenshot 2024-04-16 at 3 22 01 PM" src="https://github.com/itixa/object_detection/assets/102657153/b5479364-48d7-4770-8780-d9718a11de41">

## Note: 
#### Adjust the paths, model names, configuration files, and other parameters as necessary for your specific project setup and requirements. Ensure that the necessary files and directories are correctly configured and accessible within your Google Drive.


