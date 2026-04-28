# Longest Path NP-Complete Visualizer

An interactive web-based tool for visualizing the Longest Path problem, its NP-completeness proof, and practical algorithmic approaches.

This project was created for BCS 309 — Algorithms I.

---

## Project Overview

The Longest Path problem asks:

Given an undirected graph G = (V, E), two vertices s and t, and an integer k, does there exist a simple path from s to t with length at least k?

A simple path means a path with no repeated vertices.

This problem is important because it is NP-complete in general graphs, while the shortest path problem can be solved efficiently using algorithms like BFS or Dijkstra’s algorithm.

---

## Live Demo

Open the GitHub Pages link for this repository:

https://Avotru.github.io/longest-path-visualizer/


---

## Features

### Interactive Controls

The tool includes:

- Preset graph examples
- Custom graph input
- Start vertex s
- Target vertex t
- Required path length k
- Algorithm selection
- Speed slider
- Build Steps button
- Step button
- Step Back button
- Play / Pause buttons
- Replay Best Path button
- Reset button
- Step counter
- Status indicator

---

## Algorithms Implemented

### 1. Brute Force Exact Solver

The brute-force solver explores all possible simple paths from s to t.

It guarantees the correct longest path, but it may take exponential time because the number of simple paths can grow very quickly.

### 2. DFS Backtracking with Pruning

The practical solver uses:

- Current vertex
- Current path
- Visited set
- Best path found so far

It explores paths using DFS and backtracking.

The algorithm prunes a branch when it knows that even the best possible extension cannot reach the required length k.

This improves performance in practice, but the worst-case time complexity is still exponential.

### 3. DAG Dynamic Programming Demo

The tool also includes a DAG mode.

In a Directed Acyclic Graph, the longest path can be solved in polynomial time using:

- Topological ordering
- Dynamic programming

This demonstrates the difference between the general NP-complete case and a special graph class where the problem becomes easier.

---

## Visualizations

The project visualizes:

- The graph structure
- Current algorithm path
- Best path found
- Pruned branches
- Search tree states
- Pseudocode line highlighting
- Step-by-step explanations
- Live statistics
- Growth curve comparison
- NP-completeness reduction diagram

---

## NP-Completeness Proof

The tool includes a dedicated NP-completeness section.

### Step 1: Longest Path is in NP

A certificate is a proposed simple path from s to t.

The verifier checks:

1. The path starts at s
2. The path ends at t
3. Every consecutive pair of vertices is an edge in G
4. No vertex is repeated
5. The path length is at least k

All of these checks can be done in polynomial time.

Therefore, Longest Path is in NP.

---

### Step 2: Reduction from Hamiltonian Path

We reduce from Hamiltonian Path.

Given a Hamiltonian Path instance:

(G, s, t)

Construct a Longest Path instance:

(G, s, t, k = |V| - 1)

The graph, start vertex, and target vertex stay the same.

Only k is set to |V| - 1.

---

### Forward Direction

If the Hamiltonian Path instance is YES, then there is a simple path from s to t that visits every vertex exactly once.

A path visiting all |V| vertices has:

|V| - 1

edges.

So the Longest Path instance is also YES.

---

### Backward Direction

If the Longest Path instance is YES, then there is a simple path from s to t with length at least:

|V| - 1

A simple path in a graph with |V| vertices cannot have more than |V| - 1 edges.

So the path must visit all vertices exactly once.

Therefore, the original Hamiltonian Path instance is YES.

---

### Polynomial Time

The construction only copies the graph and computes:

k = |V| - 1

This takes polynomial time.

Therefore, Longest Path is NP-complete.

---

## Educational Content

The tool includes:

- Collapsible overview section
- Worked example
- Key concept boxes
- Counterexample showing why greedy choices can fail
- Exact vs approximation discussion
- Possible Q&A questions
- Understanding check quiz with answers

---

## How to Use the Tool

1. Choose a preset graph or enter your own graph.
2. Set the start vertex s.
3. Set the target vertex t.
4. Set the required length k.
5. Choose an algorithm:
   - Brute Force Exact Solver
   - DFS Backtracking with Pruning
   - DAG Dynamic Programming Demo
6. Click Build Steps.
7. Use Step or Play to watch the algorithm.
8. Open the other tabs to view:
   - NP-completeness proof
   - Comparison mode
   - Educational content
   - Understanding check
   - Possible Q&A

---

## Custom Graph Input Format

Enter one edge per line.

Example:

A B
B C
C D
D F
A E
E F

This creates an undirected graph with edges:

A-B, B-C, C-D, D-F, A-E, E-F

For DAG mode, the edge direction is interpreted as written.

Example:

A B
A C
B D
C D
D E
E F

means:

A → B
A → C
B → D
C → D
D → E
E → F

---

## Technology Used

This project is built using only:

- HTML5
- CSS3
- Vanilla JavaScript
- SVG

No external libraries or frameworks are used.

The entire project is contained in a single file:

index.html

---

## Project Files

index.html      Main interactive tool
README.md       Project description and usage guide

---

## Author

Zuhair Halawa

BCS 309 — Algorithms I
Spring 2026

---

## Copyright

© 2026 Zuhair Halawa.
Longest Path NP-Complete Visualizer.
All rights reserved.
