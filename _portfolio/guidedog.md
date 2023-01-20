---
title: "Teaching a Robotic Guide Dog to Walk with Human User."
excerpt: "Human gait visualization<br/><img src='/images/guidedog_w500_2.png'>"
collection: portfolio
---

<p align="center">
  <img src='/images/guidedog_w500.png'>
</p>

## Abstract
Although guide dogs can have crucial influence on the lives of visually impaired people, training the dogs are resource heavy. Therefore, there have been several efforts to transition to robotic guide dog systems. In this paper, we teach a quadrupedal robot to walk with its human user by leveraging recent reinforcement learning techniques that teach quadrupedal robots to walk in the real world. Our method is divided into two separate steps namely, pertraining and finetuning. In the pretraining step, a locomotion policy is trained in simulation using a reference motion of a dog. In the finetuning step, we test two hypotheses. First, we test how stably a policy can walk when human gait force is applied. Second, we test if policy can be fine-tuned to follow the direction of the human gait force by introducing additional reward in the fine-tuning step. We observed that pre-training the motion imitation model with random perturbations is effective when the goal is to walk stably when human gait force is applied. However, when the goal changes to moving in the direction of the applied human gait force, due to the adversarial nature of the original reward and the newly introduced reward, the policy underperforms.

## Contributions
• We formulate tasks for robot guide dogs that use rigid harness in RL, which is the first attempt, to the best of our knowledge.

• We propose new reward designs to additionally train policies to follow human feedback.

• We introduce a LSTM classifier to distinguish human feedback force

# Technical Report
[Technical Report](http://ywkim0606.github.io/files/guidedog_project.pdf)
