**# Full Scenario**
Since the outbreak of Covid-19, e-commerce has been one of the most preferred shopping centres for consumers. Even in 2024, the number of people purchasing online has witnessed a stable growth in the e-commerce contribution to the Malaysia’s gross domestic product (GDP). This also resulting in delivery companies to receive large quantities of parcels to be delivered to clients. Hurdle situations when a delivery person to convey items to a large number of households in a single journey as they never face before. Therefore, fast decision making is needed to cater the demand of customers and online sellers to ensure their product has arrived safely. They have to seek the quickest way possible during the trip to reduce delivery costs and time. When consumers actively purchase on online platforms such as Shopee, TikTok Shop, or Lazada, the number of required shipments increases daily. This demand surges even further during festive seasons, in response to monthly household needs, and during sales events organized by the e-commerce platforms themselves. As a result, the efficiency of optimizing pickup and delivery routes hinges on accurately calculating these routes among various shops within a complex road network. 

**# Why chose the project, include comparison of several other options and discuss the suitability of your proposed solution**
We noticed this issue and wanted to analyse the problem ourselves by suggesting the right algorithm to resolve the difficulty of determining the shortest path or route from a starting point to a final destination. This problem is also known as the shortest path issue which most solutions will call upon using graphs. The graph is either a directed graph or an undirected graph depending on whether one can walk along both sides or only one side of the edges. The most popular proposed algorithm for this issue is by using the Dijkstra’s based Greedy Algorithm where its ability to unravel the shortest path from one node to every other node inside the same graph data structure sets it apart from the others by also avoiding any edges with bigger weights. This shows that even only finding the shortest path from the starting node to another specific node, the algorithm searches for the shortest path to all other reachable vertices as long as the network is unchanged. This procedure continues until all the reachable nodes have been visited. This result a guaranteed shortest path from the source of destination by only running the Dijkstra’s algorithm once and preserve the outputs to be utilised again and over without having to redo the process. However, if the graph changes, you must restart the graph to guarantee that you have the most updated shortest route for your data structure.
There are a few other of the shortest path methods such as below :
     1.	Bellman-Ford Algorithm
     2.	Floyd-Warshall Algorithm
     3.	Johnson’s Algorithm
To compare with the other algorithms above, the Dijkstra’s algorithm works effectively to find out the location of the destination and distance in between. Also, it is more efficient and understandable for the researchers. Bellman-Ford algorithm is more versatile as it works when there is a negative weight edge and detects the negative weight cycle. The Bellman-Ford algorithm has less scalability and higher overheads, whereas Dijkstra's algorithm is more scalable and efficient. Other than that, Floyd-Warshall algorithm is an all-pairs shortest path algorithm used to find the shortest paths between all pairs of vertices in a weighted graph. The Floyd’s algorithm is only suitable for finding shortest paths between all pairs of vertices and inefficient for large graphs due to its high time complexity whereas Dijkstra’s has a lesser time complexity for its dense graphs and can generally find shortest path from a single-source problems. Lastly, Johnson’s algorithm is a an all pair shortest path which performs better than Floyd-Warshall algorithm. It works for all types of graphs given that negative cycles does not exist in that graph but Dijkstra’s algorithm is more memory efficient for a sparse graph as it does not need distance matrix to be represented as dense matrix making it more efficient for single-source issues. In conclusion, implementing the Dijkstra’s algorithm for this project is the optimal algorithm choice to calculate the shortest path for a delivery routes. Dijkstra’s algorithm excels in scenarios where the graph is large and sparse, and the edge weights are non-negative. The efficiency and scalability make it specifically suitable for single-source shortest path problems, ensuring that delivery routes are calculated swiftly and accurately. While other algorithms like Bellman-Ford, Floyd-Warshall and Johnson's have their own benefit unlike Dijkstra’s algorithm, it offers the best balance of computational efficiency and ease of implementation for the specific requirements of this project. By leveraging Dijkstra's algorithm, the project will gain from reduced computational overhead and enhanced performance, leading to more efficient and reliable route optimization for deliveries.


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

*D(S ,z) = d(S , z)*
 
Now, let's consider the moment when vertex `x` is included in the reached set:

- Let `P` be the actual shortest path from `S` to `x`.
- Let `z` be the first vertex not in the reached set but on the shortest path `P`.
- Let `y` be the predecessor vertex of `z` on the shortest path `P`.

### Graphical depiction of the situation:

![image](https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/164218215/3a632eff-490d-4196-9802-3292bbf2f38f)

We have the following relations:

 *D(S , y) = d(S , y)*  (The min. distance `S ⇒ y` computed by the algorithm = actual min. distance `S ⇒ y` because `y` in included before `x`).


 *D(S , z) = D(S,y) + linkcost(y , z) 
 = d(S , y) + linkcost(y , z)*  (by how `z` was chosen).


 *D(S , x) ≤ D(S,z)*  (because `x` is included after `z`).

### A sub path of a shortest path is itself a shortest path


![image](https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/164218215/fa64bf1a-aac0-4ee6-9572-8ee775de3965)


Now, using the fact that a sub-path of a shortest path is itself a shortest path:

*d(S , x) = d(S , z) + d(z , x)*

We can now conclude:

*D(S , x) ≤ D(S , z)*
*= d(S , y) + linkcost(y , z)*
*≤ d(S , y) + linkcost(y , z) + d(z , x)*
*= d(S , x)*

This contradicts our assumption that *D(S , x) > d(S , x)*.

Therefore, our initial assumption must be false, and the statement holds *true* for **Dijkstra's Algorithm**.

# Illustration Of The Problem 

The model to be analysed is the case of a package delivery service carried out by a courier from a drop point of PosLaju Seri Kembangan which is located at 1230, Jalan Sekolah, Kampung Baru Seri Kembangan, 43300 Seri Kembangan, Selangor. The number of customers served by a courier is more than 15 customers in one delivery trip depending on the density of demand. In this case, we will analysis for 17 customers in 12 locations in the Serdang area. Meanwhile, data about mileage is obtained from the Google Maps application. All this data is used to construct an initial model graph which is a connected weighted graph, where the location of the drop point or a customer is a vertex and the road connecting two locations is an edge of the graph. The weight in this graph is the distance travelled from the drop point to the customers or from one customer to another. We call the distance travelled is the mileage. Then, the Dijkstra algorithm is run on this graph where the drop point is the starting point of the route, such that the courier visits all customers and returns again to the drop point.

The flow of research methodology can be described as follows. First, collecting of customer location/address data. Then, processing location data into distance data travelled from one location to another. Second, constructing this data as an initial model i.e. a connected weighted graph. Third, running the Dijkstra algorithm on this graph so that the shortest route is obtained. This shortest route should visit all customers and return again to the drop point. Thus, this route is either a closed path (cycle) or a closed trail (circuit) that is a subgraph of the initial model graph.

The initial model graph is constructed from data on the number of customers, customer locations, the existence of roads connecting one location to another, road conditions travelled, and mileage between locations. The road connecting these locations must be passable by a motorcycle. In this model, if there is no road connecting 2 locations directly then there is no edge between the 2 locations. Thus, the initial model graph of this algorithm is a connected weighted graph, namely G, as shown in Figure 1. 

<img width="282" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/a79f3306-4ef1-4e1d-b4cf-392c94168e8e">

Figure 1 The Initial Model Graph G

Vertex 1 is the drop point of PosLaju Seri Kembangan which is the starting point or the initial vertex of the route. Vertex 2 until vertex 13 are customers who will be visited by a courier one by one sequentially according to the Dijkstra algorithm. The initial model constructed graph is not a complete graph because not all vertices are directly connected to other vertices by an edge. It is a graph with 13 vertices and 21 edges. Figure 2 shows a matrix adjacent of the initial model graph. Matrix elements are weights on the edges of the graph. The weight of the edges is the mileage from one location to another in meters. The element on the main diagonal of the matrix is zero, since there is no distance between the same vertices. This matrix is symmetrical, because the mileage from vertex i to vertex j is equal to the mileage from vertex j to vertex i. 

 ![Picture 1](https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/14cd7e83-ec00-4320-a583-147add3cb5b0)

Figure 2 Matrix Adjacent of Graph G

The steps of the Dijkstra algorithm work as follows. The first step is to establish a 
starting point with the status of having been found and has been visited. A courier picks up packages of goods sent to customers at the blabla drop point, so vertex 1 is the starting point of the route. Thus, the status of vertex 1 has been found and visited. The second step is to find other vertices that are adjacent to vertex 1. If these vertices have not yet found, then change their status to be found. However, if it has been found then only update the weight. The third step is to choose a vertex with a minimum weight to visit. 

This second and third steps result in a vertex always being found, if the vertex is connected to a vertex that has been visited (in fact, a vertex is found more than once if the vertex is connected to some vertices that have been visited). But not all vertex needs to be visited. In the optimization process, if a vertex does not have a minimum weight, then the vertex does not need to be visited. Next, we repeat the second and third steps, so that all vertices have been visited and the courier returns to the initial vertex (vertex 1). The following figure and table show the second and third steps in the first loop on Dijkstra algorithm. 

<img width="447" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/f63322f3-0fb0-48c3-b046-6412a33902d5">

Figure 3 Graph G in The First Loop of Dijkstra Algorithm

Vertex 1 has been determined as the starting point, so in Figure 3, vertex 1 is coloured blue to indicate it has been found and visited. The first row in Table 1 shows the route from vertex 1 to vertex 1 yields zero weight. In the second step, vertices 2, 3, 4, 5, 8, 9, 12, and 13 are adjacent to vertex 1. Then, these vertices are coloured by red (see Figure 3 on the left). Since {1, 9} is the edge with minimum weight of 60 meters, the next vertex to visit is vertex 9. So, vertex 9 is coloured by blue (see Figure 3 on the right). This is also shown in the ninth row of Table 1. 

<img width="237" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/4b3c01ba-1551-44c0-81a6-224e41b5412f">

Table 1 The Vertices Conditions in The First Loop of Algorithm Dijkstra

The next step is loop sequentially from second step to third step until the all of the courier returns again to vertex 1 as the starting point. The following figure shows the second and third steps in the fourth loop on Dijkstra algorithm. 

<img width="452" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/ae1633a9-6c4a-4506-ae6e-c71417f70e33">

Figure 4 Graph G in The Fourth Loop of Dijkstra Algorithm

Figure 4 on the left shows vertices 9, 10, and 11 have been found and visited, so these vertices are coloured by blue. While, vertex 12 has been found and coloured by red. Then, Figure 4 on the right shows vertex 12 has been visited, since vertex 12 is the only vertex found by vertex 11, so vertex 12 is coloured by blue. 

<img width="250" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/39af40c3-feaa-470b-8219-38c3306879e7">

Table 2 The Vertices Conditions in The Fourth Loop of Algorithm Dijkstra

The ninth until the twelfth rows in Table 3 show vertices 9, 10, 11, and 12 have been found and visited, vertices 2, 3, 4, 5, 8, and 13 have been found, while vertices 6 and 7 have not found. The route from vertex 1 to vertex 12 is (1, 9, 10, 11, 12) for a total weight of 400 meters.

In the fifth loop, we have found vertices 1 and 13, because vertex 12 adjacent to these vertices. But, vertex 1 has been visited. So, we must chose vertex 13 to visit. Since vertices 4, 3, and 2 are close together, we chose these vertices to visit sequentially on the 6th through 9th loops. Therefore, these three vertices have a status of having been visited and are coloured by blue. The route from vertex 1 to vertex 2 is (1, 9, 10, 11, 12, 13, 4, 3, 2) for a total weight of 1490 meters. 

We find out some vertices that have not yet visited, after visit vertex 2. Since vertex 2 is adjacent to vertices 1, 3, 8 and 13, so we find vertex 8. Since vertices 5, 6, 7, and 8 are close together, we chose these vertices to visit sequentially until on the final loops. Thus, the last customer to visit on this trip is vertex 5. 


<img width="262" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/4ee7e73c-b8ef-4bb3-9fd3-c92fa300b555">

Figure 5 Graph G in The Last Loop of Algorithm Dijkstra

Next, the courier must return to the starting point, vertex 1, to report the delivery results. This step from vertex 5 to vertex 1 is the last loop because there is only one road that connects directly between these vertices. Therefore, the final route at this trip as the shortest closed route as shown in Figure 5 is a cycle (1, 9, 10, 11, 12, 13, 4, 3, 2, 8, 7, 6, 5, 1) with a weight of 1890 meters as shown in the following table. 

<img width="365" alt="image" src="https://github.com/badar24434/Delivery-Route-Optimization-Using-Dijkstra-s-Algorithm/assets/115607585/66b405f8-e53e-40b7-9b5d-ee5857415407">

 Table 3 The Vertices Condition in The Last Loop of Algorithm Dijkstra

# Dijkstra's Algorithm Analysis

This repository provides an implementation of Dijkstra's algorithm using a Fibonacci heap, offering an efficient way to compute the shortest paths in a graph.

### Overview

The most efficient implementation of Dijkstra's algorithm leverages a Fibonacci heap. This data structure is a lazy heap, meaning it defers some operations to ensure others are extremely fast. The heap operations in a Fibonacci heap are very efficient due to its structure, where each node contains a pointer to its parent and one of its children, and a circular linked list connects the children nodes. This ensures that the heap maintains a pointer to the minimum distance node, facilitating very efficient operations.

### Time Complexity of Fibonacci Heap Operations Compared to Binary Heap

| Operation   | Binary Heap | Fibonacci Heap | Efficiency Improvement |
|-------------|-------------|----------------|------------------------|
| Insert      | O(log V)    | O(1)           | Significant improvement|
| ReturnMin   | O(1)        | O(1)           | No change              |
| DeleteMin   | O(log V)    | O(log V)       | No change              |
| Delete      | O(log V)    | O(log V)       | No change              |
| DecreaseKey | O(log V)    | O(1)           | Significant improvement|
| Merge       | O(1)        | O(1)           | No change              |

### Explanation of Efficiency Improvement

- **Insert**: The Fibonacci heap can perform insertions in constant time, O(1), compared to the O(log V) time in a binary heap. For \(n\) operations, this results in an improvement from O(log V) to O(1).

- **DecreaseKey**: Similarly, the DecreaseKey operation in a Fibonacci heap is O(1) compared to O(log V) in a binary heap. This leads to an overall improvement from O(log V) to O(1) for \(n\) DecreaseKey operations.

### Time Complexity Analysis
The use of a Fibonacci heap theoretically improves the efficiency of Dijkstra's algorithm, especially for dense graphs. The total time complexity for Dijkstra's algorithm with a Fibonacci heap is **O ( V log V+ E )** , where **V** is the number of vertices and **E** is the number of edges.

#### Worst Case Time Complexity

- **Time Complexity**: *O( E + V log V)*
- **Explanation**: The worst case involves multiple decrease key operations. With a Fibonacci heap, each decrease key operation takes *O(1)* time. Since the inner loop operations occur *O(V + E)* times, the total complexity is *O(E + V log V )*.

#### Average Case Time Complexity

- **Time Complexity**: *O(E + V log (E/V) V log V)*.
- **Explanation**: On average, the number of decrease key operations is limited by *O(V log (E/V))*. Multiplying this by the original complexity gives us the average time complexity of *O(E + V log (E/V) V log V)*.

#### Best Case Time Complexity

- **Time Complexity**: *O(E + V log V)*
- **Explanation**: In the best case, the algorithm performs fewer decrease key operations. The complexity remains *O(E + V log V)* due to the base complexity of Fibonacci heap operations.

#### Summary

Using a Fibonacci heap for Dijkstra's algorithm offers significant theoretical efficiency improvements, particularly for dense graphs:

- **Worst Case**: *O(E + V log V)*
- **Average Case**: *O(E + V log (E/V) V log V)*
- **Best Case**: *O(E + V log V)*
