# Ex23 Depth First Graph
## DATE: 12 - 09 - 2026
## AIM:
To write a Java code to display the Depth First Search graph traversal using recursion.

## Algorithm
1. Start the program.
2. Represent the graph using an adjacency list.
3. Mark the current node as visited and print it.
4. Recursively call DFS for all unvisited adjacent nodes.
5. End the program.

## Program:
```java
// Program to display the Depth First Search graph traversal using recursion
// Developed by: Surya Prakash B
// RegisterNumber: 212224230281

import java.util.*;

class GraphDFS {
    private int V;
    private LinkedList<Integer> adj[];

    GraphDFS(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList();
    }

    void addEdge(int v, int w) {
        adj[v].add(w);
    }

    void DFSUtil(int v, boolean visited[]) {
        visited[v] = true;
        System.out.print(v + " ");

        Iterator<Integer> i = adj[v].listIterator();
        while (i.hasNext()) {
            int n = i.next();
            if (!visited[n])
                DFSUtil(n, visited);
        }
    }

    void DFS(int v) {
        boolean visited[] = new boolean[V];
        DFSUtil(v, visited);
    }

    public static void main(String args[]) {
        GraphDFS g = new GraphDFS(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);

        System.out.println("Depth First Traversal starting from vertex 2:");
        g.DFS(2);
        System.out.println();
    }
}
```

## Output:
```text
Depth First Traversal starting from vertex 2:
2 0 1 3 
```

## Result:
Thus, the Java code to display the Depth First Search graph traversal is implemented successfully.
