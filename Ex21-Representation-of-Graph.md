# Ex21 Representation of Graph
## DATE: 10 - 09 - 2026
## AIM:
To formulate the Java code to display the Adjacency Matrix representation of a graph.

## Algorithm
1. Start the program.
2. Accept the number of vertices.
3. Initialize a 2D array of size V x V with zeros.
4. Add edges by setting array[i][j] = 1 (and array[j][i] = 1 for undirected).
5. Print the adjacency matrix.
6. End the program.

## Program:
```java
// Program to display the Adjacency Matrix representation of a graph
// Developed by: Surya Prakash B
// RegisterNumber: 212224230281

public class GraphMatrix {
    private boolean adjMatrix[][];
    private int numVertices;

    public GraphMatrix(int numVertices) {
        this.numVertices = numVertices;
        adjMatrix = new boolean[numVertices][numVertices];
    }

    public void addEdge(int i, int j) {
        adjMatrix[i][j] = true;
        adjMatrix[j][i] = true; // For undirected graph
    }

    public void removeEdge(int i, int j) {
        adjMatrix[i][j] = false;
        adjMatrix[j][i] = false;
    }

    public String toString() {
        StringBuilder s = new StringBuilder();
        for (int i = 0; i < numVertices; i++) {
            s.append(i + ": ");
            for (boolean j : adjMatrix[i]) {
                s.append((j ? 1 : 0) + " ");
            }
            s.append("\n");
        }
        return s.toString();
    }

    public static void main(String args[]) {
        GraphMatrix g = new GraphMatrix(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 3);
        System.out.println("Adjacency Matrix:\n" + g.toString());
    }
}
```

## Output:
```text
Adjacency Matrix:
0: 0 1 1 0 
1: 1 0 1 0 
2: 1 1 0 1 
3: 0 0 1 0 
```

## Result:
Thus, the Java code to display the Adjacency Matrix representation of a graph is implemented successfully.
