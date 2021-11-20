## What  is  YOLO

YOLO is a deep learning algorithm , and for a algorithm to work it  needs a framework. YOLO came out on may 2016 and it became quickly so  popular because it’s so fast compared with the previous deep learning  algorithm. YOLO is able to detect object in only one pass, while other  need to scan images many times. Which makes it detect objects at a  relatively high speed. With a GPU we can able to process over 45  frames/second while with a CPU around a frame per second.

Three most used and known frameworks compatible with YOLO are:

1. Darknet: it’s the framework built from the developer of  YOLO and made specifically for yolo.

2. Darkflow: it’s the adaptation of darknet to Tensorflow (another deep learning framework).

3. OpenCV: also OpenCV has a deep learning framework that works with YOLO. Just make sure you have OpenCV 3.4.2 at least.

## How to use YOLO with OpenCV?

- Follow the steps listed mentioned [here](https://pysource.com/2019/06/27/yolo-object-detection-using-opencv-with-python/)
- Download YOLO V3 weights from this [path](https://pjreddie.com/media/files/yolov3.weights)
- Load the algorithm. To run the algorithm we need three files:
  - **Weight file:** it’s the trained model, the core of the algorithm to detect the objects.
  - **Cfg file**: it’s the configuration file, where there are all the settings of the algorithm.
  - **Name files:** contains the name of the objects that the algorithm can detect.
- Load the image where we want to perform the object detection and also get its width and height

Now that the algorithm is ready to work and  it’s time to pass the image into the network and do the detection.

### Input Image:

![ip](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/OpenCV_YoloV3/Input/Img_6.jpg)

### Output Image:

![op](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/OpenCV_YoloV3/Output/Img_6_annotated.png)



## Reference

- [https://pysource.com/2019/06/27/yolo-object-detection-using-opencv-with-python/](https://pysource.com/2019/06/27/yolo-object-detection-using-opencv-with-python/)



