---
layout: page
title: Projects
description: Projects for me
keywords: projects
comments: true
menu: Projects
permalink: /projects/
---
# Introduction

This page is the collection of my projects, including some demos in my work as well as some research topics in my research field. Some source code of the projects will be open in the future.

My research topics are about robot learning and control for legged robots, including imitation learning, model predictive control, whole body control and reinforcement learning, *etc*.

# 2024

### 1. To be continued …



---

# 2023

### 1. C-SQG: Cosine-Law-Based Spatially Quantized Gait Generation for Knee-Stretched Biped Walking

This is a research topic for the knee-stretched gait patterns generation of the bipedal robots, the paper has been published on the International Journal of Humanoid Robotics (IJHR),  [paper](https://www.worldscientific.com/doi/abs/10.1142/S0219843623500329).  The source code for this project is open now at [github]().

The knee-stretched bipedal walking simulation in 2D on the Matlab is shown as follows: 

<center>
    <img src="/images/projects/CSQG/CSQG_matlab_simulation_kinematics_2D.gif" alt="picture not found" style="zoom:50%;" />
    <img src="/images/projects/CSQG/CSQG_matlab_simulation_dynamics_2D.gif" alt="picture not found" style="zoom:50%;" />
    <br>
</center>

where the left one is with only kinematics calculation, and the right one is with kinematics and dynamics calculation.

The knee-stretched bipedal walking simulation in 3D on the Matlab is shown as follows: 

<center>
    <img src="/images/projects/CSQG/CSQG_matlab_simulation_kinematics_3D.gif" alt="picture not found" style="zoom:50%;" />
    <img src="/images/projects/CSQG/CSQG_matlab_simulation_dynamics_3D.gif" alt="picture not found" style="zoom:50%;" />
    <br>
</center>
where the left one is with only kinematics calculation, and the right one is with kinematics and dynamics calculation.



---

# 2022

### 1. A simple trajectory generation and control demo for the two-link arm robot in the CoppeliaSim

This is a simple demonstrated project for the trajectory planning and control in Coppliasim with a two-link arm robot.

The trajectory for the robot arm is generated with the Position-Velocity-Time (PVT) trajectory interpolation, *i.e*, a polynomial trajectory interpolation approach.

The control of the simple robot arm is with PID joint position controllers.

There is a robot kinematics model for the two-link arm robot, pleas refer to the source code on [github](https://github.com/chauby/two_link_arm_in_coppeliasim) for details



The demonstrated videos can be found as follows：

1.The demo for the simple control of the robot arm, with two joints.

<center>
    <img src="/images/projects/SimpleDemoTwoLinkCoppeliaSim/two_link_demo_1.gif" alt="picture not found" style="zoom:100%;" />
    <img src="/images/projects/SimpleDemoTwoLinkCoppeliaSim/two_link_demo_2.gif" alt="picture not found" style="zoom:100%;" />
    <br>
</center>


2.The demo for the trajectory planning and control with some given via-points.

<center>
    <img src="/images/projects/SimpleDemoTwoLinkCoppeliaSim/two_link_trajectory.gif" alt="picture not found" style="zoom:100%;" />
    <br>
</center>

