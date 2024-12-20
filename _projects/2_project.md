---
layout: page
title: 2D Molecular Tagging Velocimetry
description: Two frame velocity approximation using Hough line transform and template matching algorithms
img: assets/img/MTV_2D_Grid.png
importance: 2
category: Academic
giscus_comments: false
---

### Problem Statement:
Given a 2D image of a laser sheet captured, accurately capture the coordinate of the intersections. From a pair of
2D images, resolve the correspondence problem between the intersections from each image and produce a 2D velocity
field.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/frame_0.png" title="Frame t=0" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/frame_1_2us.png" title="Frame t=dt" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the laser sheet before being displaced by the flow. Right, the laser sheet after being displaced by the flow.
</div>

Current method utilized the template matching algorithm to detect the intersection. Although the method provides an accurate method
of detecting the intersection, it lacks versatility in that if the image is rotated or scaled, the algorithm will fail to detect
the intersections. Therefore, a roboust method is being investigated to improve detection task for varying magnification images
resulting from stereoscopic imaging setups.

### Experiment

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/SNR_1.png" title="Hough Transform" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Hough line transformation is utlized for for detection task image at t=0.
</div>

Hough line transformation is preferred over template matching because of the robustness to noise of the algorithm with respect to
the template matching. Even in signal to noise ratio (SNR) of 1, the Hough line is able to detect all of the lines; however, the
limitation of the method is equally prevalent in that the algorithm in not well suited if there exist curvatures in the lines within
the image. Since the magnification factor will vary across the spatial domain of the image, template will be created for each intersection and the templates will be sequentially mapped to the displaced image to find region of interest. The assumptions made for this combination of Hough line transform and template matching will only work if the displacement in 2D and 3D is much smaller than the distance between any two adjacent intersetion points. 

### Work in Progress

This project is still work in progress. Will be updated as more progress is made.
