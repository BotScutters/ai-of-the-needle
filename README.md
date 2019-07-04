## AI-of-the-needle

We hear a lot nowadays about the many superpowers of AI, but we don't hear much about its highly refined aesthetic sensibilities. Well, that's what I'm here to change! I trained a convolutional neural net to look through thousands of photos taken from on top of the space needle and learn which ones are junk (as a baseline), and even to highlight the most beautiful of the bunch! But while this application may be a bit of pet-project-floof, it's not without a use case: think first-pass filter on a photographer's raw photos; think auto-curated album from your snap-happy vacation. 

<figure>
  <img src="/reports/beholder5.jpg" alt="ai-of-the-beholder" style="width:100%">
  <figcaption>You're so pretty, Seattle.</figcaption>
</figure>

# Abstract

For this project, I've trained a convolutional neural net to look through a gallery of images and then assign scores to each image according to it's quality, allowing a user to apply the algorithm as a first-pass filter to reduce the size of a gallery to review. As an added benefit, the scores can also be used to highlight the best amongst the images. The dataset used for this project is a collection of panoramic images taken of the Seattle skyline by a camera on top the Space Needle. The model is a depthwise separable convolutional neural net using [Xception architecture](https://arxiv.org/abs/1610.02357) using transfer learning to instantiate the model with weights pre-trained on the ImageNet dataset, and is implemented using Keras and Tensorflow. The convolutional base is reduced by a 2D global average pooling layer followed by a dropout layer and a fully connected layer reducing down to a single neuron with linear activation for the final prediction of an image's score. All but the top 4 blocks of the convolutional base were frozen during training. The top performing model used the following parameters:

- Dropout rate: 0.6
- Optimizer: stochastic gradient descent, learning rate = 0.0001, momentum = 0.9, clip value = 0.5
- Loss function: mean squared error

Read more about the implementation of this project on my [blog](http://scottbutters.com/articles/2019/06/07/AI-of-the-Beholder/).