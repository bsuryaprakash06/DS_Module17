# Ex24 Topological Sort
## DATE:
## AIM:
To write a Java program to implement Topological Sort of a directed acyclic graph.

## Algorithm
1. Start the program.
2. Initialize an adjacency list representation of the DAG.
3. Perform DFS recursively, but don't print the node immediately.
4. After visiting all descendants, push the node into a Stack.
5. Once all nodes are visited, pop from the Stack and print.
6. End the program.

## Program:
```java
// Program to implement Topological Sort of a directed acyclic graph
// Developed by: Surya Prakash B
// RegisterNumber: 212224230281

import java.util.*;

public class TopologicalSort {
    private int V;
    private ArrayList<ArrayList<Integer>> adj;

    TopologicalSort(int v) {
        V = v;
        adj = new ArrayList<ArrayList<Integer>>(v);
        for (int i = 0; i < v; ++i)
            adj.add(new ArrayList<Integer>());
    }

    void addEdge(int v, int w) {
        adj.get(v).add(w);
    }

    void topologicalSortUtil(int v, boolean visited[], Stack<Integer> stack) {
        visited[v] = true;
        Integer i;

        Iterator<Integer> it = adj.get(v).iterator();
        while (it.hasNext()) {
            i = it.next();
            if (!visited[i])
                topologicalSortUtil(i, visited, stack);
        }
        stack.push(new Integer(v));
    }

    void topologicalSort() {
        Stack<Integer> stack = new Stack<Integer>();
        boolean visited[] = new boolean[V];
        for (int i = 0; i < V; i++)
            visited[i] = false;

        for (int i = 0; i < V; i++)
            if (visited[i] == false)
                topologicalSortUtil(i, visited, stack);

        while (stack.empty() == false)
            System.out.print(stack.pop() + " ");
    }

    public static void main(String args[]) {
        TopologicalSort g = new TopologicalSort(6);
        g.addEdge(5, 2);
        g.addEdge(5, 0);
        g.addEdge(4, 0);
        g.addEdge(4, 1);
        g.addEdge(2, 3);
        g.addEdge(3, 1);

        System.out.println("Topological Sort of the given graph:");
        g.topologicalSort();
        System.out.println();
    }
}
```

## Output:
```text
Topological Sort of the given graph:
5 4 2 3 1 0 
```

## Result:
Thus, the Java program to implement Topological Sort of a directed acyclic graph is implemented successfully.
