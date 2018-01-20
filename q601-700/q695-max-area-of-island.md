# 695. Max Area of Island

Problem: [https://leetcode.com/problems/max-area-of-island/description/](https://leetcode.com/problems/max-area-of-island/description/)

作法：參考討論區（使用DFS）

* 使用一個max紀錄目前最大的area
* 跑到一個grid\[i\]\[j\] == 1時，就去跑dfs
  * 當i, j 超過 grid邊際，且grid\[i\]\[j\] == 0，就return 0
  * grid\[i\]\[j\] = 0，表示已經探索過此island
  * return 1+dfs\(該island的上下左右格子\)

Language: Ruby

```
# @param {Integer[][]} grid
# @return {Integer}
def max_area_of_island(grid)
    
    max = 0
    for i in 0...grid.length
        for j in 0...grid[0].length
            if grid[i][j] == 1
                max = [max, dfs(grid, i, j)].max
            end
        end
    end
    
    return max
end
    
def dfs(grid, i, j)
    
    if( i<0 || i>= grid.length || j<0 || j>= grid[0].length || grid[i][j] == 0)
        return 0
    end
    
    grid[i][j] = 0
    return (1 + dfs(grid, i+1, j) + dfs(grid, i-1, j) + dfs(grid, i, j+1) + dfs(grid, i, j-1))
        
end
```







