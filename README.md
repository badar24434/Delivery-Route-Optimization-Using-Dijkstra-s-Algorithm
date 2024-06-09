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


## Proof of Correctness for Dijkstra's Algorithm:

**Claim:** In Dijkstra's Algorithm, when a vertex `u` is included in the reached set, the distance computed by the algorithm `D(S , u)` is equal to the actual minimum distance `d(S , u)` from the source `S` to `u`.

**Proof:** (by contradiction)

Let's suppose the statement is false. That implies there exist some vertices for which, when `u` is included in the reached set, we have:

*D(S , u) > d(S , u)*

Let's denote `x` as the first vertex among these where this inequality holds, and assume `x` was included in the reached set.

This implies that all previous vertices, `z`, included in the reached set have:

\[ D(S,z) = d(S,z) \]

Now, let's consider the moment when vertex `x` is included in the reached set:

- Let `P` be the actual shortest path from `S` to `x`.
- Let `z` be the first vertex not in the reached set but on the shortest path `P`.
- Let `y` be the predecessor vertex of `z` on the shortest path `P`.

We have the following relations:

 *D(S,y) = d(S,y)*  (because `y` was included before `x`).

 *D(S,z) = D(S,y) + linkcost(y,z) = d(S,y) + linkcost(y,z)*  (by how `z` was chosen).

 *D(S,x) ≤ D(S,z)*  (because `x` is included after `z`).

Now, using the fact that a sub-path of a shortest path is itself a shortest path:

*d(S,x) = d(S,z) + d(z,x)*

We can now conclude:

*D(S,x) ≤ D(S,z)*
*= d(S,y) + linkcost(y,z)*
*≤ d(S,y) + linkcost(y,z) + d(z,x)*
*= d(S,x)*

This contradicts our assumption that *D(S,x) > d(S,x)*.

Therefore, our initial assumption must be false, and the statement holds *true* for **Dijkstra's Algorithm**.
