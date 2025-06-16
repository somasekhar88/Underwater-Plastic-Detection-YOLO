# YOLO Underwater Plastic Detection

This project implements YOLOv8 and YOLOv10 models for detecting underwater plastic debris. It includes Jupyter notebooks for training and inference, using real-world images from the JAMSTEC Deep-Sea Debris Database (via Roboflow).

## Table of Contents

1. Overview  
2. Installation  
3. Directory Structure  
4. Dataset Setup  
5. Available Models  
6. Training  
7. Inference  
8. Customization  
9. References

---

## Overview

- Models used: YOLOv8-s/l and YOLOv10-s/l  
- Performance evaluated using mAP50, mAP50–95, IoU, Precision, Recall  
- YOLOv10-s showed the best trade-off between accuracy and computational efficiency  
- Trained on a curated set of 1,200 underwater images (annotated for plastic detection)

---

## Installation

Install the required packages:

```
pip install ultralytics numpy opencv-python jupyter
```

To launch Jupyter Notebook:

```
jupyter notebook
```



## Directory Structure

```
yolo-underwater-plastic/
│
├── Models/
│   ├── yolov8s.pt
│   ├── yolov8l.pt
│   ├── yolov10s.pt
│   └── yolov10l.pt
│
├── Data/
│   ├── train/
│   ├── test/
│   ├── valid/
│   └── data.yaml
│
├── Train_Yolo_v8s.ipynb
├── Train_Yolo_v8l.ipynb
├── Train_Yolo_v10s.ipynb
├── Train_Yolo_v10l.ipynb
├── inference.ipynb
└── README.md
```

---

## Dataset Setup

This project uses a dataset derived from the JAMSTEC Deep-Sea Debris Database, available via Roboflow.

**Download here:**  
[Roboflow – Underwater Plastic Detection Dataset](https://universe.roboflow.com/yolov8yolov10comparision/underwaterplasticdetection-9ojxt)

Extract the dataset into the following structure:

```
Data/
├── train/
│   ├── images/
│   └── labels/
├── test/
│   ├── images/
│   └── labels/
├── valid/
│   ├── images/
│   └── labels/
└── data.yaml
```

Ensure your `data.yaml` file is correctly configured with paths and class names.

---

## Available Models

| Model       | Type  | Notes                         |
|-------------|-------|-------------------------------|
| YOLOv8s.pt  | Small | Fast, lightweight             |
| YOLOv8l.pt  | Large | More accurate, heavier        |
| YOLOv10s.pt | Small | Best accuracy/efficiency      |
| YOLOv10l.pt | Large | Higher compute, good accuracy |

---

## Training

Prepare the dataset as described above.

Open a training notebook:
- `Train_Yolo_v8s.ipynb`
- `Train_Yolo_v10s.ipynb`

Each notebook includes:
- Loading data  
- Model configuration  
- Training loop  
- Evaluation and visualization  

You can adjust the following training parameters:
- Number of epochs  
- Batch size  
- Image size  
- Learning rate  
- Optimizer type  

---

## Inference

To perform inference on new images, open `inference.ipynb`:

- Load a trained model  
- Select an input image  
- Run predictions and visualize results  

You can extend the notebook to:
- Process multiple images  
- Integrate with pipelines or automation  

---

## Customization

You can customize the project by:
- Retraining with a new dataset by updating `data.yaml`  
- Adding or swapping YOLO model versions in the `Models/` folder  
- Modifying training hyperparameters (learning rate, epochs, etc.)  

---

## References

- Ultralytics YOLOv8 Documentation: https://docs.ultralytics.com/  
- YOLOv10 Paper: https://arxiv.org/abs/2405.14458  
- JAMSTEC Deep-Sea Debris Dataset: https://www.godac.jamstec.go.jp/dsdebris/e/  
- Roboflow Dataset Hosting: https://universe.roboflow.com/  
