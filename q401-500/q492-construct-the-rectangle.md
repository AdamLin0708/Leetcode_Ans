# 492. Construct The Rectangle

Problem: [https://leetcode.com/problems/construct-the-rectangle/description/](https://leetcode.com/problems/construct-the-rectangle/description/)

作法：

* 找出width, length
* 若是w &gt; l，則break
* 成對push到possible中
* 最後一個push的即為答案

Language: Ruby

```
# @param {Integer} area
# @return {Integer[]}
def construct_rectangle(area)
    
    possible = []
    
    for i in 1..area                
        w = i
        l = area/w
        
        next if area%w != 0
        break if w > l             
        
        possible.push([l, w])            
    end
    
    return possible.pop
    
end
```



