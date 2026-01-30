# Traveling Ethiopia Search Problem 

This project explores classic search techniques using a simplified map of Ethiopia, then brings those ideas to life through a 3D robotic simulation built with ROS 2 and Gazebo.

The work progresses step by step:

* Uninformed search (BFS, DFS)
* Cost-based search (UCS)
* Heuristic search (A*)
* Adversarial search (MiniMax)
* A ROS 2 robot that navigates the environment using search-based planning

---

## Prerequisites

**Programming Language**

* Python 3.x

**Core Python Libraries**

* `collections` (deque)
* `heapq`
* `math`

**Operating System**

* Ubuntu 24.04 (Noble Numbat) --for task 5

**Robotics Stack**

* ROS 2 Jazzy Jalisco
* Gazebo Harmonic (`gz-sim`)

---

## Project Structure & Tasks

### Question 1: Uninformed Search (BFS & DFS)

**Goal**
Model the Ethiopian city map as a state-space graph and explore it using uninformed search strategies.

**Implementation**

* The map is stored as a Python adjacency dictionary.
* **Breadth-First Search (BFS)**
  Uses a FIFO queue to find the shortest path in terms of number of hops.
* **Depth-First Search (DFS)**
  Uses a LIFO stack to explore paths deeply before backtracking.

**How to Run**

* Execute the Jupyter Notebook cell for **Q1**.

---

### Question 2: Uniform Cost Search (UCS)

**Goal**
Find optimal paths using cumulative travel cost (distance or price).

**Implementation**

* The graph is represented as a weighted adjacency dictionary.
* **Uniform Cost Search** uses a priority queue (`heapq`) ordered by total cost
  [
  g(n) = \text{cost from start to node } n
  ]
* **Multi-goal UCS**
  A custom loop dynamically visits multiple target cities (e.g. Axum, Lalibela, Bale) by repeatedly selecting the nearest unvisited goal, maintaining a locally optimal solution.

**How to Run**

* Execute the Jupyter Notebook cell for **Q2**.

---

### Question 3: A* Search (Heuristic Search)

**Goal**
Find the optimal route from **Addis Ababa** to **Moyale** using both actual cost and heuristic guidance.

**Implementation**

* Uses the A* evaluation function:
  [
  f(n) = g(n) + h(n)
  ]

  * ( g(n) ): actual cost traveled so far
  * ( h(n) ): heuristic estimate (straight-line distance to the goal)
* This approach significantly reduces unnecessary exploration and is the most efficient search used in the project.

**How to Run**

* Execute the Jupyter Notebook cell for **Q3**.

---

### Question 4: Adversarial Search (MiniMax)

**Goal**
Model a competitive scenario where an agent selects the best-quality coffee while an adversary attempts to reduce the agent’s payoff.

**Implementation**

* **Agent (Maximizer):** maximizes coffee quality (utility)
* **Adversary (Minimizer):** minimizes the agent’s utility
* A recursive **MiniMax** algorithm explores the game tree up to depth 3 and evaluates terminal states.

**How to Run**

* Execute the Jupyter Notebook cell for **Q4**.

---

## Summary

This project ties together theoretical AI search algorithms and practical robotics. You start with abstract graphs and end with a robot navigating a simulated version of Ethiopia, using the same planning logic under the hood. It’s a full pipeline from algorithms to motion.

