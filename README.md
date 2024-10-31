# Graph Node Selection Optimization

## Project Overview
This project explores different optimization techniques to solve a graph-based selection problem. Given a 20-node graph with weighted edges, the goal is to select 5 nodes that form a subgraph with the highest sum of edge weights. To achieve this, we implement and compare three algorithms:
1. **Brute-Force Search** - Finds the optimal solution by testing all possible combinations.
2. **Hill-Climbing** - A local search algorithm that iteratively moves to a neighbor with a higher value.
3. **Simulated Annealing** - A probabilistic technique that explores the solution space to avoid local optima.

The results of Hill-Climbing and Simulated Annealing are compared to the Brute-Force solution to evaluate their effectiveness in approaching the optimal solution.

## Problem Definition
In this task, we have:
- A fully connected graph with **20 nodes**.
- **Edge weights** assigned randomly between each pair of nodes.
- The objective is to select **5 nodes** that maximize the sum of edge weights among these nodes.

The algorithms implemented in this project aim to find or approximate the best possible selection of nodes that satisfies the objective.

## Algorithms Overview

### Brute-Force Search
The Brute-Force approach calculates all possible combinations of 5 nodes out of 20 and computes the sum of edge weights for each subset. This method guarantees the optimal solution but is computationally expensive due to the large number of possible combinations (over 15,000). 

### Hill-Climbing
The Hill-Climbing algorithm starts with a random selection of 5 nodes and iteratively moves to a neighboring selection with a higher edge sum. Here, two states are considered neighbors if they differ by exactly one node. While Hill-Climbing is more efficient than Brute-Force, it may get stuck in local optima since it always chooses the best immediate option without considering future moves.

### Simulated Annealing
Simulated Annealing is a probabilistic technique that explores the solution space with a "temperature" parameter, allowing the algorithm to occasionally accept suboptimal moves to escape local optima. Initially, the algorithm makes more frequent uphill moves, but as the temperature decreases, it gradually focuses on refining the best current solution. This enables a balance between exploration and convergence.

## Algorithm Comparison
Each algorithm was tested on multiple instances of the graph with randomized edge weights. This comparison highlights how close Hill-Climbing and Simulated Annealing can get to the optimal solution provided by the Brute-Force method.

- **Brute-Force**: Always finds the exact optimal solution but is time-consuming.
- **Hill-Climbing**: Often finds a near-optimal solution but may get trapped in local optima, missing the global maximum.
- **Simulated Annealing**: Typically finds results close to the optimal solution, often outperforming Hill-Climbing by avoiding local optima due to its probabilistic nature.

To assess the reliability of each method, the algorithms were run 10 times on graphs generated with different random seeds, and the results were recorded and compared.
