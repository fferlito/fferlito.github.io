---
layout: page
title: Generating cat faces with GANs
description: Generative Adversarial Network (GAN) for generation of cat images
img: /assets/img/cats.png
importance: 4
category: deep learning
---

Generative Adversarial Network (GAN) is a class of unsupervised machine learning systems in which two different neural networks compete in a game (such as a zero-sum game) in order to train each other. These two are called generator and discriminator. The former one has the goal to create as output samples with the same distribution of the training data, taking as input a vector from a random distribution. The latter one has to judge whether its input is a real image or a generated one, thus it will have two classes as output (real or fake).

In the context of Deep learning, many variants of GAN include convolutional layers to increase the capacity of these models for unsupervised tasks. This project contains some of these implementations. These include DCGAN, WGAN and ProGAN.The task for these networks is to learn to generate cats’ faces, using a collection of open source data-sets. The final dataset can be found at this link: https://github.com/Ferlix/Cat-faces-dataset . To get more insights on the quality and diversity of the generated images, two different metrics are used, namely Inception Score (IS) and Frechet Inception Distance (FID).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/cats.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/wcats.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dccats.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Examples of generated cats using different GAN models. On the left, there's some images made with proGAN. In the middle, images are made with W-GAN. On the right, the cats are made with DC-GAN.
</div>


