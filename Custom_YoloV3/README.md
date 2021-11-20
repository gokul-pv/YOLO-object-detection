# YoloV3 Training on Custom dataset

> Full credit goes to [this](https://github.com/ultralytics/yolov3), and if you are looking for much more detailed explanation and features, please refer to the original [source](https://github.com/ultralytics/yolov3).

## Data Collection

Download the dataset from [here](https://drive.google.com/file/d/1sVSAJgmOhZk6UG7EzmlRjXfkzPxmpmLy/view) and collect additional 100 images with Creative common license for the below classes (25 images per class):

- hardhat
- vest
- boots
- mask

## Data Annotation

Use the annotation tool from this [repo](https://github.com/miki998/YoloV3_Annotation_Tool). The installation steps are mentioned in the repo. Using the tool annotate the images with bounding boxes. These 100 images are then merged with the above dataset.

![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/annotation.PNG)

```
data
  --customdata
    --images/
      --img001.jpg
      --img002.jpg
      --...
    --labels/
      --img001.txt
      --img002.txt
      --...
    custom.data #data file
    custom.names #class names
    custom.txt #list of name of the images the network to be trained on. Currently we are using same file for test/train
```

Create **custom.data** file. For 4 class example, your file will look like this:

```
classes=4
train=data/customdata/train.txt
valid=data/customdata/test.txt
names=data/customdata/custom.names
```

Add the image name to the train.txt and test.txt. This is how our file looks like (please note the .s and /s):

```
./data/customdata/images/img001.jpg
./data/customdata/images/img002.jpg
./data/customdata/images/img003.jpg
...
```

You need to add custom.names file like  this:

```
hardhat
vest
mask
boots
```

## Model Training

- Creat a folder 'weights' in the root (YoloV3) folder and copy the 'yolov3-spp-ultralytics.pt' file downloaded from [link](https://drive.google.com/open?id=1LezFG5g3BCW6iYaV89B2i64cqEUZD7e0)

- In 'yolov3-custom.cfg' file, change the following

  - 'filters=255' to ((4 + 1 + (No of classes))*3)  = 27
  - classes=80 to classes = 4
  - burn_in to 100
  - max_batches to 5000
  - steps to 4000,4500

  

### A Collage of Training images

![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/train_batch0.png)



### Logs

![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/results.png)



## Result

### Inference on 16 Images (4 for each class):



| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj1_003.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj1_015.jpg) |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj1_016.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj1_024.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj2_001.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj2_003.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj2_006.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj2_009.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj3_001.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj3_011.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj3_017.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj3_023.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj4_008.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj4_009.jpg) |
| ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj4_015.jpg) | ![](https://github.com/gokul-pv/EVA6_Assignments_Session11/blob/main/Custom_YoloV3/YoloV3/output_images/custom_obj4_016.jpg) |



### Inference on Video uploaded to YouTube 

[![Link](https://img.youtube.com/vi/C0aGKyuvNkw/0.jpg)](https://youtu.be/C0aGKyuvNkw)



## References

1. https://arxiv.org/abs/1804.02767
2. https://paperswithcode.com/method/yolov3
