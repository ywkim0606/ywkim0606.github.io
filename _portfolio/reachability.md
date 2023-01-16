---
title: "Reachability Map Visualization on an AR device."
excerpt: "Reachability map of 7-DoF mobile manipulator<br/><img src='/images/reach_visualization_w500.png'>"
collection: portfolio
---


# 1. Introduction

## 1.1 Problem description
As robots become more capable, smooth interaction between humans and robots has become
an important topic. However, as the appearance of the manipulator becomes increasingly
complex with many degrees of freedom, visualizing the workspace of a manipulator in one’s
head with intuition is difficult. For this reason, this project will tackle the problem of visualizing
the workspace of a 7 degrees of freedom redundant robot manipulator such as Fetch robot.
This project is related to mobile manipulation because visualizing the workspace of a robot
requires thorough understanding of the manipulator, and the project can further stretch to
moving the base of the robot while a human worker is informed about the workspace of the
manipulator for smooth interaction.

## 1.2 Related work
Kunze [1] uses widely known frameworks such as, MoveIt and Rviz to visualize the workspace
of a 7-DOF robot manipulator. Nadal [2] shows boundaries of a non-redundant manipulator’s
workspace and various motion barriers and mobility losses within the workspace through
computation of certain generalized singularities. Maur [3] explains how a large point cloud in 3D
space can be meshified using a method called Delaunay Triangulation.

## 1.3 Project Contribution
The main goal of this project is to visualize the workspace of a Fetch robot which can potentially
be a type of robot that can handle physical interaction with human workers. This is a
visualization problem. The output of this solution will be a 3D rendering of a Fetch robot’s
workspace which will give insight and better understanding for potential users of the robot.

# 2. Approach

## 2.1 Methodology
### 1) Randomly generate configurations of the Fetch robot
Fetch robot has 7 revolute joints. Therefore, configuration of the robot can be represented as a list containing 7 joint variables. Each joint variable is randomly generated within the corresponding joint limit. 100,000 configurations were generated using this method.
### 2) Derive end effector’s position in a 3D space
From each configuration, the end effector’s position can be derived using forward kinematics. The position of end effector can be written as (x,y,z) in 3D space and therefore, form a point cloud.
### 3) Delete points that will cause collision with the robot itself
Some end effector’s position may lie at an impossible coordinate for example inside the torso or below the surface. These points are deleted using a self collision check.
### 4) Meshify the remaining points using Delaunay Triangulation
Point cloud includes points within the workspace of the robot. If all points are shown, it is hard to identify the geometry or shape of the workspace. Therefore, using the delaunay triangulation algorithm, the point cloud is meshified to visualize only the outer surface.
Simplified pseudo code of the Delaunay Triangulation for better understanding: For each point:
Create a tetrahedron with neighboring points While not satisfying Delaunay criterion[3]:
Visit face neighbors
Gather list of faces forming boundary
Create tetrahedron from each point/face combination

## 2.2 Implementation
Randomly generating joint variables within the joint limits was done using numpy random. Forward kinematics was implemented from using the GTSAM library. To do self collision check, accurate description of geometry of the robot was needed. This information can be imported from the Fetch URDF file which is available in Fetch documentation website. Self collision check was done with the imported geometry of the Fetch robot and the randomly generated configurations using MoveIt library. There are a lot of python tools that can be used to meshify a point cloud. In this project, a library called “pygalmesh” was used which uses Delaunay Triangulation algorithm to create 3D meshes.

# 3. Results

<br/><img src='/images/pc_fig1.png'>

<br/><img src='/images/mesh_fig1.png'>

<br/><img src='/images/mesh_fig2.png'>

The results above is visualization of Fetch robot’s workspace using forward kinematics and sampling method. Future work can be visualizing the singularity configurations within the workspace for human workers to better understand the robot. When the end effector of a robot manipulator is close to the singular configuration, joint velocities can jump to infinity leading to uncontrollable end effector forces. This can cause problems for robots assigned delicate tasks such as surgery or painting. Therefore, it is important for humans to be able to identify singular configurations that might occur within the workspace of the robot. Also, there are other ways to visualize the workspace of a robot such as sweeping algorithms and it will be interesting to compare the final visualized workspace of these various methods.

# 4. Meta-learning
This project allows visualization of the proximate workspace of an actual robot. Although the method of sampling random configurations and using forward kinematics to visualize the workspace of a theoretical robot was explained in Kunze [2] there weren't cases where this method was actually used on a real robot manipulator. This project uses ROS, MoveIt, and Fetch library.

# 5. Bibliography
[1] D. Zlatanov, Generalized Singularity Analysis of Mechanisms. PhD thesis, University of Toronto, 1998.

[2] Kunze, Mirko. “On-the-Fly Workspace Visualization for Redundant Manipulators.” 2016.

[3] Nadal, Oriol Bohigas. “Numerical Computation and Avoidance of Manipulator Singularities.” Tesi doctoral - Universitat Politècnica de Catalunya. Institut d'Organització i Control de Sistemes Industrials, 2013.

[4] Spong, Mark W., Seth Hutchinson, M.Vidyasagar. Robot Modeling and Control. John Wiley & Sons, Inc., 2005.
