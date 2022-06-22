July 2020
# Modified Efficientnet for Age and Gender Prediction

Profiling people from images will enable malls, shops, etc. to generate better insight from video data. This project modifies an EfficientNet B4 to create a CNN model that can predict the age and gender from a person's face.

Refer to this README for a quick summary of the implementation, or view the notebooks for an in-depth description. The data and some data-cleaning steps are not included in this repo, as the data is open-source and the steps are straightforward. This repo focuses on the techniques used in developing this model.

Below are the out-of-sample test results:
```
Test Sample Count: 1041
Age Mean Average Error (Standard Deviation): 4.8 (4.3)
Gender Accuracy: 96.8%
```
## EfficientNet Background

In 2020, the EfficientNet was the state-of-the-art CNN architecture for image classification. Its 8 versions, each of different size, boasts significantly higher accuracies over similarly sized models.

![EfficientNet-Performance](images/efficientnet_performance.png)

## Model Overview

An EfficientNet B4 is modified to produce a double-headed model, with one a regressor (age) and the other a classifier (gender). It is pre-loaded with ImageNet weights and fine tuned with the 100,000+ face samples.

## Data & Preprocessing

Data was taken from the Wikipedia (https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/, >50,000), AFAD Face (https://afad-dataset.github.io/, >50,000), and UTKFace (https://susanqq.github.io/UTKFace/, >20,000) Datasets. They generally consist of faces of people ages 0 to 80 with age and gender labels. 

After filtering out extreme ages (>80+) and downsampling some ages from the 3 datasets, a DataFrame "age_gender_data.csv" was created to store the image paths and labels.

The main pre-processing step was to standardize the input images. As shown below, the images had different zoom levels, as some captured the face only, while others captured the shoulders or more.

![alt-text-1](images/face_only.png "title-1") ![alt-text-2](images/face_and_shoulders.png "title-2")