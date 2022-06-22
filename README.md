July 2020
# Modified Efficientnet for Age and Gender Prediction

Profiling people from images will enable places like malls, shops, and any physical locations to generate better insight from their video stream data. This project modifies the EfficientNet B4 to create a multi-headed model that can predict the age and gender of a person from their face. Refer to this README for a quick summary of the implementation, or view the notebooks for an in-depth description.

Below are results from an unseen test set
```
Test Sample Count: 1041
Age Mean Average Error (Standard Deviation): 4.8 (4.3)
Gender Accuracy: 96.8%
```
## EfficientNet Background

As of 2020, the EfficientNet was the state-of-the-art CNN architecture for image classification. Its 8 versions, each of different size, boasts significant accuracy advantages over similarly sized models.

![EfficientNet-Performance](efficientnet_performance.png)

## Model Overview

This project is an implementation of Efficientnet to build a multi-ouput model that can predict the age and gender of the person. It is trained on the IMDB-Wiki dataset (https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/) and the AFAD face dataset (https://afad-dataset.github.io/).

The model managed a test gender accuracy of above 95% and a test age MAE of around 5.

In depth project descriptions are in the notebooks
