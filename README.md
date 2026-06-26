# Construction and Visualization of Shortest Paths in Transportation Networks

## Project Overview

This project focuses on the construction, testing, and comparison of shortest path algorithms on transportation networks. Transportation networks are important because they model real-world systems such as road maps, airline routes, and route-planning systems.

In these networks, locations are represented as nodes, and the direct connections between them are represented as edges. The main goal is to find the shortest path between selected source and target nodes using different shortest path algorithms.

The project compares several algorithmic approaches, measures their execution time, and shows how their performance changes across different transportation datasets.

## Selected Network Category

The selected network category is:

**Transportation Networks**

This category was chosen because transportation graphs are directly connected to real-world routing problems, such as finding the fastest route between cities, airports, or road intersections.

## Datasets Used

The datasets used in this project are transportation network datasets.

| Dataset        | Description                     |
| -------------- | ------------------------------- |
| inf-USAir97    | U.S. air transportation network |
| inf-euroroad   | European road network           |
| inf-roadNet-PA | Pennsylvania road network       |
| inf-roadNet-TX | Texas road network              |
| inf-road-usa   | Full U.S. road network          |

The datasets are stored in the `datasets/` folder.

## Graph Modeling

Each dataset is modeled as a graph:

* Nodes represent airports, road intersections, or transportation locations.
* Edges represent direct connections between nodes.
* The graphs are treated as undirected graphs.
* Edge weights represent the cost, distance, or connection weight between two nodes.
* The algorithms are tested using different source and target nodes.

This graph model allows shortest path algorithms to be applied and compared on real transportation-style networks.

## Algorithms Implemented

The project includes one algorithm from each required shortest path algorithm category.

### 1. Binary Heap Dijkstra

Binary Heap Dijkstra is used as the baseline shortest path algorithm. It uses a priority queue to always expand the node with the smallest known distance from the source.

This algorithm is reliable and guarantees the shortest path when all edge weights are non-negative.

### 2. A*

A* is a heuristic-guided shortest path algorithm. It uses the actual distance from the source and an estimated distance to the target to guide the search.

The main idea is to reduce unnecessary exploration by directing the search toward the target.

### 3. Bidirectional Dijkstra

Bidirectional Dijkstra performs two simultaneous searches: one from the source node and one from the target node.

The algorithm stops when the two searches meet. This can reduce the number of explored nodes compared to normal Dijkstra, especially when the source and target are far apart.

### 4. Planar-Style Road Graph Approach

The planar-style road graph approach is designed for road-like transportation networks. These networks are usually sparse and locally connected, meaning each node is connected to nearby nodes rather than many random distant nodes.

This approach uses the structure of road networks to support shortest path computation.

### 5. Multi-Level Dijkstra

Multi-Level Dijkstra is a preprocessing-based shortest path method.

The graph is divided into regions, boundary nodes are identified, and higher-level connections are used to speed up shortest path queries. The purpose of preprocessing is to reduce the amount of work needed during the actual query stage.

### 6. Distance Oracles

Distance Oracles are approximate or accelerated shortest path methods.

They use precomputed information to answer distance queries faster than running a full shortest path algorithm every time. This makes them useful when many shortest path queries need to be answered.

## Main Notebook

The full implementation is included in the notebook:

[Transportation_Networks.ipynb](Transportation_Networks.ipynb)

The notebook contains the implemented algorithms, dataset loading, testing code, and output results.

## Repository Structure

```text
Transportation-Networks-Shortest-Paths/
│
├── README.md
├── Transportation_Networks.ipynb
│
├── datasets/
│   ├── inf-USAir97.mtx
│   ├── inf-euroroad.edges
│   └── other transportation datasets
│
└── visuals/
    └── shortest path visualization files
```

## How to Run

1. Download or clone this repository.
2. Open `Transportation_Networks.ipynb` using Jupyter Notebook, JupyterLab, or Google Colab.
3. Make sure the datasets are inside the `datasets/` folder.
4. Run the notebook cells from top to bottom.
5. The notebook will load the datasets, run the algorithms, and display the results.

## Testing Method

Each algorithm is tested using multiple source-target pairs. For each test, the following values are recorded:

* Test number
* Source node
* Target node
* Shortest path distance
* Path length
* Number of explored nodes
* Execution time

This allows the algorithms to be compared based on correctness, speed, and search efficiency.

## Results

The results are displayed directly inside the notebook after running the test cells.

The comparison focuses on:

* Execution time
* Number of explored nodes
* Shortest path distance
* Path length
* Algorithm behavior across different datasets

The results show that each algorithm has different strengths depending on the graph size, graph structure, and the type of shortest path query.

## Visualizations

The visualization files are included in the `visuals/` folder.

These visualizations demonstrate the shortest path search process and show how the algorithms explore the graph and construct paths step by step.

## Team Contributions

| Member           | Contribution                                                           |
| ---------------- | ---------------------------------------------------------------------- |
| Marwan Sherif    | Multi-Level Dijkstra implementation, testing, and GitHub documentation |
| Hana El assal    | Binary Heap Dijkstra implementation and testing                        |
| Ziad Hossam      | A* implementation and testing                                          |
| Aley Anany       | Bidirectional Dijkstra implementation and testing                      |
| Kenzie Malek     | Planar-style road graph approach implementation and testing            |
| Hala El fiky     | Distance Oracles implementation and testing                            |
| Mohamed Rageh    | Visualizations                                                         |
| Karim Mohamed    | Presentation slides                                                    |
| Mohamed Elshafei | Testing and Github documentation                                       |

## Conclusion

This project compares several shortest path algorithms on transportation networks. The experiments show that algorithm performance depends on the graph structure, number of nodes, number of edges, and whether the algorithm uses heuristics or preprocessing.

Binary Heap Dijkstra works well as a baseline algorithm. A* and Bidirectional Dijkstra can reduce search effort in point-to-point queries. Multi-Level Dijkstra and Distance Oracles demonstrate how preprocessing can help speed up shortest path queries, especially when many queries are performed on the same graph.

Overall, transportation networks are a strong use case for shortest path algorithms because they represent real-world routing and navigation problems.

