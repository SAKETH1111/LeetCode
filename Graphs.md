# Topics in Graphs

## Basic
1. Intro to graphs 
2. Matrix DFS
3. Matrix BFS
4. Adjacency Lists
## Advanced
1. Dijkstra's
2. Prim's
3. Kruskal's
4. Topological Sort

## To Do List
- [ ] Understand the Basic Topics.
- [ ] Solve the Neet Code Basic Problem.
- [ ] Understand the Leet Code Cheat Sheet.
- [ ] Understand the Advanced Topics.
- [ ] Solve the Neet Code Advanced Problem.
- [ ] Solve the Microsoft,Apple,Facebook problems related to Tree.

## Understanding Graphs

1. In graphs, nodes are referred to as vertices and the pointers connecting these nodes are referred to as edges.
2. It is also possible that the nodes are not connected by any edges and this would still be considered a graph - `A Null Graph`.
3. The number of edges E, given the number of vertices V will always be less than or equal to V^2 . `𝐸 < = 𝑉 ^ 2`.
4. If the pointers connecting the edges together have a direction, we call this a `directed graph`. Examples `Trees` & `Linked List`.
5. If there are edges but no direction, this is referred to as an undirected graph.
6. Graphs are represented using the following:
  - Matrix
  - Adjacency Matrix
  - Adjacency List
8. Matrix Blocked - 0 Free - 1 0 is nodes.
9. Adjacency Matrix-  0 denotes that an edge does not exist between a given v1, v2, and 1 denotes the opposite. Less commonly used.
  - The issue with this is that if our graph has few edges it is not a good use of memory. Because it is a square matrix, the space complexity is 𝑂 ( 𝑉 ^2 ), where V is the number of vertices.
11. Adjacency List - Most common way.
    - This is also a two dimensional array. The convenience here is that we can declare it using a class called GraphNode and it contains a list attribute called neighbors, using which we can access all of a given vertex's neighbor.
    - This ends up being more space efficient because we only care about nodes that are connected.
```
  public class GraphNode {
    int val;
    List<GraphNode> neighbors;
    
    public GraphNode(int val) {
        this.val = val;
        this.neighbors = new ArrayList<GraphNode>();
    }
}
```
## Matrix DFS

1. DFS is Recursive in Nature

2.
   ```
   // Count paths (backtracking)
    int dfs(int[][] grid, int r, int c, int[][] visit) {
    int ROWS = grid.length, COLS = grid[0].length;

    if (Math.min(r, c) < 0 || r == ROWS || c == COLS ||
        visit[r][c] == 1 || grid[r][c] == 1 ) {
        return 0;
    }
    if (r == ROWS - 1 && c == COLS - 1) {
        return 1;
    }
    visit[r][c] = 1;

    int count = 0;
    count += dfs(grid, r + 1, c, visit);
    count += dfs(grid, r - 1, c, visit);
    count += dfs(grid, r, c + 1, visit);
    count += dfs(grid, r, c - 1, visit);

    visit[r][c] = 0;
    return count;
    }                       
    ```
   3. Island related problems can be done using DFS recursive.
  
   4. 
```
class Solution {
    public int numIslands(char[][] grid) {
        int count =0;
        int row = grid.length ;
        int column = grid[0].length;
        for(int i=0;i< row;i++){
            for(int j=0;j<column;j++){
                if(grid[i][j]=='1'){
                    dfs(grid,i,j);
                    count++;
                }
            }
        }
        return count;
        
    }
    public void dfs(char[][] grid,int r , int c){
        if(Math.min(r,c)<0 || r >(grid.length-1) || c > (grid[0].length-1) || grid[r][c]=='0'){
            return;
        }
        grid[r][c] = '0';
        dfs(grid,r+1,c);
        dfs(grid,r-1,c);
        dfs(grid,r,c+1);
        dfs(grid,r,c-1);
    }
}
```
## Matrix BFS
