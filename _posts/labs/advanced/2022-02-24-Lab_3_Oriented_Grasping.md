---
title: "CSCI 4302 - Lab 3 - Oriented Grasping"
img-thumb: cansegmentation.png
img: cansegmentation.png
permalink: lab-oriented-grasping.html
---

The goal of this lab is to compute suitable grasp poses given an object-of-interest's pose.

You are provided with a perfect object detection pipeline that segments all objects in the crate.

Steps:

* Pick a single can, obtain its bounding object, and compute the position and orientation for grasping it. For this lab, you can limit yourself to grasping the cans at the center along its shorter width. Start with a simple world in which there is only one object to grasp and possible collisions are limited.
(Use the world with the "simple" extension). 

* Make sure you understand how the different coordinate systems on the robot add up and use the supervisor functionality to visualize poses relative to the robot.

* Implement a controller that grasps the can in any orientation. Bonus: can you adjust the orientation of the gripper so that you can grasp the can from any angle in the bin-picking world?

Deliverable: A Python script that grasps the cans it can see.

# Overview

In this lab, soda cans are presented randomly in a crate. The cans can be identified by Webot's buil-in [object recognition](https://www.cyberbotics.com/doc/reference/recognition) pipeline that augments the "camera" node by a ["segmentation image"](https://www.cyberbotics.com/doc/reference/camera#wb_camera_recognition_get_segmentation_image).
   
This lab consists of two worlds: an environment with a crate full of randomly placed cans and another environment with just one can on the table. 

## Required Files

- Download files from [Github](https://github.com/Introduction-to-Autonomous-Robots/labs/tree/main/csci4302manipulation/lab3_orientedgrasping)
- You will need to install the following libraries: open3d, spatialmath-python and transforms3d.

## Preliminaries

- Work through the example that helps you in detecting the cans, extract the point cloude for a can segemented in a specific color, and compute the grasp pose.
- Pay close attention to the way the centroid locations are translated into the robot's base frame. You will need to complete this computation.  



## Compute a grasp pose

- Use the existing code snippets to determine a suitable grasp pose based off an object of interest. 
- Compute grasp poses for the different cans based on the example given. You might need to experiment in a less complex environment using just one can on the table. Use transforms to compute the grasp pose from the object's centroid and orientation. This will require a translation, to reach the object from above, and a rotation, to make sure that the gripper is aligned correctly. 


# Deliverables

- A single Python file that implements your controller in the provided Webots world. The controller has to grasp a can that is presented in front of the robot. This lab can be submitted as a team effort. Please indicate all team members in the source code. You are encouraged to create a git repository to facilitate collaboration and track contributions. 
