# ANPR-TFOD-and-OCR
### Problem Statement:
Traffic controlling, Identifying which vehicle entered the premises of an organisation at what time and left. Detection of vehicle licence plate and extracting the text within it.

### _Phases of the project_
--
### 1. Licence plate detection
---
<b>Dataset Used:</b> https://www.kaggle.com/andrewmvd/car-plate-detection

Custom object detection model trained using tensorflow object detection module using.

<b>PRETRAINED_MODEL_NAME</b> = ```ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8```

<b>PRETRAINED_MODEL_URL</b> = 'http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz'

<img src='base_image.jpg' alt='base image for deteciton'>
<img src='README files/image_detection.JPG' alt = 'detected licence plate'>
