---
layout: page
title: Raytracer
description: C++ project to render scenes from json specifications
img: /assets/img/dnaHD.png
importance: 2
category: University
---

This Raytracer program, written in C++, supports:

*Full Phong Lighting Model
*shadows
*reflections
*textures
*super sampling
*Cel-shader (a.k.a. Toon-shader)
*Gooch shader

The objects supported are:

*sphere
*triangle
*quad
*plane
*cylinder (with caps)
*triangle meshes

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/ss.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/toon.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/texture.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Some examples of rendered scenes. On the left, some sphere rendered with the Phong lighting model. In the middle, the same scene is rendered with the Toon-shader. On the right right, a sphere is rendered with a texture.
</div>

The scenes to be rendered are read from a .json file, which contains the details of each model to be rendered. Using some additional scripts, it's possible to render more complex scenes. For example, below there is a render of a DNA helix, with some H2O molecules floating around in random positions.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dnaHD.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    A scene showing a DNA helix and H2O molecules. 
</div>

The script also supports non-photorealistic shading, which are toon-shading and cell-shading, as shown in some example images below.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dnaToon.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    A scene showing a DNA helix and H2O molecules, rendered with Toon shading. 
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dnaGooch.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    A scene showing a DNA helix and H2O molecules, rendered with the non-photorealistic Gooch shading. 
</div>


