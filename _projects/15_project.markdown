---
layout: page
title: 3D Style transfer
description: Creating marvelous textures with neural networks 
img: /assets/img/style2.jpeg
importance: 1
category: computer graphics
---

Neural networks have been very popular in the last years for computer vision task, like images classification. In the last years, a new wave of artist is pushing their bundaries further, using techniques like <a href="https://ai.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html" target="blank">DeepDream</a>, <a href="https://arxiv.org/pdf/1508.06576.pdf" target="blank">style transfer</a> and <a href="https://distill.pub/2017/feature-visualization/" target="blank">feature visualization</a>.

All these technologies are based on the same intuition. Neural networks can interpret images as they store some abstract representation in their internal layers, called features or filters. Once we feed an image to a network, each pixel will contribute to the activation of certain filters, leading to a certain prediction. We can also use these representation to describe some properties (a.k.a. style) that we want to optimize in a picture. This optimization is possible as the activations each filter are differentiable with respect to each input: this means that we can tweak the input using the gradient descent algorithm in an iterative way.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/style.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example 1
</div>


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
