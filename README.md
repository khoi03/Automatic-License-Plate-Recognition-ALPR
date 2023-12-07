# Automatic-License-Plate-Recognition-ALPR

<sub> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1EYOb6wNegfWFNEKebrli7mneMyn9aVgY?usp=sharing)
</sub>

## Introduction
Our objective is the development of an Automatic License Plate Recognition (ALPR) system designed to identify various vehicles and their corresponding license plates. The system is intended to process input in the form of videos or images containing vehicles. The desired output entails the detection of vehicles and license plates, with the results prominently displayed on the respective video.
  
## Table of contents:

1. [Approach](https://github.com/khoi03/Automatic-License-Plate-Recognition-ALPR#1approach)

2. [Overview results](https://github.com/khoi03/Automatic-License-Plate-Recognition-ALPR#2overview)
     

## 1. Approach
In this task, I incorporate the use of the YOLOv8 model, Warped Planar Object Detection Network, WPOD-NET for short(you can find their paper [here](https://openaccess.thecvf.com/content_ECCV_2018/papers/Sergio_Silva_License_Plate_Detection_ECCV_2018_paper.pdf) and the implementaion in Torch [here](https://github.com/Pandede/WPODNet-Pytorch)) and PaddleOCR model.
- Firstly, we commence by detecting all vehicles in the frame/image
- Next step is to identify the license plate of each vehicle. WPOD-NET excels in its ability to recognize license plates from diverse countries and license plates of different vehicles with high confidence scores.
  <table>
    <tr>
        <td> Example </td>
        <td> <img src="./docs/sample/original/03009.jpg" width="300px"></td>
        <td> <img src="./docs/sample/original/03016.jpg" width="300px"></td>
        <td> <img src="./docs/sample/original/03025.jpg" width="300px"></td>
    </tr> 
    <tr>
        <td> Confidence </td>
        <td> 0.9841 </td>
        <td> 0.9945 </td>
        <td> 0.9979 </td>
    </tr>
  </table>
  
- Eventually, we rectify the license plate from the frame/image using perspective transformation and input it into the PaddleOCR to get the final license plate number.
