# ANPR-TFOD-and-OCR
### Problem Statement:
Traffic controlling, Identifying which vehicle entered the premises of an organisation at what time and left. Detection of vehicle licence plate and extracting the text within it.

### _Phases of the project_
### 1. Licence plate detection
---
**Dataset Used:** https://www.kaggle.com/andrewmvd/car-plate-detection

Custom object detection model trained using tensorflow object detection module using.

**PRETRAINED_MODEL_NAME** = ```ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8```

**PRETRAINED_MODEL_URL** = 'http://download.tensorflow.org/models/object_detection/tf2/20200711/ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz'

<img align="left" src='README files/base_image.jpg' width="400" alt='base image for deteciton'>
<img src='README files/image_detection.JPG' width="400" alt = 'detected licence plate'>

### 2. Licence plate region extraction
---
The detected region of licence plate is extracted which we'll further use to extract text from the licence plate and store the image in database.<br>

<img align="left" src='README files/detect1 (1).jpg' width="300" alt='detected licence plate'>
<img align="left" src='README files/detect1 (2).jpg' width="300" alt='detected licence plate'>
<img src='README files/detect1 (4).jpg' width="300" alt='detected licence plate'>

### 3. Licence plate OCR
---
For the OCR part I've used easyocr an open source module in python that make the OCR process really simple all you need to do is get an image or the numpy matrix for the image and pass it the the easyocr and you'll get all the text available in the image with the bounding box of the text region.

<img src='README files/performing_ocr.JPG' width="400" alt='detected licence plate'>

**Problem:** As you can see there are also other text in the deteted licence plate. This might create problem with the correct licence number extraction form the image.

**Solution:** To solve this issue, All I had to do was check the region/bounding box that occupy more then 60% of the image region. And then returning the text result in that region.


### 4. Realtime licence plate detection, OCR and storing the value in database
---
The project also support realtime licence plate detection using a webcam or any other camera connected to the system.

### Summary
This project is capable of detecting and extracting licence plate numbers from an image. The detecte image and text is stored in the database. Also a csv file is generated for the record of all the licence plate image names and the extracted text licence plate.


### Tools and Technology used
- opencv-python
- Numpy
- csv
- tensorflow-gpu=2.3.0
- tensorflow object detection (object_detection)
- Pillow
- pyyaml
- protobuf
- matplotlib=3.2
- easyocr
- torch=1.9.1+cu102

**Model Trained on:** Nvidia GeForce GTX 1050Ti

| Version              | Python Version | Compiler  | Build tools | cuDNN | CUDA |
|----------------------|----------------|-----------|-------------|-------|------|
| tensorflow_gpu-2.3.0 | 3.5-3.8        | MSVC 2019 | Bazel 3.1.0 | 7.6   | 10.1 |