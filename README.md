## AI-of-the-needle

Author: Scott Butters
Description: This a machine vision project using deep neural networks to learn to classify images. In this particular example, the network is trained on panorama images captures from the top of the Space Needle in Seattle, and has learned to filter our bad images (too cloudy, dark, blurry, etc.), as well as highlight images that are likely to be perceived as the "best" images by a human's aesthetic judgment. The model is a depthwise separable convolutional neural net using [Xception architecture](https://arxiv.org/abs/1610.02357) using transfer learning to instantiate the model with weights pre-trained on the ImageNet dataset, and is implemented using Keras and Tensorflow. Read more about the implementation of this project on my [blog](http://scottbutters.com/articles/2019/06/07/AI-of-the-Beholder/).

