# Class 35: Graphs

## [Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)


A graph is a non-linear data structure that can be looked at as a collection of `vertices` (or `nodes`) potentially connected by line segments named `edges`.

### Glossary:

| Term | Definition |
| --- | --- |
| Vertex | A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices. |
| Edge | An edge is a connection between two nodes. |
| Neighbor | The neighbors of a node are its adjacent nodes, i.e., are connected via an edge. |
| Degree | The degree of a vertex is the number of edges connected to that vertex. |

<br>

---

<br>

## Directed vs Undirected

### <u>Undirected Graphs</u>

An `Undirected Graph` is a graph where each edge is <u>undirected</u> or <u>bi-directional</u>. This means that the undirected graph does not move in any direction.

![Undirected Graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

>The undirected graph we are looking at has 6 vertices and 7 undirected edges.
>
>Vertices/Nodes = {a,b,c,d,e,f}
>
>Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}

### <u>Directed Graphs (Digraph)</u>

A `Directed Graph` also called a `Digraph` is a graph where every edge is directed.

Unlike an undirected graph, a `Digraph` has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

![Directed Graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

>The directed graph above has six vertices and eight directed edges
>
>Vertices = {a,b,c,d,e,f}
>
>Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}

<br>

---
<br>

## Complete vs Connected vs Disconnected

### Complete Graphs

A complete graph is when all nodes are connected to all other nodes.

![Complete Graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/CompleteGraph.PNG)

### Connected

A connected graph is graph that has all of vertices/nodes have at least one edge.

![Connected Graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/ConnectedGraph.PNG)

### Disconnected

A disconnected graph is a graph where some vertices may not have edges.

![Disconnected Graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DisconnectedGraph.PNG)




























