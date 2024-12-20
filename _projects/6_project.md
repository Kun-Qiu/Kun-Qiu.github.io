---
layout: page
title: Two-Dimensional Tracking System for Solar Panel
description: Maximizing solar panel efficiency by implementing a two degrees of freedom rotational tracking system
img: assets/img/solar_panel.jpg
importance: 5
category: Academic
---

Solar energy is a pivotal resource in our transition to sustainable energy solutions. However, a common challenge lies in maximizing energy output by ensuring solar panels maintain optimal exposure to sunlight throughout the day. This blog introduces a solar panel tracking system designed to address this issue through a two-dimensional rotational mechanism that adjusts dynamically to changes in light intensity.

### Problem Statement

Traditional static solar panels cannot adapt to the sun's movement across the sky, leading to suboptimal energy production. For optimal efficiency, solar panels need to adjust their orientation to align with the sun's position, ensuring maximum light capture. The challenge lies in designing a responsive, efficient, and cost-effective mechanism to achieve this.

### Design

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/solar_panel_design.png" title="CAD Design" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/solar_panel_prototype.png" title="Prototype" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: The CAD design of the solar panel platform. Right: The prototype for the solar panel platform.
</div>

Our solution uses photo-resistors as light intensity sensors, paired with two servo motors for two-dimensional rotation. The system components include:

<ul>
    <li><strong>Photo-Resistors:</strong> Arranged in a cross-shaped configuration to detect light intensity gradients in four regions (upper, lower, left, right).</li>
    <li><strong>Voltage Divider and Low-Pass Filter:</strong> Convert light intensity readings into stable voltage signals.</li>
    <li><strong>Servo Motors:</strong> A continuous servo for 360° x-axis rotation and a positional servo for 0-90° y-axis adjustments.</li>
    <li><strong>Rotational Platform:</strong> Designed with grooves and steel ball bearings to minimize friction during movement.</li>
</ul>

### Results

<div class="table-responsive mt-4">
    <table class="table table-bordered">
        <thead class="thead-light">
            <tr>
                <th>Angle [degrees]</th>
                <th>X Rotation Response Time [s]</th>
                <th>Y Rotation Response Time [s]</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>15</td>
                <td>2.89</td>
                <td>2.58</td>
            </tr>
            <tr>
                <td>30</td>
                <td>2.77</td>
                <td>2.78</td>
            </tr>
            <tr>
                <td>45</td>
                <td>2.62</td>
                <td>3.18</td>
            </tr>
            <tr>
                <td>60</td>
                <td>1.63</td>
                <td>2.48</td>
            </tr>
            <tr>
                <td>75</td>
                <td>2.21</td>
                <td>2.10</td>
            </tr>
            <tr>
                <td>90</td>
                <td>2.32</td>
                <td>2.02</td>
            </tr>
        </tbody>
    </table>
</div>

<div class="table-responsive mt-4">
    <table class="table table-bordered">
        <thead class="thead-light">
            <tr>
                <th>Distance [cm]</th>
                <th>X Rotation Response Time [s]</th>
                <th>Y Rotation Response Time [s]</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>5</td>
                <td>2.52</td>
                <td>2.97</td>
            </tr>
            <tr>
                <td>10</td>
                <td>5.57</td>
                <td>4.56</td>
            </tr>
            <tr>
                <td>15</td>
                <td>17.25</td>
                <td>12.24</td>
            </tr>
            <tr>
                <td>20</td>
                <td>Infinite</td>
                <td>Infinite</td>
            </tr>
            <tr>
                <td>25</td>
                <td>Infinite</td>
                <td>Infinite</td>
            </tr>
            <tr>
                <td>30</td>
                <td>Infinite</td>
                <td>Infinite</td>
            </tr>
        </tbody>
    </table>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/solar_panel_rotate.png" title="Rotate Response Time" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/solar_panel_distance.png" title="Distance Response Time" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: The response time of platform as a function of rotational angle. Right: The response time of platform as a function of light source from platform.
</div>

### Insights from Experiment

Our experiments provided valuable insights into the solar panel tracking system’s performance. For different angles, we expected the response time to remain constant, but instead, it decreased as the angle increased. At 15°, the response times were 2.89 seconds (X rotation) and 2.58 seconds (Y rotation), while at 60°, they dropped to 1.63 seconds and 2.48 seconds. This unexpected trend suggests the system adjusts more efficiently for larger changes in light intensity.

When testing the response time at different distances, we found that it increased exponentially as the light source moved further away. At 5 cm, the system responded quickly, but by 15 cm, response times soared, and beyond this distance, the sensors failed to detect the light due to its divergence. This highlights a key limitation in the sensitivity of photo-resistors.

The system also struggled with tracking fast-moving light, limited by the speed of the sensors and software. To improve, we could expand the sensor area, increase sampling rates, and add predictive algorithms for dynamic tracking.

### Conclusion

In summary, while the system showed promise in tracking light at close distances and angles, there’s room for improvement to enhance its range and adaptability. For light source such as the Sun, the distances between the photoresistor should be enlarge to ensure that the intensity gradient is detected accurately and that the rotate of the platform is adequate. These lessons are crucial for creating more effective solar tracking solutions in the future.
