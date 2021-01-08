# Graphs

A visual representation of different variables relationship to one another

## Common Terms

- Vertex: a node that can have zero or more adjacent vertices

- Edge: connection between nodes

- neighbor: the adjacent nodes

- degreee: number of edges connected to a vertex

## Directed vs Undirected

### Undirected

edge is undirected or bi-directional. It does not grow or shrink in either direction
This happens when the edges have no specification

### Directed (Digraph)

when the edges have specific direction.

This kind of graph would have arrows pointing from one node to another

## Completed vs Connected vs Disconnected

### Complete

All nodes have a connection to other nodes

### Connected

Each node has at least one edge

### Disconnected

Some vertices may ahve no edges connected to them and thus they are disconnected

## Acyclic vs Cyclic

Acyclic is directed without cycles

If there are arrows, they do not lead in a cycle

Cyclic must be directed and must have cycles

## Graph Representation

### Adjacency Matrix

2-D array with n vertices giving a n by n array of Boolean values

The boolean is 1 if the intersecting nodes have an edge


