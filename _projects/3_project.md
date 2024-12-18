---
layout: page
title: Adhesion and Frictional Force Detection for Adhesive
description: Using properties of cantilever beams for small force measurement for biological applications
img: assets/img/canti_beam.png
importance: 3
category: Academic
---

This project aims to develop automatic adhesion and friction measurement system with force sensors and computer vision. In particular,
the project explores to characterize the properties of adhesive on biological systems such as the colons and intestines. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dong_Fixture.png" title="Fixture Iter=1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dong_Fixture.png" title="Fixture Iter=2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the first iteration of the fixture for the cantilever probe and the tissue. Right, the second iteration of the fixture for the cantilever probe and the tissue. In each iteration, the probe fixture is located on the left and the tissue fixture is located on the right.
</div>
The probe fixture is mounted onto the motion stage which have two degrees of translational freedom (x and y translation) and holds the cantilever beam. The tissue fixture is designed such that the height of the tissue can be adjusted according to need during experimentation. For the cantilever beam, the width can be adjusted by tightening the four screws on the side; however, this design could be improved to include mechanism that account for the softness of the beam.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
