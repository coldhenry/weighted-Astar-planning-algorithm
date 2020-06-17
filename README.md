# Weighted A* Planning Algorithm

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



Furthermore, we create an OPEN set that contains set of nodes that can potentially be part of the shortest path to the goal. To be more precise, the nodes in OPEN set are the search frontier in every search iteration.



### Weighted A* algorithm

The A* algorithm is a modification to the LCA in which the requirement for admission to OPEN set is strengthened:



where h_j  is a positive lower bound on the optimal cost to get from node j to the goal and is known as heuristic.

By adding up a more stringent criterion can reduce the number of iterations required by the LCA. The heuristic is constructed depending on “special knowledge” about the problem. The more accurately                                 estimates the optimal cost from j to the goal, the more efficient the A* algorithm becomes. 

