**Problem:** Number of Islands

**Difficulty:** Medium

**Description:** Given an m x n 2D binary grid grid which represents a map of '1's (land) and '0's (water), return the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Explanation:**
<text here>


**Code(Python)**:

* Runtime: 
```Python
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        # grid is empty, no islands
        if not grid:
            return 0
        
        count = 0
        # iterate through thh
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
