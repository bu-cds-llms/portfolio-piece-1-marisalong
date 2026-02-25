# MNIST Dataset Adaptation: Multi-digit Classifacation Using Simple Neural Networks vs CNN Encoder-Decoder Models

## Overview
This project focuses on classifying multi-digit handwritten images adjusted from the MNIST dataset. Two approaches are examined: Simple Neural Networks vs CNN Encoder-Decoder Models. The goal is to solve a computer's difficulty processing and focusing on the meaningful parts of these images to correctly identify sequences of varying length.

### Motivation
In lab 3, I built a neural network for digit classification using the MNIST dataset. However, the MNIST dataset only contains single-digits. This project idea came to me through a problem we were facing at work. As part of the neuropsychological exam that participants complete, they perform a "math fluency" task, where they are given a page of math problems to solve. To faciliate the scoring process, we wanted to automate the scoring of this task by recognizing each number written by the participant and comparing it to the key of pre-defined answers. The challenge arrises when figuring out if a response is a one-digit response or two-digit response. 

## Relevence to the coursework
For this porfolio piece, I'm going to touch on the class topics:

    - Tokenization
    - Neural Network
    - Attention
    - Transformer Architecture (Encoder-Decoder)

## Methods
For my exploratory model, I chose to use a CNN because they excel working with images and spatical patterns. I combined this with an Encoder-Decoder transformer to see how the concept could be applied to sequences other than natural language, as we discussed in class. Attention allowed the decoder to only focus on the parts of the image (or the sequences) that were most relevant for classification instead of taking in the surrounding blank space. I chose to use greedy decoding for speed and determinability.


## Key Results

Compared to the Simple Normalized Neural Network, the CNN Encoder-Decoder Model performed much better on the multi-digit dataset (baseline ≈ 58% accuracy vs. CNN encoder-decoder ≈ 95-96%). The improvement likely stems from two factors: 
    1)the CNN encoder produces locality-aware features that are more condusive to pattern recognition in visual data, and 
    2) the decoder with attention allows the model to understand parts of an image through sequences rather than attempting to look at and classify the entire image at once. The decoder's attention on allowed for alignment between output digits and image regions, which led it to more accurately predict and classify images with various counts of handwritten digits.

## How to run
Please install the requirement needed for this project by running

```
pip install -r requirements.txt
```

To create the multi-digit MNIST dataset, navigate to [notebooks/preprocessing.ipynb](notebooks/preprocessing.ipynb) for a full walk-through. This will automatically create the multi-digit dataset in your `data/MNIST` folder, so make sure this directory has been created.

To follow along with the training of the two models, please see [notebooks/models.ipynb](notebooks/models.ipynb). 

If possible, I recommend using GPUs for the model notebook. You may do so my uploading this notebook to your Google Colab. If you do so, ensure that you also upload the MNIST multi-digit dataset created in the preprocessing step to your Drive as well. I have indicated in the notebook where you may wish to adjust filepaths, but to follow my example without changes, make a `DS593` folder in the root directory of your Drive. Upload your dataset to this folder.

Please create an issue with any questions or concerns. 

## Requirements
These notebooks were developed using `Python 3.13.5`. Please check your python version with the following command:
```
python --version
```

If using a different Python version, you may need to adjust the version numbers listed in the requirements.txt file.
