---
layout: post
published: true
mathjax: true
featured: false
comments: true
title: Convolutional Neural Networks - An Introduction
description: 'Convolution neural networks '
headline: Convolutional Neural Networks - An Introduction
categories:
  - NeuralNetworks
  - MachineLearning
  - ComputerVision
tags: >-
  Coursera MachineLearning NeuralNetworks ConvolutionNeuralNetwork
  ComputerVision Edge Detection
---
>&quot;A person who never made a mistake never tried anything new.&quot;
><small><cite title="Einstein">Einstein</cite></small>

## Convolutional Neural Network
In real word examples computer vision has to work on images with a size of 1000x1000x3 pixels. This becomes a huge matrix, if e.g. the first layer has 1000 knots. This results in a matrix dimension of (1000, 3M). To solve this kind of problems, we introduce **convolutional neural networks**.

Classical problem fields are **computer vision** or **edge detection**.

### Edge Detection
![vertEdgeDetection.png]({{site.baseurl}}/images/posts/ConvolutionalNN/vertEdgeDetection.png)

There are multiple filters developed in the past. But there is also the possibility to use **Backprop** to capture the values of this 3x3 filter matrix.
In this sense neural networks can learn low-level features, such as edge detection.

### Padding
![padding.png]({{site.baseurl}}/images/posts/ConvolutionalNN/padding.png)

If we have a *nxn* image and a *fxf* filter, the result will be a *n-f+1 x n-f+1* matrix.

To solve this **shrinking output** we use padding. Otherwise if every layer would shrink our image, we would loose a lot of information.

By adding an additional pixel layer around the image, we can preserve the image size. In this case the Padding p=1 and their value is *zero*.

#### Valid And Same Convolutions
- Valid: no padding
- Same: Pad so that output size is the same as the input size
><small> To keep the input size while using a 5x5 filter, the padding would have to be p=2, meaning 2 additional surrounding pixels.</small>

### Stride Convolution
![stringing.png]({{site.baseurl}}/images/posts/ConvolutionalNN/stringing.png)

#### Technical Note
The convolution operation is also called **cross-correletion** in signal processing and math books. In this fields it's common to flip the filter in both dimensions.

### Convolutions Over Volumes

#### Convolutions On RGB Images
The filter will be increased in the same dimension as the image data. In this case this is 3 dimensions, for the three color channels.

![convVol.png]({{site.baseurl}}/images/posts/ConvolutionalNN/convVol.png)

It is possible to choose by the 3D filter to switch between edge detection on single channels or multiple.

#### Multiple Filters
If we want to apply multiple filters such as vertical and horizontal edge detection. The results will be stacked into a multidimensional data stack with the corresponding amount of layers.

#### Summary
*n-f+1 x n-f+1 x n_c'*  where *n_c'*  is the amount of filters.