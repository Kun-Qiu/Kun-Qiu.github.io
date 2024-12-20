---
layout: page
title: Wheel Chair Lift Design
description: Using linkages, design a wheel chair lift under a set of physical constraints  
img: assets/img/WheelChair_Lift.jpg
importance: 4
category: Academic
---

The "Chairway to Heaven" project aims to solve a significant accessibility challenge: designing a wheelchair lift that allows seamless vertical movement in residential garages with a height difference of one meter. This project explores the innovative approach used to create a compact, efficient, and user-friendly lift solution.

### The Design Vision

The project team sought to create a lift mechanism that is both space-efficient and compliant with Federal ADA regulations. By focusing on simplicity and functionality, we developed a multi-scissor linkage lift that optimizes vertical displacement while maintaining a minimal footprint. Key specifications include supporting a 300-pound load and ensuring smooth operation within 10 seconds for a one-meter elevation.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lift_design.png" title="Lift Design" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The conceptual design of the lift.
</div>

### Why a Multi-Scissor Linkage?
The multi-scissor linkage design was chosen for its compactness and scalability. By stacking scissor mechanisms, the design doubles vertical displacement without increasing the overall size. This innovative setup ensures:

<ul>
    <li><strong>Smooth Translation:</strong> The design ensures a horizontal platform throughout its motion.</li>
    <li><strong>Compact Footprint:</strong> Ideal for tight residential spaces.</li>
    <li><strong>Efficiency:</strong> Less force is required for equivalent elevation compared to traditional designs.</li>
</ul>

### Prototyping 

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/chair_side.png" title="Side View" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/chair_front.png" title="Front View" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/chair_iso.png" title="Isometric View" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: The side view of the final rendered design. Middle: The front view of the final rendered design. Right: The isometric view of the final rendered design.
</div>


### Kinematic Analysis

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/platform_kin.png" title="Platform Kinematics" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The kinematic analysis of the top platform for the scissor lift design.
</div>

The kinematic analysis focused on ensuring smooth and controlled motion for the lift platform. By using vector equations, the position, velocity, and acceleration of the platform’s center of mass were derived as functions of time. This approach confirmed that the lift meets velocity and acceleration limits of 0.158 m/s and 0.159 m/s², respectively, ensuring user safety and comfort. A MATLAB simulation demonstrated the platform’s predictable movement trajectory, which minimizes any abrupt changes during operation.

Key insights include:
<ul>
    <li>The lift’s movement follows a stable vertical trajectory, with minimal horizontal deviation.</li>
    <li>The mechanism maintains a horizontal platform orientation throughout the motion cycle, complying with ADA requirements.</li>
</ul>

### Kinetics and Failure Analysis

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/chair_fail.png" title="Platform Failure" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The kinetic and failure analysis of the scissor lift design.
</div>

The kinetics analysis evaluated the forces, moments, and stresses acting on the lift components to ensure structural integrity. Using free-body diagrams and equilibrium equations, the team identified high-stress areas, particularly at the central pin and bearing locations. The analysis revealed the following:

<ul>
    <li>
        <strong>Stress Distribution:</strong> The maximum stresses occur at the center of the linkage due to bending moments. This necessitated using 202 annealed stainless steel for its high yield strength (260 MPa).
    </li>
    <li>
        <strong>Load Capacity:</strong> Bearings and shafts were selected to exceed the maximum static and dynamic loads, ensuring durability.
    </li>
    <li>
        <strong>Safety Factor:</strong> A safety factor of 2 was applied to all critical components to accommodate unexpected loads and material inconsistencies.
    </li>
</ul>

### Conclusion

The "Chairway to Heaven" lift is a testament to engineering innovation and user-centric design. By leveraging advanced analysis tools and iterative refinement, the project delivers a solution that enhances accessibility and independence for individuals with mobility challenges. This lift not only bridges physical gaps but also paves the way for more inclusive residential spaces.