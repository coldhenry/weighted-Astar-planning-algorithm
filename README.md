# Weighted A* Planning Algorithm

<img src="https://github.com/coldhenry/Dynamic-Programming-and-Markov-Processes/blob/master/pic/env.png" width="120">

## Introduction

​	Weighted A* is the advanced version of A* algorithm, and also a common approach of Search-based planning algorithms. Original A* is composed of the Dijkstra’s algorithm and a heuristic function. Compared to original A* algorithm, Weighted A* provides a more flexible restriction on the selection of a path. The result would be sub-optimal but the efficiency increases. 



## Problem Formulation 

We formulate this problem as a **deterministic shortest path problem** and consider following basic elements:

1. Path: A sequence consists of all nodes in a given set.
2. All paths from two given nodes in a given set.
3. Path Length: The sum of the arc lengths over the path.
4. Objective: Find a path that has the smallest length from a given node to the other node.


## Technical Approach

### Label Correcting Algorithms (LCA)

Instead of visiting all nodes to compute the shortest path, LCA only visit a portion of nodes. It prioritizes the visited nodes i using the cost-to-arrive values. There are several ideas in this algorithm. 

First, we define a label g_i  that is an estimate of the lowest cost from node s to each visited node i. Each time g_i is reduced, the labels g_j, which node j is one of the children of node i, can be corrected 

<img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/LCA.png" width="120">

Furthermore, we create an OPEN set that contains set of nodes that can potentially be part of the shortest path to the goal. To be more precise, the nodes in OPEN set are the search frontier in every search iteration.


### Weighted A* algorithm

The A* algorithm is a modification to the LCA in which the requirement for admission to OPEN set is strengthened:

<img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/Astar1.png" width="360">

where h_j  is a positive lower bound on the optimal cost to get from node j to the goal and is known as heuristic.

By adding up a more stringent criterion can reduce the number of iterations required by the LCA. The heuristic is constructed depending on “special knowledge” about the problem. The more accurately                                 estimates the optimal cost from j to the goal, the more efficient the A* algorithm becomes. 

<img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/Astaralg.png" width="360">

### Implementation



### Test cases
There are seven scenarios, which are Single Cube/Window/Maze/Flappy Bird/Room/Tower/Monza.

### Results

| <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/default.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/default2.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/flappy1.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/flappy2.png" width="120"> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Single Cube**                                              |                                                              | **Flappy Bird**                                              |                                                              |
| <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/room1.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/room2.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/monza1.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/monza2.png" width="120"> |
| **Room**                                                     |                                                              | **Monza**                                                    |                                                              |
| <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/window1.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/window2.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/tower.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/otower2.png" width="120"> |
| **Window**                                                   |                                                              | **Tower**                                                    |                                                              |
| <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/maze1.png" width="120"> | <img src="https://github.com/coldhenry/weighted-Astar-planning-algorithm/blob/master/pic/maze2.png" width="120"> |                                                              |                                                              |
| **Maze**                                                     |                                                              |                                                              |                                                              |

