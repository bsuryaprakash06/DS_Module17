# Ex25 Adjacency List Representation
## DATE:
## AIM:
To formulate the Java code to display the Adjacency List representation of a graph.

## Algorithm
1. Start the program.
2. Create an array of `ArrayLists` for the vertices.
3. Add an edge from u to v by adding v to the list at index u.
4. Print the adjacency list for each vertex.
5. End the program.

## Program:
```java
// Program to display the Adjacency List representation of a graph
// Developed by: Surya Prakash B
// RegisterNumber: 212224230281

import java.util.ArrayList;

public class AdjacencyList {
    static void addEdge(ArrayList<ArrayList<Integer>> adj, int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // For undirected graph
    }

    static void printGraph(ArrayList<ArrayList<Integer>> adj) {
        for (int i = 0; i < adj.size(); i++) {
            System.out.print("\nAdjacency list of vertex " + i + "\nhead");
            for (int j = 0; j < adj.get(i).size(); j++) {
                System.out.print(" -> " + adj.get(i).get(j));
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        int V = 5;
        ArrayList<ArrayList<Integer>> adj = new ArrayList<ArrayList<Integer>>(V);

        for (int i = 0; i < V; i++)
            adj.add(new ArrayList<Integer>());

        addEdge(adj, 0, 1);
        addEdge(adj, 0, 4);
        addEdge(adj, 1, 2);
        addEdge(adj, 1, 3);
        addEdge(adj, 1, 4);
        addEdge(adj, 2, 3);
        addEdge(adj, 3, 4);

        printGraph(adj);
    }
}
```

## Output:
```text
Adjacency list of vertex 0
head -> 1 -> 4

Adjacency list of vertex 1
head -> 0 -> 2 -> 3 -> 4

Adjacency list of vertex 2
head -> 1 -> 3

Adjacency list of vertex 3
head -> 1 -> 2 -> 4

Adjacency list of vertex 4
head -> 0 -> 1 -> 3
```

## Result:
Thus, the Java code to display the Adjacency List representation of a graph is implemented successfully.
