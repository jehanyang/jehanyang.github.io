---
layout: default
title: Prosthetic Leg Pressure Sensing
---

# {{ page.title }}

<div class="message">
The <a href="http://www.bipedalrobotics.com/">AMBER Lab</a> at Caltech specializes in legged walking. Here, I worked with Rachel Gehlhar on
improving the robustness of a custom prosthetic robot leg by adding a pressure sensor in order for
walking on various terrain and with various users without a need for adjusting the controller used.  
</div>


<img src="/images/pressure.png" style="width:50%; float:right; margin-right:0.3rem; padding-left:0.8rem; border-radius:0">

Here I worked on real-time pressure sensing in order to control a prosthetic robot leg. Challenges of
real-time pressure sensing include reading from all the sensors at a high frequency in order to feed
into the system. This time constraint caused me to look into real-time OS guarantees,
multithreading, and various adjustments in order to not slow down the control loop. The results from
[this
paper](https://authors.library.caltech.edu/113763/1/Powered_Prosthesis_Locomotion_on_Varying_Terrains_Model-Dependent_Control_with_Real-Time_Force_Sensing.pdf)
ended up being published in the *Robotics and Automation Letters* along with *IEEE ICRA
2022*. 

Working with a prosthetic robot leg is challenging in that experiments require a certain amount of
risk for the user. By using theoretical guarantees of nonlinear control convergence at a exponential
rate using ID-CLF-QP, we were able to ensure the robot moved efficiently and follow the desired trajectory.
