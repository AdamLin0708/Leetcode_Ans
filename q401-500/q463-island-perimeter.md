# 463. Island Perimeter

Problem: [https://leetcode.com/problems/island-perimeter/description/](https://leetcode.com/problems/island-perimeter/description/)

作法：參考討論區

* 由最簡單的例子可以找到規律為 island\*4 - near\*2

Language: Ruby

```
# @param {Integer[][]} grid
# @return {Integer}
def island_perimeter(grid)

    island = 0
    near = 0

    for i in 0...grid.length
        for j in 0...grid[i].length
            if grid[i][j] == 1
                island = island+1
                if ((i < grid.length-1) && (grid[i+1][j] == 1)) 
                    near = near+1 
                end
                if ((j < grid[i].length-1) && (grid[i][j+1] == 1))                 
                    near = near+1 
                end
            end
        end
    end

    return island*4-near*2

end
```



