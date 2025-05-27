# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Start from the first vertex and try assigning each of the m colors.
2. For each color, check if it's safe (no adjacent vertex has the same color).
3. If safe, assign the color and move to the next vertex.
4. If all vertices are colored successfully, return the color assignment.
5. If no color leads to a solution, backtrack and try other colors.  

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if solveNQUtil(board,col+1)==True:
                return True
            board[i][col]=0
    return False
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] and colour[i] == c:
                return False
        return True

    def graphColoringUtil(self, m, colour, v):
        if v == self.V:
            return True

        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColoringUtil(m, colour, v + 1):
                    return True
                colour[v] = 0
        return False  

    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColoringUtil(m, colour, 0):
            print("Solution does not exist")
            return
        
        return colour
            

# Driver code
g = Graph(4)
g.graph = [
    [0, 1, 1, 1],
    [1, 0, 1, 0],
    [1, 1, 0, 1],
    [1, 0, 1, 0]
]
m = 3
colors = g.graphColouring(m)

if colors:
    print("Solution exist and Following are the assigned colours:")
    for c in colors:
        print(c, end=" ")
    print()

*/
```

## Output:

![image](https://github.com/user-attachments/assets/7936a4f5-3c3d-430a-8c44-51ada136e02e)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
