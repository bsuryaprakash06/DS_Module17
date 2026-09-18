# Ex22 Breadth First Graph
## DATE: 10 - 09 - 2026
## AIM:
To write a Java function to display the Breadth First Search graph traversal.

## Algorithm
1. Start the program.
2. Create a graph using adjacency list representation.
3. Start from a source node, mark it visited, and enqueue it.
4. While queue is not empty, dequeue a vertex and print it.
5. Get all adjacent vertices of the dequeued vertex. If an adjacent has not been visited, mark it visited and enqueue it.
6. End the program.

## Program:
```java
// Program to display the Breadth First Search graph traversal
// Developed by: Surya Prakash B
// RegisterNumber: 212224230281

import java.util.*;

class GraphBFS {
    private int V;
    private LinkedList<Integer> adj[];

    GraphBFS(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList();
    }

    void addEdge(int v, int w) {
        adj[v].add(w);
    }

    void BFS(int s) {
        boolean visited[] = new boolean[V];
        LinkedList<Integer> queue = new LinkedList<Integer>();

        visited[s] = true;
        queue.add(s);

        while (queue.size() != 0) {
            s = queue.poll();
            System.out.print(s + " ");

            Iterator<Integer> i = adj[s].listIterator();
            while (i.hasNext()) {
                int n = i.next();
                if (!visited[n]) {
                    visited[n] = true;
                    queue.add(n);
                }
            }
        }
    }

    public static void main(String args[]) {
        GraphBFS g = new GraphBFS(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);

        System.out.println("Breadth First Traversal starting from vertex 2:");
        g.BFS(2);
        System.out.println();
    }
}
```

## Output:
```text
Breadth First Traversal starting from vertex 2:
2 0 3 1 
```

## Result:
Thus, the Java function to display the Breadth First Search graph traversal is implemented successfully.
