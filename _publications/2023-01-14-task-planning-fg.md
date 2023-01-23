---
title: "Task Planning in Factor Graph Representation"
collection: publications
permalink: /publication/2023-01-14-task-planning-fg
excerpt: 'This paper is about representing task planning problems in factor graphs.'
date: 2023-01-13
venue: 'Thesis'
paperurl: 'http://ywkim0606.github.io/files/Yoonwoo_thesis.pdf'
citation: 'Yoonwoo Kim. (2023). &quot;Task Planning in Factor Graph Representation.&quot; <i>Thesis</i>.'
---
Committee: Prof. Frank Delleart (Advisor), Prof. Matthew Gombolay, Prof. Danfie Xu

## Contribution
To expand the use of factor graphs in robotics problems, our first contribution is representing the classical planning problem in factor graphs. Our representation enables combining task planning with various robotics problems, such as motion planning, on a single framework. This opens up new approaches for problems like task and motion planning on a factor graph representation which can be solved by discrete-continuous optimization methods. Moreover, the representation naturally exposes actions that can be executed in parallel, allowing concurrent plans to be found. We test “classical planning using factor graphs” on scenarios that best exploit the advan- tages of concurrent plans, such as the gripper domain from IPC 1998 and the centralized multirobot planning environment.

Yet, the inference speed was too slow due to the exponential blow-up of discrete state space. Therefore, we made our second contribution, developing discrete probabilistic factor optimized for sparsity, which we call TableFactor. This factor ignores invalid states, for example, states that do not satisfy preconditions or effects, during computation reducing the execution time of factor multiplication by 19 times on average for sparse factors. We benchmark TableFactor against discrete probabilistic factor implemented in GTSAM varying the size and sparsity of the factors.

[Download paper here](http://ywkim0606.github.io/files/Yoonwoo_thesis.pdf)

<!-- Recommended citation: Yoonwoo Kim. (2023). "Paper Title Number 3." <i>Thesis</i>. 1(3). -->
