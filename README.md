# Optimizing Delivery Routes with Dijkstra's Algorithm

## Introduction

In general, the application of the **Dijkstra algorithm** is optimization in the problems of **computer networks**, **communication networks**, and **transport networks**. Theoretically, the **Dijkstra algorithm** is an algorithm used in determining routes in networks with minimum weight. This weight is the travel time, mileage, or cost needed during the trip through a route. This algorithm was found by **Edsger W. Dijkstra in 1956** (Ahmed, Ahmed, and Ahmed 2017). 

Thus, the **Dijkstra algorithm** can be used for the application of graph theory in the determination of the shortest route in the network of the package delivery service companies. The shortest route is generated by running the **Dijkstra algorithm** on the initial model graph, starting from the starting point to all other points and returning again to the starting point. Thus, this shortest route is a closed route traversed by a courier from a package delivery service company in a trip. 

#### Graph Theory in Delivery Optimization

The graphs used in this study are **simple and finite graphs**. A graph that is connected and its edges have a weight is called a **connected weighted graph**. This initial model graph is a connected weighted graph, where the weight is the mileage. We call a point in a graph a vertex. So, the starting point is the starting vertex. The shortest closed route generated from this algorithm can be either a **cycle** or a **circuit**. 

A cycle is a closed route that visits a vertex once, otherwise, it is a circuit. For example, **𝐶1 = (2, 3, 4, 2)** is a cycle, but **𝐶2 = (1, 2, 3, 4, 2, 3, 5, 1)** is a circuit in a graph, where **{1, 2, 3, 4, 5}** is a vertex set of this graph (Chartrand, Lesniak, and Zhang 2016).

#### Importance of Route Optimization

Optimal distribution management capabilities will have a major impact on all aspects, especially for freight package delivery service companies. Recently, there have been several studies related to delivery service optimization, namely the problem of routing vehicles with drones for delivery services using **ant colony optimization algorithms** (Huang et al. 2022), integrating clustering methodologies and routing optimization algorithms for last-mile parcel delivery (Ramírez-Villamil et al. 2022), multi-objective optimization of bicycle routes for last-mile package delivery with drop-off (Osaba et al. 2018), synchronized 
truck and drone routing in package delivery logistics (Das et al. 2020), and a multi-objective optimization approach to package delivery by the crowd of occupied taxis (Zhou et al. 2022).

In this article, we will determine the shortest route for delivery service by **PosLaju Malaysia** in **Selangor** using the **Dijkstra algorithm**.












# Optimizing Delivery Routes with Dijkstra's Algorithm

## Introduction

In general, the application of the **Dijkstra algorithm** is optimization in the problems of **computer networks**, **communication networks**, and **transport networks**. Theoretically, the **Dijkstra algorithm** is an algorithm used in determining routes in networks with minimum weight. This weight is the travel time, mileage, or cost needed during the trip through a route. This algorithm was found by **Edsger W. Dijkstra in 1956** (Ahmed, Ahmed, and Ahmed 2017). 

Thus, the **Dijkstra algorithm** can be used for the application of graph theory in the determination of the shortest route in the network of the package delivery service companies. The shortest route is generated by running the **Dijkstra algorithm** on the initial model graph, starting from the starting point to all other points and returning again to the starting point. Thus, this shortest route is a closed route traversed by a courier from a package delivery service company in a trip. 

## Graph Theory in Delivery Optimization

The graphs used in this study are **simple and finite graphs**. A graph that is connected and its edges have a weight is called a **connected weighted graph**. This initial model graph is a connected weighted graph, where the weight is the mileage. We call a point in a graph a vertex. So, the starting point is the starting vertex. The shortest closed route generated from this algorithm can be either a **cycle** or a **circuit**. 

A cycle is a closed route that visits a vertex once, otherwise, it is a circuit. For example, **𝐶1 = (2, 3, 4, 2)** is a cycle, but **𝐶2 = (1, 2, 3, 4, 2, 3, 5, 1)** is a circuit in a graph, where **{1, 2, 3, 4, 5}** is a vertex set of this graph (Chartrand, Lesniak, and Zhang 2016).

## Importance of Route Optimization

Optimal distribution management capabilities will have a major impact on all aspects, especially for freight package delivery service companies. Recently, there have been several studies related to delivery service optimization, namely the problem of routing vehicles with drones for delivery services using **ant colony optimization algorithms** (Huang et al. 2022), integrating clustering methodologies and routing optimization algorithms for last-mile parcel delivery (Ramírez-Villamil et al. 2022), multi-objective optimization of bicycle routes for last-mile package delivery with drop-off (Osaba et al. 2018), synchronized truck and drone routing in package delivery logistics (Das et al. 2020), and a multi-objective optimization approach to package delivery by the crowd of occupied taxis (Zhou et al. 2022).

## Other Algorithms in Optimization

Optimization can also use the **Prim algorithm** to design autonomous drone controls in packet delivery (Wirabudi, Hafiza, and Fachrurrozi 2022) and determine the shortest or fastest path in logistics distribution (Lusiani, Sartika, Habinuddin, et al. 2021). The Prim algorithm can be compared to the **Floyd-Warshall algorithm** in optimization to determine the shortest path (Ramadhan, Siahaan, and Mesran 2018). Using a methodology based on the **Prim Algorithm**, we can improve the reliability index using artificial immune system techniques by applying graph theory considerations to improve computational performance and Pareto's rule of dominance (Alonso, Oliveira, and De Souza 2014).

## Graph Theory Applications

As an application in graph theory, a study has been conducted by Ginting et al. in 2019 on delivery simulation using the **Dijkstra algorithm** to solve the problem of traveling salesmen (Ginting, Osmond, and Aditsania 2019). The application of graphs as models to a problem is not only in determining the shortest path and the fastest path. A graph is also used as a model on traffic congestion problems. 

In this article, we will determine the shortest route for delivery service by **PosLaju Malaysia** in **Kuala Lumpur** using the **Dijkstra algorithm**.

## Proof of Correctness

### Introduction
Let's denote the true shortest path distance of vertex \( v \) from the source \( s \) as \( \delta(v) \). Dijkstra’s algorithm estimates this by initially setting the distance to \( \infty \) for all vertices and then gradually lowering this estimate.

### Lemma 2.1
If \( d[v] = \delta(v) \) for any vertex \( v \) at any stage of Dijkstra’s algorithm, then \( d[v] = \delta(v) \) for the rest of the algorithm.

**Proof:**
- The distance \( d[v] \) cannot become smaller than \( \delta(v) \).
- Thus, the test condition in the RELAX() procedure will always fail once \( d[v] \) equals \( \delta(v) \).

### Theorem 2.1
Let \( \langle v_1 = s, v_2, \ldots, v_n \rangle \) denote the sequence of vertices extracted from the heap \( Q \) by Dijkstra’s algorithm. When vertex \( v_i \) is extracted from \( Q \), \( d[v_i] = \delta(v_i) \).

**Proof:**

1. **Base Case (First Vertex):**
   - For the initial vertex \( v_1 = s \):
     - \( d[s] = 0 \) since \( \delta(s) = 0 \) and all edge weights are positive.

2. **Induction Step:**
   - Assume for the first \( k-1 \) vertices that \( d[v_i] = \delta(v_i) \) holds for each \( i = 2, 3, \ldots, k-1 \).
   - Consider the \( k \)-th vertex \( v_k \) as it is extracted from \( Q \):
     - By the mechanics of Dijkstra's algorithm, \( d[v_k] \leq d[v_j] \) for any \( j > k \).
     - Assume the shortest path from \( s \) to \( v_k \) involves only vertices from the set \( R = \{v_1, \ldots, v_{k-1}\} \):
       - Hence, \( d[v_k] = \delta(v_k) \).

3. **Contradiction:**
   - Consider the first vertex \( v_q \) not in \( R \) on the shortest path from \( s \) to \( v_k \). Let \( v_p \) be the vertex before \( v_q \) on this path:
     - When \( v_p \) is deleted from \( Q \), \( d[v_q] = \delta(v_q) \) since all its edges were relaxed.
     - Since there are no zero-cost edges, \( \delta(v_q) < \delta(v_k) \), hence \( d[v_q] < d[v_k] \).
     - This contradicts the choice of \( v_k \) as the vertex for which \( d[v_k] \) is minimum when \( v_k \) is deleted from \( Q \).

Thus, \( d[v_i] = \delta(v_i) \) for all vertices \( v_i \).

### Visualization
Consider a simple weighted graph with vertices and edges, where weights represent the distance or cost between vertices.

1. **Initial Setup:**
   - Start at the source vertex \( s \) with \( d[s] = 0 \) and all other distances \( d[v] = \infty \).

2. **Iteration:**
   - Select the vertex with the smallest \( d[v] \) not yet processed.
   - Update the distances \( d[v] \) for all adjacent vertices using the relaxation step.
   - Continue until all vertices are processed.

### Summary
The correctness of Dijkstra's algorithm hinges on the property that once a vertex’s shortest path estimate is determined (when it’s removed from the priority queue), it remains correct. This ensures the algorithm consistently finds the shortest path in graphs with non-negative weights.
