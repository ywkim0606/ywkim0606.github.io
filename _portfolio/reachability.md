---
title: "Reachability Map Visualization on an AR device."
excerpt: "Reachability map of 7-DoF mobile manipulator<br/><img src='/images/reach_visualization_w500.png'>"
collection: portfolio
---

# Introduction

## Problem description
As robots become more capable, smooth interaction between humans and robots has become
an important topic. However, as the appearance of the manipulator becomes increasingly
complex with many degrees of freedom, visualizing the workspace of a manipulator in one’s
head with intuition is difficult. For this reason, this project will tackle the problem of visualizing
the workspace of a 7 degrees of freedom redundant robot manipulator such as Fetch robot.
This project is related to mobile manipulation because visualizing the workspace of a robot
requires thorough understanding of the manipulator, and the project can further stretch to
moving the base of the robot while a human worker is informed about the workspace of the
manipulator for smooth interaction.

## Related work
Kunze [1] uses widely known frameworks such as, MoveIt and Rviz to visualize the workspace
of a 7-DOF robot manipulator. Nadal [2] shows boundaries of a non-redundant manipulator’s
workspace and various motion barriers and mobility losses within the workspace through
computation of certain generalized singularities. Maur [3] explains how a large point cloud in 3D
space can be meshified using a method called Delaunay Triangulation.

## Project Contribution
The main goal of this project is to visualize the workspace of a Fetch robot which can potentially
be a type of robot that can handle physical interaction with human workers. This is a
visualization problem. The output of this solution will be a 3D rendering of a Fetch robot’s
workspace which will give insight and better understanding for potential users of the robot.
