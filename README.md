# Object detection using YOLO


## Part  A: OpenCV -Yolo [(Click here)](./OpenCV_YoloV3)

- Follow the steps listed mentioned [here](https://pysource.com/2019/06/27/yolo-object-detection-using-opencv-with-python/)
- Take a image with object which is there in COCO data set (search for COCO classes to learn).
- Run this image through the code above
- Upload the imaged annotated by above code.



## Part B: Training Custom Dataset on YoloV3 [(Click here)](./Custom_YoloV3)

- Download [this](https://drive.google.com/file/d/1sVSAJgmOhZk6UG7EzmlRjXfkzPxmpmLy/view) dataset
- Collect and add 25 images for the following 4 classes into the dataset shared:
  - class names are hardhat, vest, mask and boots, its is listed in custom.names file
- Once additional 100 images are added, train the model

Once done then,

- Download a very small (~10-30sec) video from YouTube which shows the 4 classes.

- Use ffmpeg to extract frames from the video.

- Infer on these images using detect.py file.

  ```python
  python detect.py --conf-three 0.3 --output output_folder_name
  ```

- Use  ffmpeg  to convert the files in your output folder to video

- Upload the video to YouTube.

- Also run the model on 16 images that you have collected (4 for each class)
