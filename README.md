# Twitter-Based Gender Recognition Using Transformers

### Zahra Movahedi Nia Ali Ahmadi, Bruce Mellado, Jianhong Wu, James Orbinski, Ali Asgary Jude Kong

To reference the data or methods here, please cite the manuscript. Contact Jude Kong with questions at jdkong@yorku.ca.

## Overview

This project is a multimodal approach that uses transformers for gender identification by image and text.
These libraries need to be installed:
- pip install -q transformers
- pip install transformers pytorch-lightning --quiet
- sudo apt -qq install git-lfs

The image and text classification models are fine-tuned on Vision Transformers (ViT) and Bidirectional Encoder Representations from Transformers (BERT), respectively. 

The image classification model which is available in 1Image.py, is trained using an image dataset of Twitter users that we are not able to share due to privacy policies. However, ViTModel classifies an image into three classes: Female, Male, and Unknown with 88.65% accuracy. Our model is then applied on the [PAN-18 dataset](https://pan.webis.de/clef18/pan18-web/author-profiling.html). Our Model was able to classify PAN-18 users by only image with 79.94% accuracy. 

The text classification model (BERTModel) which is available in 2Text.py, is trained on [PAN-18 dataset](https://pan.webis.de/clef18/pan18-web/author-profiling.html) and classifies the users with 81.89% accuracy.

The 1Image.py and 2Text.py produce .csv files that are fed into the 3Image+Text.py. The 3Image+Text.py files combines the Image and Text models using a Feedforward Neural Network (FNN). the FNN consists of one hidden layer of 10 neurons and an output layer of two neurons. The final model (FinalCombinedModel) classifies PAN-18 users based on gender with 85.52% Accuracy.

Our models were originally written on [Google  colaboratory](https://colab.research.google.com/drive/1q7waIubin3G_8S0O9hEfVRs4qL3NqCPd?usp=sharing) and use GPU to execute.
