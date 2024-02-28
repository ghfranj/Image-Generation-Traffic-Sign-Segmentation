# Image-Generation-Traffic-Sign-Segmentation
This repo is for detecting and segmenting traffic signs using mask-RCNN in MMDetection library

Pre-trained detection models such as Mask R-CNN detect and segment objects of fixed classes, including stop signs

It is proposed to train the selected model to segment 8 types of signs on the Russian road signs data set https://www.kaggle.com/datasets/viacheslavshalamov/russian-road-signs-segmentation-dataset containing 100,000 images of Russian road signs (the segmentation set is built on based on the detection data set https://graphics.cs.msu.ru/projects/traffic-sign-recognition.html ).

Pre-trained models can be used from the MMDetection library https://github.com/open-mmlab/mmdetection, or you can try YOLOv8 Testing should be carried out on 10 photographs of streets with road signs, taken independently near ITMO University, if it is impossible for good reasons, then in other recognizable places - these photographs with predicted segmentation will need to be shown to the inspector.

The quality of segmentation is assessed using the metrics IoU, Precision, Recall, L2 separately on the validation part of the Russian road signs image set and photographs taken, also interested in the percentage of images in which IoU >= 0.5, IoU >= 0.75, IoU >= 0.9

1- Dataset used:
~~~
!kaggle datasets download -d viacheslavshalamov/russian-road-signs-segmentation-dataset
~~~
2- MMDetection model:
~~~
!mim download mmdet --config mask-rcnn_r50-caffe_fpn_ms-poly-3x_coco --dest ./checkpoints
~~~
3- Training:
~~~
!python tools/train.py {config}
~~~
4- Example of training results:
![image](https://github.com/ghfranj/Image-Generation-Traffic-Sign-Segmentation/assets/98123238/5830578b-c778-4244-b455-2f4e00420f6e)
