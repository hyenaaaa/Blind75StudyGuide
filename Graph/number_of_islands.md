**Problem:** Number of Islands

**Difficulty:** Medium

**Description:** Given an m x n 2D binary grid grid which represents a map of '1's (land) and '0's (water), return the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Explanation:**
This one is pretty difficult at first unless you know some of the tricks. For starters, we make sure the grid actually has data in it. Then we iterate through the grid, and if we get to a '1' that is when we call our dfs function (depth first search) and increment our count. In the dfs function it's simple! We have a general base case so we don't go out of bounds and make sure each cell is a 1. Then we change the current cell to a pound sign so we know we visited that before and then call our dfs function 4 times for up, down, left, and right!


**Code(Python)**:

* Runtime: O(m * n), where m is the number of rows, and n is the number of columns.
```Python
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        # grid is empty, no islands
        if not grid:
            return 0
        
        count = 0
        # iterate through the grid
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                # if island found call depth first search function and increase our count
                if grid[i][j] == '1':
                    self.dfs(grid, i, j)
                    count += 1
        return count
    
    def dfs(self, grid, i, j):
        # base case, don't go out of bounds or we don't encounter land
        if i < 0 or j < 0 or i >= len(grid) or j >= len(grid[0]) or grid[i][j] != '1':
            return
        
        # change current cell to pound sign to show we already visited it
        grid[i][j] = '#'
        # recursively check each direction for more land of the island
        self.dfs(grid, i+1, j)
        self.dfs(grid, i-1, j)
        self.dfs(grid, i, j+1)
        self.dfs(grid, i, j-1)
```

**Code(C++)**:
* Runtime: 
```C++
class Solution {
public:

};
```
