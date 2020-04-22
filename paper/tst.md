Convolutional layer
========================================================

![](FCNs-figure/conv_img.gif)
***
![](FCNs-figure/conv_layer_2.gif)

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
