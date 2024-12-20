---
layout: page
title: Fluids Simulation
description: COMSOL based fluid simulation of interactions between thermoelectric and soda can
img: assets/img/heat_transfer.png
importance: 3
category: Academic
---

Have you wonder how effective is thermoelectric in rejecting heat from an enclosed space? Currently, commericially available thermoelectric have an efficiency of approximately 5 to 6 percent. One of my favorite drink is Coca-Cola, and I occasionally wonders if there exists portable cooler where you could cool the soft drinks. In this project, I will provide a simulation of the cooling effect of thermoelectric device with COMSOL, numerical simulation with MATLab, and experimental data. For the COMSOL specifically, two configurations of cooling (vertical and horizontal can) are simulated to determine which method is better for cooling. 

### Computational Setup

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Vert_Can.png" title="Vertical Can" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Hor_Can.png" title="Horizontal Can" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, schematic of the verticle can. Right, schematic of the horizontal can.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Vert_Can_mesh.png" title="Mesh of Vertical Can" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Hor_Can_mesh.png" title="Mesh of Horizontal Can" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the discretization of the verticle can's computational domain using tetrahedrals. Right, the discretization of the verticle can's computational domain using tetrahedrals.
</div>

The material properties of all the material included in the simulation is shown in the table below. Note that the air flow speed is assumed to be small which means that the flow condition will be laminar and not turbulent. 
<!-- Material Properties Table -->
<div class="table-responsive mt-4">
    <table class="table table-bordered">
        <thead class="thead-light">
            <tr>
                <th>Material</th>
                <th>Material Density [kg/m<sup>3</sup>]</th>
                <th>Thermal Conductivity [W/m·K]</th>
                <th>Thermal Capacity [J/kg·K]</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Air</td>
                <td>1.208</td>
                <td>0.02623</td>
                <td>1006</td>
            </tr>
            <tr>
                <td>Aluminum</td>
                <td>2730</td>
                <td>155</td>
                <td>893</td>
            </tr>
            <tr>
                <td>Water</td>
                <td>997</td>
                <td>0.598</td>
                <td>4184</td>
            </tr>
            <tr>
                <td>Silica Glass</td>
                <td>2203</td>
                <td>1.38</td>
                <td>703</td>
            </tr>
        </tbody>
    </table>
</div>

---
### Theoretical Foundation

Before devling into the results of the simulation, let us discuss the governing equation of the interactions between the Coca-Cola can and the thermoelectric device. In addition, the Coca-Cola is assumed to be a solid with a material properties similar to that of water. Within the Coca-Cola can, the heat transfer is governed by the 3D heat equation:

$$
    C_p k \frac{\partial T}{\partial t} = \nabla^2\cdot T + q_k
$$

Here, $$C_p$$ represents heat capacity, k represents the thermal conductivity, T represents the temperature, (x, y, z) represents the spatial variable, and t represents the time variable. The behavior of the fluid within the closed system is governed by the Navier-Stokes equations ass shown in the equation below. The natural convection only occurs in the z-axis; therefore, the gravity term in the x-direction and y-direction of the Navier-Stokes equations are zeros.

$$

    \frac{\partial \vec{u}}{\partial t} + \vec{u} \left(\vec{u} \cdot \nabla \right)= -\nabla\vec{p} + \frac{\mu}{\rho}\nabla^2\vec{u} + \vec{g}
    
$$

Here $$\mu$$ represents the viscocity of fluid, p represents the pressure, u represents the velocity vector, and $$\rho$$ represent the density of fluid. Since the fluid will carry the temperature as it flows from one location to another, the fluid motion and the corresponding temperature can be described with the temperature convection-diffusion equation.

$$
    \frac{\partial T}{\partial t} + \vec{u} \cdot \nabla T = \alpha (\nabla^2 T)
$$

---

### COMSOL Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Vert_Can_Temp.png" title="Vertical Can Temperature Profile" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Hor_Can_Temp.png" title="Horizontal Can Temperature Profile" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The surface temperature profile of the vertical and horizontal configuration of Coca-Cola Can. 
</div>

From the surface temperature graphs, the cooling effect of the horizontal configuration is 12.5% more effective than the standing configuration. For a much more symmetric cooling, the horizontal configuration should be utilized over the vertical configuration if using thermoelectric device as the main source of cooling. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Vert_Can_Vel.png" title="Vertical Can Velocity" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Hor_Can_Vel.png" title="Horizontal Can Velocity" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, slices of the velocity field around the Coca-Cola can in the vertical configuration. Right, slices of the velocity field around the Coca-Cola can in the configuration configuration.
</div>

The maximum velocity for the standing and horizontal configurations are 0.141 m/s and 0.188 m/s, respectively. Notably, the maximum velocity in the horizontal setup exceeds that of the standing configuration by 33%. The greater maximum velocity in horizontal configuration likely contributes to the significantly enhanced heat transfer observed in the horizontal setup. However, it is evident that the velocity profile exhibits greater symmetry in the standing configuration without any significant effect on the heat transfer. 

---

### MATLab Numerical Studies

For the numerical study, the surface temperature on the Coca-Cola is obtained using the lumped capacitane model. It is assumed that the heat transfer coefficient, denoted by h, remains constant throughout the operation of the device.

$$
    T_s(t) = (T_i - T_{\inf})e^{\frac{hA_s}{\rho C_pV}t} + T_{\inf}
$$

$$
    q^{"}(t) = h(T_s(t) - T_{\inf}) 
$$

Here $$T_s(t)$$ represents the surface temperature, $$T_{\inf}$$ represents the ambient temperature, h represent the heat transfer coefficient, and $$A_s$$ represents the surface aera.  

---

### Numerical Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Mat_Surface.jpg" title="Surface Temperature" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Mat_Heat.jpg" title="Heat Transfer" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the surface temperature using the lumped capacitance model. Right, the heat transfer across the solid and fluid assuming constant heat source.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Geom.jpg" title="MATLab Geometry" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Geom_mesh.jpg" title="MATLab Geometry Mesh" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the axis-symmetric geometry of the Coca-Cola can. Right, the discretization of the geometry using triangular structures.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Temp_Dist1.jpg" title="Temperature Distribution 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Temp_Dist2.jpg" title="Temperature Distribution 2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Temp_Dist3.jpg" title="Temperature Distribution 3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the temperature distribution at t=3hr. Middle, the temperature distribution at t=5hr. Right, the temperature distribution at t=10hr.
</div>

At the three-hour mark, the internal temperature of the Coca-Cola can remains 15 degrees Celsius. As the cooling time increases to the five-hour mark, majority of the can reachs a 10 degrees Celsius except for the bottom left corner. To fully reach the desired 5 degree Celsius, it will require 10 hours of cooling at a constant heat flux of -5W. For the experimental section of the fluid simulation, the thermoelectric device is enclosed in a "perfectly thermal isolated" environment where the cold side of device is expose to the air inside and the hot side facing the ambient environment.  

### Experimental Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Experiment_Heat.jpg" title="Experimental Setup" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Experiment_Heat2.jpg" title="Experimental Setup 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the exterior of the experimental setup. Right, the internal of the experimental setup with the thermal insulation.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Experiment_Heat_Result.png" title="Experimental Result" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The experimental result over an hour of data recording. 
</div>

### Conclusion

This study investigated the efficiency of a closed-system cooling device utilizing the Seebeck effect of a thermoelectric device (TED) through COMSOL simulation, numerical modeling, and experimental analysis. The results revealed that the horizontal configuration of the cooling system outperforms the standing configuration, achieving a temperature approximately 12.5% lower, highlighting the importance of system orientation in TED-based cooling devices. Despite this, the study also identified the limitations of thermoelectric cooling for beverage applications, with prolonged cooling times and inefficiencies in heat extraction indicating a need for further optimization. While TED-based cooling shows promise, its performance currently lags behind conventional cooling methods, offering opportunities for future improvements and innovations in thermoelectric cooling technology.
