---
layout: page
title: 3D Style transfer
description: Creating marvelous textures with neural networks 
img: /assets/img/style2.jpeg
importance: 1
category: computer graphics
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">

</div>


Neural networks have been very popular in the last years, especially in the field of computer vision (i.e. images classification tasks). In the last years, a new wave of artist is pushing their bundaries further, using techniques like <a href="https://ai.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html" target="blank">DeepDream</a>, <a href="https://arxiv.org/pdf/1508.06576.pdf" target="blank">style transfer</a> and <a href="https://distill.pub/2017/feature-visualization/" target="blank">feature visualization</a> to create artistic images and abstract visualizations.

All these technologies are based on the same intuition. Neural networks are formed stacking layers of artifical neurons. They can interpret the input images as they store some abstract representation in these internal layers, which we call features, filters or kernels. Once we feed an image to a network, each pixel will contribute to the activation of certain filters, leading to a certain prediction. We can use these representation in a different way: to describe some properties (a.k.a. style) that we want to optimize in a picture. This optimization is possible as the activations each filter are *differentiable* with respect to the input: this means that we can tweak the input using the gradient descent (or other algorithms) in an iterative way. 

An example of such application is called *neural style transfer*,  an optimization technique used to achieve image stylization in a non-photorealistic way. In the next sections, the basic concept of style transfer is described. Following, an extension for applying this technique on 3d models is given.


## Neural style transfer

Neural style transfer is used to take two images, a content image and a style reference image (such as an artwork by a famous painter), and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image. Some examples of stylized images are shown below.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style2d.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example of style transfer, taken from the  <a href="https://arxiv.org/pdf/1508.06576.pdf" target="blank">original paper</a>. In the top left image, there is the content. In the three other images, the output for three different styles is shown. 
</div>

The main architecture requried for style transfer is a pretrained convolutional neural network. Then, the optimization procedure is computed using three components: (i) a content image, (ii) a style image, (iii) and the input image, which is the one that is generated as final output. What allows the network to generate these beutiful stylized images is at the core of the optimization process: the loss function. Let's discuss them in detail to understain better what's going on.

### A matter of loss
Neural style transfer is based on two loss functions: the **content loss** and the **style loss**. The first ensures that the activations of the higher layers of the neural network activates in the same way between the content image and the generated image. The other loss allows the correlation of the activation between the layers on the networks are similar between the style image and the generated image. Let's break each of the functions down.

#### Content loss function
The content loss function allows that what it's represented in the content image to be preserved in the generated image. It does so based on the pattern of activations of the last layers of the model. The different layers of CNNS captures patterns with different levels of detail: the first layers focus more on the individual pixels, and they learn small patterns like lines or curves. Deeper layers of the network learns more abstract shapes.  Below, we can see how the different filters activate when the image of a face is fed to a CNN.

<div class="row">
    <div class="col-sm-12 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cnn_layers.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Filters of the CNN at different level of depth learns features with different complexity: first layers learnt basic primitives (edges and colours). Deeper filters learnt textures and patterns. The final layers contains complex features, which can resemble objects from the training data. 
</div>

Therefore we will use the pattern of activation of the last layer of the CNN to define this loss function. Let *A* be the activation of a layer *l*, at the *i*-th feature map and the *j*-th position. Then the content loss function, based on the generated image *g* and the content image *c* is defined as:

<p align="center">
        <img src="https://latex.codecogs.com/png.image?\dpi{150}&space;L_{content}&space;=&space;\frac{1}{2}&space;\sum_{ij}^{}&space;(A^l_{ij}&space;(g)&space;-&space;A^l_{ij}&space;(c))^2&space;&space;&space;" title="L_{content} = \frac{1}{2} \sum_{ij}^{} (A^l_{ij} (g) - A^l_{ij} (c))^2 " />
</p>

In a nutshell, this function takes the *root mean squared error* between the activation produced by the two images. 

#### Style loss function

#### Final loss 
The final loss is defines as a weighted sum of the two losses defined above:


<p align="center">
	<img src="https://latex.codecogs.com/png.image?\dpi{150}&space;L&space;=&space;\alpha&space;L_{content}&space;&plus;&space;\beta&space;L_{style}&space;&space;" title="L = \alpha L_{content} + \beta L_{style} " />
</p>

Where **α** and **β** are two hyper-parameter decided by the user. Controlling these two parameters allow to control the amount of style and content injected in the generated image. In the examples below the effect of these two parameters is shown.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/alpha_beta.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example of style transfer for different values of  α and β, taken from the  <a href="https://arxiv.org/pdf/1508.06576.pdf" target="blank">original paper</a>. In the left, the ratio α/β is the smallest: the generated image contains mostly the pattern of the style. As we go to the right, the ratio become smaller, and the pattern of the content image appears more clear.  
</div>

Changing the parametrization of the optimization problem can change drastically the results of the neural network, despite the other components (i.e. loss function) remains the same. 

## 3D Neural style transfer


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style4.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example 2
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style5.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example 3
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style3.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example 4
</div>
