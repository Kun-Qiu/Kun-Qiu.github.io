---
layout: page
title: Force Detection for Biological Adhesive
description: Using properties of cantilever beams for small force measurement for biological applications
img: assets/img/canti_beam.png
importance: 4
category: Academic
---

This project aims to develop automatic adhesion and friction measurement system with force sensors and computer vision. In particular,
the project explores to characterize the properties of adhesive on biological systems such as the colons and intestines. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dong_Fixture.png" title="Fixture Iter=1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Dong_Fixture_2.png" title="Fixture Iter=2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the first iteration of the fixture for the cantilever probe and the tissue. Right, the second iteration of the fixture for the cantilever probe and the tissue. In each iteration, the probe fixture is located on the left and the tissue fixture is located on the right.
</div>
The probe fixture is mounted onto the motion stage which have two degrees of translational freedom (x and y translation) and holds the cantilever beam. The tissue fixture is designed such that the height of the tissue can be adjusted according to need during experimentation. For the cantilever beam, the width can be adjusted by tightening the four screws on the side; however, this design could be improved to include mechanism that account for the softness of the beam.

---
The force can be related to the maximum deflection of the cantilever beam using the following equation:

$$
\delta = \frac{FL^3}{3EI}
$$

Here, F represents the force, L represents the length of the beam, E represents the Young's modulus of the beam, and I represents the area moment of inertia of the cross-section. The beam was made of Mold Max 20 with a thickness of 1.235 mm, length of 1.658 cm, width of 0.482 cm. The measured Young's modulus for the matieral is 49 psi and moment of inertia is calculated to be approximately 0.756 $$mm^4$$.

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Experimental_Setup.png" title="Experimental Setup" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Force_v_distance.png" title="Force_v_Displacement" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the experimental setup for the adhesion and frictional force measurement is shown. On the right, a sample run of the the detected force over the movement of the motion stage in the y axis is shown.
</div>

One limitation of the setup was that the beam's length was insufficient to approximate the applied load as a point force. This limitation introduced inaccuracies in the force measurement. Despite this, the automated detection system for deflection was able to correctly observe the overall trend of the force. Specifically, the force exhibited an increase with diminishing returns until the adhesion force was no longer sufficient to hold the probe against the biological tissue. At this point, the system displayed an oscillatory behavior as the probe lost consistent contact with the tissue.

In addition to the challenges posed by the point force assumption, force spikes were observed due to errors in detecting the deflection angle. The primary vision algorithm employed for tracking the probe's movement was based on contour detection. This approach relied on identifying the center of the contour as a reference point for calculating the deflection angle. However, this method proved highly susceptible to noise and interference from other objects, leading to deviations in the estimated center of mass of the probe.

If I were to revisit this project, I would incorporate more robust detection methods, such as line detection, to improve the accuracy and reliability of the system. Additionally, I would optimize the color scheme and refine the camera setup to create an environment more conducive to effective line detection. These adjustments would likely mitigate noise-related issues and enhance the precision of the deflection measurements.
