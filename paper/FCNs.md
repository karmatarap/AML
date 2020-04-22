FCNs for Semantic Segmentation
========================================================
author: Karma Tarap & Alexander Noll
date: 26-10-2017
autosize: true

Image Classification
========================================================

Standard convolutional neural networks (CNNs) are good at **global classification**:

![](FCNs-figure/CNN.png)


Image Segmentation
========================================================

What if we are interested in asking the question: where is the hotdog?

![](FCNs-figure/FCN-Motivation.png)


Image Segmentation Examples
========================================================

![](FCNs-figure/image_seg.png)

Problem
========================================================

So we have a *local* classification problem:

+ For each point of an image a class is supposed to be predicted
+ Numerous applications: e.g
  - Machine vision
  - Medical imaging
  - Object detection
  - Self-driving-cars (**Code Demo**) 

Convolutional layer
========================================================
<div align="center">
<img src="FCNs-figure/filter.png" width=300 height=300>
</div>
**Filter**
***

<div align="center">
<img src="FCNs-figure/conv_layer_2.gif" width=800 height=600>
</div>
Convolutional layers
========================================================

Convolutional layers use the **spatial symmetry** of the problem to reduce the number of weights. They do this using the concept of **weight sharing**: a hot-dog in the upper right is the same as a hot-dog in the lower left corner.

Important parameters:

+ Kernel size: how big of a region should share the same weights
+ Stride: how many steps at a time should the filter take

Pooling layers
========================================================

Summarize patch of an image by taking the maximum or mean (or whatever)

Important parameters:

+ Kernel size: how big of a region should the summary function be applied to
+ Stride: how many steps at a time should the filter take

Pooling layers
========================================================

![](FCNs-figure/pooling_layer.png)


Key Points
========================================================
+ **End to end** convolutional networks for semantic segmentation
+ Upsample using deconvolutional layers
+ Transfer learning for pretrained networks
+ Skip layers to improve upsampling prediction

End to end convolutional networks
========================================================
+ Series of convolutional layers and pooling-layers decreasing the size of the output
+ Followed by a series of **deconvolutional layers** or **transposed convolutional layers** or **upsampling layers** that increase the output size

![](FCNs-figure/tabby_heatmap.png)


Convolutional (CNN) Vs Fully Convolutional NN (FCN)
========================================================
Architecture of VGG16
<div align="center">
<img src="FCNs-figure/vgg16.png" width=800 height=800>
</div>


***
Architecture of FCN32

<div align="center">
<img src="FCNs-figure/fcn_architecture.gif" width=800 height=800>
</div>

Upsampling
========================================================

How do we retrieve the size of the original image?

Use **upsamling** or **transposed convolutional** or **deconvolutional** layers to upscale image


Upsampling -  No pad, no strides
========================================================

<div align="center">
<img src="FCNs-figure/no_padding_no_strides.gif" width=800 height=800>
</div>


***

<div align="center">
<img src="FCNs-figure/no_padding_no_strides_transposed.gif" width=800 height=600>
</div>


Upsampling -  No pad, 2 strides
========================================================


<div align="center">
<img src="FCNs-figure/no_padding_strides.gif" width=800 height=800>
</div>


***

<div align="center">
<img src="FCNs-figure/no_padding_strides_transposed.gif" width=800 height=800>
</div>



Transfer Learning
========================================================

+ Use architecture from pre-trained CNNs
+ Use weights from networks trainined on imagenet
+ Replace connected layers with upsampling

*Transfer learning with direct up-sampling produced state of the art performance*
Skip layer
========================================================

Used to transfer information (spatial) from **early layers** directely into layers close to the output layer via elementwise addition.

![](FCNs-figure/skip_layer.png)
Skip connections - Results
========================================================

![](FCNs-figure/skip_result.png)



Recap:
========================================================

![](FCNs-figure/recap.png)
***
+ End-to-end convolutional network
+ Transfer Learning
+ Upscaling
+ Skip layers

FCN-8 Results: PASCAL VOC
========================================================

+ 1112 images (see below)
+ 20% improvement: 

![](FCNs-figure/pascal.png)
![](FCNs-figure/pascal-res.png)

Reference:
========================================================
Fully Convolutional Networks for Semantic Segmentation

Jonathan Long, Evan Shelhamer, Trevor Darrell
https://arxiv.org/abs/1411.4038


========================================================

Demo


