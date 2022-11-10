# webcam-detectron2
ECGR-6119: Applied AI Midterm - Michael Campo

## Objective: 
Implement a simple solution to run Detectron Mask R-CNN algorithm for object detection and instance segmentation with webcam. The ouptut feed must be in real time and visualized using matplotlib.

## Steps: 
1. Cloned Detectron2 repository and installed requirements 
2. Created Detector class to handle all functions and inputs
3. Using "model_zoo" from the Detectron2 folder, models were selected for detection tasks. For instance segmentation, **_mask_rcnn_R_50_FPN_3_** was used since it has the fastest inference time and training of the models available. Information regarding the models can be found [here](https://github.com/facebookresearch/detectron2/blob/main/MODEL_ZOO.md). Dependent on the key passed, a predictor will be created to perfrom detection
4. A webcam function was created to display the inferred results in real time. OpenCV2 is used to begin reading frames from the webcam. While frames are being read, each frame gets predicted by the Model and passed through the visualizer to draw on prediction mask. The final predicted frame is then converted into RGB to be displayed on Matplot.
5. To output a video using Matplotlib, the interactive mode **_plt.ion()_** was used. Each predicted frame is set into an image array and then is re-drawn for every new frame using the **_plt.draw()_** function. New frames caputred from the webcam will be continuously predicted and displayed until the loop is broken using **ctrl+C** in the terminal.

## Results:
Run the [**webcam_detectron2.py**](https://github.com/mcampo21/webcam-detectron2/blob/main/webcam_detectron2.py) file. Detector mode can be chosen by setting **_model_type_** to one of the following string abbreviations:
* OD = Object Detection
* IS = Instance Segmentation
* PS = Panoptic Segmentation
* KD = Keypoint Detection

### Instance Segmentation Example:
<img src="https://github.com/mcampo21/webcam-detectron2/blob/main/example_capture.png" width = "777" >
