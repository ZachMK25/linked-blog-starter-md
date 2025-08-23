definition: finding a **continuous** path connecting a system


## visibility graph
- assume: robot is a point in 2D, obstacles are 2D polygons
- construct visibility graph:
	- nodes: 
		- starting point, goal points, vertices of obstacles
	- edges:
		- connect all nodes which are visible
		- include all edges of polynomial obstacles
- for graph based algorithms: e.g. dijkstra's, A*
- implement any graph search algo, e.g. dijkstra from start to goal
- **visibility** determined if can go from A to B without crossing an edge of an obstacle
	- vis algo example: for every 2 points in the graph (start/end, obstacle corners), draw a edge. Verify if it works by checking if there is an intersection with any other obstacle edge

## Dijkstra's Algorithm
- a solution to the single-source shortest path problem in graph theory
- works on both directed and undirected
- optimal
- greedy: visit the best (shortest path to get to) unvisited node
- input: weighted graph and source vertex, such that all edge weights are nonnegative
- output: lengths of shortest paths (or shortest paths themselves) from a given source vertex to all other vertices

- simplest implementation:
	- O(|V|^2 + |E|)
- In sparse graph: very few edges and many nodes
	- O(|E| + |V| log (|V|))


## Common questions
- what happens if instead of a point, we are using a robot/car that has additional width? How do we navigate the obstacles then?
	- inflate the obstacles' size to account for vehicles width
	- then resolve problem in same way
- 