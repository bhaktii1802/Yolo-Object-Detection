
# YOLOv5 Object Detection with Custom Dataset

This project implements object detection using the YOLOv5 architecture on a custom dataset sourced and managed via Roboflow. It showcases how to train a YOLOv5 model using custom image data, perform inference on test images, and fine-tune hyperparameters for optimal accuracy. The project runs in Google Colab and is ideal for anyone looking to get hands-on experience with real-time object detection.




![App Screenshot](https://raw.githubusercontent.com/bhaktii1802/Yolo-Object-Detection/main/d8ce0480-9ac0-11ea-8062-809a1b8bfab6.png)



## Installation


```bash
  # Clone the YOLOv5 repository
!git clone https://github.com/ultralytics/yolov5

# Install required dependencies
%cd yolov5
%pip install -qr requirements.txt
!pip install roboflow

```
    
## Features
We began by curating a custom dataset, specifically tailored for mask detection. Images were uploaded and manually labeled using Roboflow, a powerful data management and annotation platform. Using Roboflow’s intuitive annotation tool, we drew bounding boxes around faces in the images and classified them into two object classes: with_mask and without_mask. Roboflow’s interface made it seamless to assign class labels and export the dataset in the YOLOv5 format.

To improve model generalization and performance, we applied various data augmentation techniques within Roboflow. These included random rotations, flips, exposure adjustments, and noise addition—ensuring the model learns robust features under diverse conditions.

After finalizing the dataset, we downloaded it directly into the Colab environment using the Roboflow API. The dataset was organized into appropriate folders (train, valid, test) along with a pre-generated data.yaml file specifying class names and file paths—ensuring compatibility with YOLOv5's training pipeline.

The YOLOv5 repository was then cloned, and dependencies such as torch, opencv-python, and roboflow were installed. We used the yolov5s.pt pretrained weights as the base model and initiated training with the following parameters:

Image size: 416×416 pixels

Batch size: 4

Epochs: 100

Caching: Enabled to speed up training

During training, YOLOv5 automatically saved the best-performing model based on validation performance.

Once training was complete, we performed inference using the trained model on:

The test dataset provided by Roboflow

Additional unseen images

Custom image paths specified in the code

YOLOv5's detection script output images with bounding boxes and labels, highlighting whether the detected person was wearing a mask or not, along with confidence scores.

Overall, this project not only demonstrates how to build a mask detection model using state-of-the-art object detection techniques but also provides hands-on experience with real-world dataset preparation, annotation, augmentation, training, and evaluation.

This pipeline can be extended for various object detection use cases, especially in public safety, healthcare compliance, and surveillance systems.


## 🔧 Technologies Used

- Python

- YOLOv5

- Roboflow

- Google Colab



