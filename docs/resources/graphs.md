---
title: "Grafos"
---


# Grafos

## Introducción a Grafos

- Slides de Nico Lehmann sobre Grafos (muy buenas):
  - <http://campamento2015.progcomp.cl/material> (revisar la parte Grafos)
  - <http://campamento2016.progcomp.cl/material> (revisar la parte Grafos)
- (youtube) [Data structures: Introduction to graphs](https://youtu.be/gXgEDyodOJU)
- (youtube) [Data structures: Properties of Graphs](https://youtu.be/AfYqN3fGapc)
- (youtube) [Graph Representation part 01 - Edge List](https://youtu.be/ZdY1Fp9dKzs)
- (youtube) [Graph Representation part 02 - Adjacency Matrix](https://youtu.be/9C2cpQZVRBA)
- (youtube) [Graph Representation part 03 - Adjacency List](https://youtu.be/k1wraWzqtvQ)
- (youtube) [Graph Theory: 02. Definition of a Graph](https://www.youtube.com/watch?v=S1Zwhz-MhCs)
- (youtube) [Graph Theory: 03. Examples of Graphs](https://www.youtube.com/watch?v=lLOvB1qFE1E)
- (youtube) [Graph Theory: 04. Families of Graphs](https://www.youtube.com/watch?v=71XbdtoG7P8)
- (youtube) [Graph Theory: 36. Definition of a Tree](https://www.youtube.com/watch?v=QFQlxtz7f6g)
- Grafo dirigido vs Grafo no-dirigido:
  - (youtube) [Graph Types Directed and Undirected Graph](https://www.youtube.com/watch?v=amaH38_mXK4)
- (geeksforgeeks) [Graph and its representations](https://www.geeksforgeeks.org/graph-and-its-representations/)

## Algoritmos de Graph Traversal

- **Breadth First Search (BFS)**:
  - [cp-algorithms: BFS](https://cp-algorithms.com/graph/breadth-first-search.html)
  - [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/BFS.cpp)
- **Depth First Search (DFS)**:
  - [cp-algorithms: DFS](https://cp-algorithms.com/graph/depth-first-search.html)
  - [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/DFS.cpp)

- (youtube) [5.1 Graph Traversals - BFS & DFS -Breadth First Search and Depth First Search](https://www.youtube.com/watch?v=pcKY4hjDrxk)
- (youtube) [Graph Traversals - Breadth First and Depth First](https://www.youtube.com/watch?v=bIA8HEEUxZI)
- (youtube) [Graph : BFS, DFS](https://www.youtube.com/watch?v=ImMnYq2zP4Y)
- (youtube) [Algorithms: Graph Search, DFS and BFS](https://www.youtube.com/watch?v=zaBhtODEL0w)
- Flood Fill: <https://en.wikipedia.org/wiki/Flood_fill>

## Diámetro de un Árbol

- [cs.stackexchange: Algorithm to find diameter of a tree using BFS/DFS. Why does it work?](http://cs.stackexchange.com/questions/22855/algorithm-to-find-diameter-of-a-tree-using-bfs-dfs-why-does-it-work)
- [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/diameter_of_tree.cpp)

## Topological Sort

- (youtube) [Topological Sort Algorithm \| Graph Theory](https://www.youtube.com/watch?v=eL-KzMXSXXI)
- (youtube) [Topological Sort Graph Algorithm](https://www.youtube.com/watch?v=ddTC4Zovtbc)
- [Codeforces - How to check cycles inside a Topological Sort](https://codeforces.com/blog/entry/4907)
- [Códigos de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/TopoSort.cpp)

## Algoritmos de Camino Más Corto (Shortest Path)

- De un nodo (**single source**) a todos los demás nodos:
  - ##### Dijkstra (cuando **NO** hay aristas negativas)
    - (youtube) [Dijkstra's algorithm in 3 minutes — Review and example](https://www.youtube.com/watch?v=_lHSawdgXpI)
    - (youtube) [Dijkstra's Algorithm (5 minutos)](https://www.youtube.com/watch?v=gdmfOwyQlcI)
    - (youtube) [Muy buen ejemplo de Dijkstra](https://www.youtube.com/watch?v=5GT5hYzjNoo)
    - (youtube) [Correctness of Dijkstra's Algorithm](https://www.youtube.com/watch?v=ZjSvU2guTtY)
    - [cp-algorithms: dijkstra (incluye código de ejemplo)](https://cp-algorithms.com/graph/dijkstra.html)
    - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/Dijkstra.cpp)
    - [Código de ejemplo Ignacio](https://github.com/ignaciohermosillacornejo/apuntes_icpc/blob/master/graphs/dijsktra/dijsktra.cpp)
  - ##### Bellman-Ford (cuando **SÍ** hay aristas negativas)
    - (youtube) [Bellman-Ford in 5 minutes — Step by step example](https://www.youtube.com/watch?v=obWXjtg0L64)
    - (youtube) [Bellman-Ford in 4 minutes — Theory](https://www.youtube.com/watch?v=9PHkk0UavIM)
    - (youtube) [Bellman Ford Algorithm \| Shortest path & Negative cycles \| Graph Theory](https://youtu.be/lyw4FaxrwHg)
    - (video) [Bellman-Ford Algorithm: Proof of Correctness](https://es.coursera.org/lecture/algorithms-on-graphs/bellman-ford-algorithm-proof-of-correctness-txk8R)
    - (youtube) [Bellman Ford Algorithm - Single Source Shortest Path - Dynamic Programming (17m)](https://www.youtube.com/watch?v=FtN3BYH2Zes)
    - [cp-algorithms: bellman-ford (incluye códigos de ejemplo)](https://cp-algorithms.com/graph/bellman_ford.html)
    - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/BellmanFord.cpp)
    - ¿Cómo detectar un ciclo negativo con Bellman-Ford?
      - [GeeksforGeeks - Detect a negative cycle in a Graph \| (Bellman Ford)](https://www.geeksforgeeks.org/detect-negative-cycle-graph-bellman-ford/)
      - (PDF) [Proof of Correctness](https://web.stanford.edu/class/archive/cs/cs161/cs161.1168/lecture14.pdf)
- De todos los nodos (**multiple source**) a todos los nodos:
  - ##### Floyd-Warshall
    - (youtube) [Floyd–Warshall algorithm in 4 minutes](https://www.youtube.com/watch?v=4OQeCuLYj-4)
    - (youtube) [All Pairs Shortest Path (Floyd-Warshall) - Dynamic Programming (14m)](https://www.youtube.com/watch?v=oNI0rf2P9gE)
    - [cp-algorithms: floyd-warshall (incluye código de ejemplo)](https://cp-algorithms.com/graph/all-pair-shortest-path-floyd-warshall.html)
    - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/FloydWarshall.cpp)
    - ¿Qué pasa cuando hay ciclos negativos?
      - (wikipedia) [Behavior_with_negative_cycles](https://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm#Behavior_with_negative_cycles)
      - [Floyd-Warshall with negative cycles. How do I find all undefined paths?](https://stackoverflow.com/questions/15709277/floyd-warshall-with-negative-cycles-how-do-i-find-all-undefined-paths)

## Minimum Spanning Tree (MST)

- (youtube) [3.5 Prims and Kruskals Algorithms - Greedy Method](https://youtu.be/4ZlRH0eK-qQ)
- Kruskal's Algorithm:
  - (youtube) [Kruskal's algorithm in 2 minutes — Review and example](https://www.youtube.com/watch?v=71UQH7Pr9kU)
  - (youtube) [Kruskal's algorithm Minimum Spanning Tree Graph Algorithm](https://www.youtube.com/watch?v=fAuF0EuZVCk)
- Prim's Algorithm:
  - (youtube) [Prim's algorithm in 2 minutes — Review and example](https://www.youtube.com/watch?v=cplfcGZmX7I)
  - (youtube) [Prim's Algorithm Minimum Spanning Tree Graph Algorithm](https://www.youtube.com/watch?v=oP2-8ysT3QQ)
- Correcteness Proofs:
  - (youtube) [Proof of Cut Property](https://www.youtube.com/watch?v=P7K7mG8QDVM)
  - (youtube) [Proof of Prim's MST algorithm using cut property](https://www.youtube.com/watch?v=UfhUr5QzfiI)
  - (youtube) [Correctness of Kruskal's Algorithm](https://www.youtube.com/watch?v=S9PIItOUyzA)
- cp-algorithms:
  - [Minimum Spanning Tree - Prim's Algorithm](https://cp-algorithms.com/graph/mst_prim.html)
  - [Minimum Spanning Tree - Kruskal](https://cp-algorithms.com/graph/mst_kruskal.html)
  - [Minimum Spanning Tree - Kruskal with Disjoint Set Union](https://cp-algorithms.com/graph/mst_kruskal_with_dsu.html)
  - [Second best Minimum Spanning Tree - Using Kruskal and Lowest Common Ancestor](https://cp-algorithms.com/graph/second_best_mst.html)
- [Códigos de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/MinimumSpanningTree.cpp)

## Lowest Common Ancestor (LCA)

- General Overview of Methods:
  - <http://codeforces.com/blog/entry/16221> (skip to the LCA part)
- Método 1 (**RECOMENDADO**): Binary Lifting Method (aka [jump pointers](https://en.wikipedia.org/wiki/Level_ancestor_problem#Jump_pointer_algorithm)):
  - [Codeforces: Lowest common ancestor's binary lifting method for path queries on trees](http://codeforces.com/blog/entry/22325) Nota: como dice el post, este método es muy útil ya que se puede adaptar para computar consultas sobre caminos entre 2 nodos en un árbol.
  - (youtube) [Episode 17 - Binary Lifting](https://www.youtube.com/watch?v=kOfa6t8WnbI)
- Método 2: Euler Tour + Range Minimun Query:
  - [Topcoder: range minimum query and lowest common ancestor](https://www.topcoder.com/community/data-science/data-science-tutorials/range-minimum-query-and-lowest-common-ancestor/)
  - (youtube) [Episode 28 - Sparse Tables and LCA](https://www.youtube.com/watch?v=EKcQt-74bNw)
  - (youtube) [Sparse Table Algorithm Range Minimum Query](https://www.youtube.com/watch?v=c5O7E_PDO4U)
- [Códigos de ejemplo (ambos métodos)](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/LCA.cpp)

- Level Ancestor:
  - <https://en.wikipedia.org/wiki/Level_ancestor_problem>
  - <https://www.quora.com/Why-does-storing-log-N-pointers-work-in-the-jump-pointer-solution-of-the-level-ancestor-problem>
  - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/LA.cpp)

## Puntos de articulación, Aristas de corte y Componentes Biconexas

- (youtube) [Graph Theory: 53. Cut-Vertices](https://www.youtube.com/watch?v=BxAgmaLWaq4)
- (youtube) [Graph Theory: 55. Bridges and Blocks](https://www.youtube.com/watch?v=iGsxKUzW3cs)
- [HackerEarth: Articulation Points and Bridges](https://www.hackerearth.com/practice/algorithms/graphs/articulation-points-and-bridges/tutorial/)
- [HackerEarth: Biconnected Components](https://www.hackerearth.com/practice/algorithms/graphs/biconnected-components/tutorial/)
- (PDF) [MTL776 Graph algorithms: Cut vertices, Cut Edges and
Biconnected components](http://web.iitd.ac.in/~bspanda/biconnectedMTL776.pdf)
- (youtube) [5.2 Articulation Point and Biconnected Components](https://www.youtube.com/watch?v=jFZsDDB0-vo)
- (youtube) [Articulation Points Graph Algorithm](https://www.youtube.com/watch?v=2kREIkF9UAs)
- [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/articulation-points%2Ccut-edges%2Cbiconnected-components.cpp)
- Teoremas relevantes:
  - **Menger's Theorem**
    - <https://en.wikipedia.org/wiki/Menger%27s_theorem>
    - (youtube) [Menger's Theorem](https://www.youtube.com/watch?v=dUAeleBMRCQ)
    - <https://www.quora.com/How-can-I-prove-without-using-Mengers-theorem-that-any-two-vertices-of-a-2-connected-graph-lie-on-a-common-cycle>

## Strongly Connected Components (SCC)

- Método 1: Tarjan's Algorithm for SCC
  - (youtube) [Tarjans Strongly Connected Components algorithm \| Graph Theory](https://www.youtube.com/watch?v=TyWtx7q2D7Y)
  - (geeksforgeeks) [Tarjan’s Algorithm to find Strongly Connected Components](https://www.geeksforgeeks.org/tarjan-algorithm-find-strongly-connected-components/)
- Método 2: Kosaraju's Algorithm for SCC
  - (youtube) [Strongly Connected Components Kosaraju's Algorithm Graph Algorithm](https://www.youtube.com/watch?v=RpgcYiky7uw)
  - (geeksforgeeks) [Kosaraju's Algorithm to find Strongly Connected Components](https://www.geeksforgeeks.org/strongly-connected-components/)
  - (cp-algorithms) [Finding strongly connected components, Building condensation graph](https://cp-algorithms.com/graph/strongly-connected-components.html)
- (quora) [Diferencias entre Tarjan y Kosaraju](https://www.quora.com/Is-there-any-difference-or-advantages-or-disadvantages-between-Kosarajus-algorithm-and-Tarjans-algorithm-for-finding-strongly-connected-component-Which-one-is-most-useful)
- [Códigos de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/SCC.cpp)

## Flujo Máximo y aplicaciones

- (youtube) [Episode 33 - Maximum Flow Intuition](https://www.youtube.com/watch?v=K1i-wP82Zdo)
- Cuándo se usa:
  - (**MUY RECOMENDADO**) [(youtube) Ejemplos de problemas usando flujo](https://www.youtube.com/watch?v=nKcVc8XkFSA)
  - [geeksforgeeks: Maximum Bipartite Matching](http://www.geeksforgeeks.org/maximum-bipartite-matching/)
- Ford-Fulkerson Algorithm:
  - (youtube) [Ford-Fulkerson in 5 minutes — Step by step example](https://www.youtube.com/watch?v=Tl90tNtKvxs)
  - (youtube) [Residual Networks - Georgia Tech - Computability, Complexity, Theory: Algorithms](https://www.youtube.com/watch?v=XPpmzulEmjA)
  - (youtube) [Edmonds Karp Algorithm to find the Max Flow](https://www.youtube.com/watch?v=MczX0SM3I84)
  - (youtube) [Ford Fulkerson Algorithm Edmonds Karp Algorithm For Max Flow](https://www.youtube.com/watch?v=GiN3jRdgxU4)
  - Intuición detrás del grafo residual: [cs.stackexchnge: Residual Graph in Maximum Flow
](https://cs.stackexchange.com/questions/55041/residual-graph-in-maximum-flow)
- Dinic Algorithm (**RECOMENDADO**):
  - (youtube) [CS261 Lecture 2 (Edmonds-Karp/Dinic algorithms)](https://www.youtube.com/watch?v=uM06jHdIC70)
  - (PDF) [CMU, 15-451 Algorithms, Fall 2014: Lecture 11: Dinic’s Algorithm](http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15451-f14/www/lectures/lec11/dinic.pdf)
  - (PDF) [Stanford, CS261: A Second Course in Algorithms, Lecture #2: Augmenting Path Algorithms for Maximum Flow](http://theory.stanford.edu/~tim/w16/l/l2.pdf)
  - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Graphs/Dinic.cpp)

## Heavy-Light Decomposition

- <https://cp-algorithms.com/graph/hld.html>
- <https://blog.anudeep2011.com/heavy-light-decomposition/>
- <https://www.geeksforgeeks.org/heavy-light-decomposition-set-1-introduction/>
- <http://codeforces.com/blog/entry/22072>
