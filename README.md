# Network Intrusion Detection with Machine Learning

**Author:** Mohammad Javad Akbari 

## 1. Project Overview

This repository contains a comprehensive machine learning project for **Network Intrusion Detection (NID)** on the NSL-KDD dataset. The primary goal is to develop and evaluate robust models capable of accurately classifying network traffic into 'normal' or one of four major attack categories (DoS, Probe, R2L, U2R).

A key challenge in this dataset is the severe **class imbalance**, where attack types like R2L and U2R are extremely rare. This project places a strong emphasis on techniques to mitigate this imbalance and build models that perform well not just on common traffic but also on detecting these infrequent, critical threats.

The entire workflow, from data analysis to model evaluation, is detailed in the `NIDS.ipynb` notebook.

## 2. Methodology

The project follows a structured machine learning pipeline to ensure reproducibility and rigor:

1.  **Data Preprocessing and Cleaning:** The NSL-KDD training and test sets are loaded, cleaned, and specific attack labels are mapped into five general categories (`normal`, `dos`, `probe`, `r2l`, `u2r`).

2.  **Feature Engineering:** New, informative features were created from the existing data to enhance model performance.

3.  **Handling Class Imbalance:** The **SMOTETomek** technique was applied to the training data. This oversamples minority classes and cleans class boundaries, creating a more balanced dataset for training and preventing model bias.

4.  **Model Training:** Four powerful models were selected for the task:
    * Random Forest
    * XGBoost
    * Deep Neural Network (DNN)
    * Gated Recurrent Unit (GRU) Network

<br>Each model was trained directly using a set of pre-selected, optimal hyperparameters to ensure an efficient and direct comparison of their core performance.

## 3. Results and Model Comparison

The models were evaluated on the untouched test set. The **XGBoost model** emerged as the top performer, achieving the highest F1 score, which indicates the best balance in detecting attack categories.

### Final Performance Metrics

![Model Performance Comparison](https://github.com/Javad-Ak/network-intrusion-detection/blob/main/results/figures/model_comparison.png)

The F1 Macro score is the most critical metric here, as it provides a better measure of success on an imbalanced dataset than accuracy alone.

### Confusion Matrices

The confusion matrices below provide a detailed view of each model's classification performance across all five categories.

| Random Forest                                                                                                                  | XGBoost                                                                                                                    | Neural Network                                                                                                                  | GRU Neural Network                                                                                                                          |
|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| ![RF CM](https://github.com/Javad-Ak/network-intrusion-detection/blob/main/results/figures/Random_Forest_confusion_matrix.png) | ![XGB CM](https://github.com/Javad-Ak/network-intrusion-detection/blob/main/results/figures/XGBoost_confusion_matrix.png) | ![NN CM](https://github.com/Javad-Ak/network-intrusion-detection/blob/main/results/figures/Neural_Network_confusion_matrix.png) | ![GRU CM](https://github.com/Javad-Ak/network-intrusion-detection/blob/main/results/figures/GRU_Neural_Network_confusion_matrix.png) |

## 4. How to Reproduce the Results

To replicate this analysis:

1.  **Clone the repository** and navigate into the directory.
2.  **Set up a virtual environment** and install the dependencies from `requirements.txt`.
3.  **Place the dataset files** (`KDDTrain+.txt`, `KDDTest+.txt`) into the `NSL_KDD/` directory.
4.  **Run the `NIDS.ipynb` Jupyter Notebook** from start to finish.

## 5. License
This project is licensed under the MIT License.
