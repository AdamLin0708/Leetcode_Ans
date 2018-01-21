# 598. Range Addition ll

Problem: [https://leetcode.com/problems/range-addition-ii/description/](https://leetcode.com/problems/range-addition-ii/description/)

作法一：暴力法（Time Limit Exceeded）

* 完成matrix
* 用hash紀錄數字出現次數
* 找到最大的數字，並且return出現次數

Language: Ruby

Method:

* 二維陣列的宣告: [http://ruby-doc.org/core-2.2.0/Array.html\#class-Array-label-Creating+Arrays](http://ruby-doc.org/core-2.2.0/Array.html#class-Array-label-Creating+Arrays)

```
# @param {Integer} m
# @param {Integer} n
# @param {Integer[][]} ops
# @return {Integer}
def max_count(m, n, ops)
    
    return m*n if ops.length == 0
    return ops[0][0]*ops[0][1] if ops.length == 1
    
    array = Array.new(m) { Array.new(n) }
    
    hash = {}
    for i in 0..ops.length
        hash[i] = 0
    end
    
    for i in 0...m
        for j in 0...n
            array[i][j] = 0
        end
    end
    
    for i in 0...ops.length
        x = ops[i][0]
        y = ops[i][1]
        
        for j in 0...x
            for k in 0...y
                array[j][k] = array[j][k] + 1            
            end
        end
    end
    
    for i in 0...array.length
        for j in 0...array[0].length
            hash[array[i][j]] = hash[array[i][j]] + 1
        end
    end
                    
    return hash[hash.length-1]
end
```

作法二：

* m = 3, n = 3, ops = \[ \[2,2\], \[3, 3\] \]
* 最後的陣列是
  \[ \[2,2,1\],   
    \[2,2,1\],  
    \[1,1,1\] \]

* 所以可以看出，是x方向最小值\(2\)以及y方向最小值\(2\)的交錯面積\(4\)

* 也就是答案為，min\( ops\[i\]\[0\] \) \* min\( ops\[i\]\[1\] \)

Language: Ruby

```
# @param {Integer} m
# @param {Integer} n
# @param {Integer[][]} ops
# @return {Integer}
def max_count(m, n, ops)
    
    ops_min_x = m
    ops_min_y = n
    
    for i in 0...ops.length
        ops_min_x = ops[i][0] if ops[i][0] < ops_min_x
        ops_min_y = ops[i][1] if ops[i][1] < ops_min_y
    end
    
    return ops_min_x * ops_min_y
end
```



