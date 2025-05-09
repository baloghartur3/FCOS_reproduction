# FCOS_reproduction

This project implements a face detection model based on the FCOS (Fully Convolutional One-Stage Object Detection) architecture.

## Overview

The [FCOS.ipynb](FCOS.ipynb) notebook contains the following key components:

-   **Data Preparation**: Utilizes a custom `FacesDataset` class to load and preprocess face images and their bounding box annotations from the `data/faces.csv` file and `data/images/` directory.  The images are resized to 128x128 to ease resource needs.
-   **Model Architecture**: Implements a FCOS-like neural network (`FCOS_NN`) with a Feature Pyramid Network (FPN) backbone and three prediction heads (class, bounding box, and centerness).
-   **Training**: Trains the model using a combination of Binary Cross-Entropy (BCE) loss for classification and centerness prediction, and Smooth L1 loss for bounding box regression.
-   **Inference**: Implements an `inference_on_img_by_idx` function that performs inference on a given image, applies Non-Maximum Suppression (NMS) to filter overlapping bounding boxes, and visualizes the results.

## Dependencies

-   torch
-   matplotlib
-   numpy
-   pandas
-   PIL (Pillow)
-   torchvision
-   tqdm

## Usage

1.  Ensure all dependencies are installed.
2.  Run the [FCOS.ipynb](FCOS.ipynb) notebook to train the model and perform inference.
3.  The trained model weights are saved to `model/FCOS_ish.pt`.

## File Structure

-   `FCOS.ipynb`: Main notebook containing the implementation.
-   `README.md`: This file.
-   `data/`: Contains the dataset.
    -   `faces.csv`: CSV file with face annotations.
    -   `images/`: Directory containing face images.
-   `model/`: Contains the saved model.
    -   `FCOS_ish.pt`: Trained model weights.

## Example Output

The notebook visualizes the predicted bounding boxes on the input images, along with their confidence scores.
