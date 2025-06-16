# YOLO Underwater Plastic Detection

This project implements YOLOv8 and YOLOv10 models for detecting underwater plastic objects. It includes Jupyter notebooks for training models and running inference on new images.

## Table of Contents

1. [Installation](#installation)
2. [Directory Structure](#directory-structure)
3. [Available Models](#available-models)
4. [Training](#training)
5. [Inference](#inference)
6. [Customization](#customization)

## 1. Installation

. Install the required packages:
   ```
   pip install ultralytics numpy opencv-python jupyter
   ```

## 2.. Launch Jupyter Notebook:
   ```
   jupyter notebook
   ```

## 3.  Directory Structure

The project contains the following files:

```
yolo-underwater-plastic/
│
├── Models/
│   ├── yolov8s.pt
│   ├── yolov8l.pt
│   ├── yolov10s.pt
│   └── yolov10l.pt
│
├── Train_Yolo_v8s.ipynb
├── Train_Yolo_v8l.ipynb
├── Train_Yolo_v10s.ipynb
├── Train_Yolo_v10l.ipynb
├── inference.ipynb
└── README.md
```

### Training Setup

If you want to train your own models, you need to set up your data directory with the following structure:

```
── Data/
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

Ensure that:
1. Your images are in the respective `images/` folders.
2. Corresponding label files are in the `labels/` folders.
3. The `data.yaml` file is properly configured with paths to your train, test, and validation sets.

## Available Models

This project includes the following pre-trained YOLO models:

- YOLOv8s (small)
- YOLOv8l (large)
- YOLOv10s (small)
- YOLOv10l (large)

These model files are provided in the `Models/` directory.

## Training

To train a model, follow these steps:

1. Set up your data directory as described in the [Training Setup](#training-setup) section.
2. Open one of the training notebooks:
   - `Train_Yolo_Models.ipynb`

Each notebook contains the necessary code to:

1. Load the dataset
2. Configure training parameters
3. Train the model
4. Validate the results

You can modify the training parameters within the notebook, such as:

- Number of epochs
- Image size
- Batch size
- Learning rate
- Optimizer

The notebook will display the number of images, label files, and annotations in your dataset before starting the training process.

## Inference

To run inference on new images, use the `inference.ipynb` notebook. This notebook allows you to:

1. Load a trained model
2. Select an input image
3. Run inference
4. Visualize the results

You can easily modify the notebook to process multiple images or integrate it into your own workflow.

## Customization

### Retraining with New Data

To retrain the model with your own data:

1. Organize your data following the directory structure mentioned in the [Training Setup](#training-setup) section.
2. Update the `data.yaml` file with the paths to your new dataset.
3. Modify the appropriate training notebook with your desired parameters.

### Modifying Model Architecture

If you want to use a different YOLO version or modify the model architecture:

1. Add the new model file to the `Models/` directory.
2. Create a new training notebook based on the existing ones.
3. Update the model loading code to use the new model.

### Adjusting Hyperparameters

You can modify various hyperparameters directly in the training notebooks, such as:

- Learning rate
- Optimizer
- Number of epochs
- Batch size
- Image size

Feel free to experiment with these parameters to optimize model performance for your specific use case.


---

For more information on YOLO models and the Ultralytics framework, visit [Ultralytics Documentation](https://docs.ultralytics.com/).
