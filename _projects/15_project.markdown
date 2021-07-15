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

An example of such application is called *neural style transfer*,  an optimization technique used to take two images—a content image and a style reference image (such as an artwork by a famous painter)—and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image, as shown in the examples below. 



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style2d.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example of style transfer, taken from the  <a href="https://arxiv.org/pdf/1508.06576.pdf" target="blank">original paper</a>. In the top left image, there is the *content*. In the three other images, the output for three different *styles* is shown. 
</div>

Changing the parametrization of the optimization problem can change drastically the results of the neural network, despite the other components (i.e. loss function) remains the same. 

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
