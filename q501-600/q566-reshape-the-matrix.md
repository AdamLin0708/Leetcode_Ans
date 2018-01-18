566. Reshape The Matrix

Problem: [https://leetcode.com/problems/reshape-the-matrix/description/](https://leetcode.com/problems/reshape-the-matrix/description/)

作法：

*     先把所有的數字以 row-traversing 放入 stack
*     比較stack.length跟 r\*c
  * 如果不一樣，代表無法產生reshape matrix，回傳nums
  *  如果一樣，代表可以reshape
    * 將stack內的element先按照c shift到row內
    * 把row push 到 ans 內
    * 回傳ans

Language: Ruby

Method:

* Array shift: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-shift](http://ruby-doc.org/core-2.2.0/Array.html#method-i-shift)

```
# @param {Integer[][]} nums
# @param {Integer} r
# @param {Integer} c
# @return {Integer[][]}
def matrix_reshape(nums, r, c)
    
    # 作法：
    # 先把所有的數字以 row-traversing 放入 stack
    # 比較stack.length跟 r*c
    #     如果不一樣，代表無法產生reshape matrix，回傳nums
    #     如果一樣，代表可以reshape
    #         將stack內的element先按照c shift到row內
    #         把row push 到 ans 內
    #         回傳ans
    
    stack = []
    ans = []
    
    nums.each do |num|        
        num.each do |element| 
            stack.push(element)            
        end      
    end
            
    return nums if (stack.length != r*c)
            
    for i in 0...r
        row = []
        for j in 0...c
            row.push(stack.shift)
        end
        ans.push(row)
    end
    
    return ans
    
    
end
```





