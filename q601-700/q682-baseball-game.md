# 682. Baseball Game

Problem: [https://leetcode.com/problems/baseball-game/description/](https://leetcode.com/problems/baseball-game/description/)

作法：

* 用一個num\_stack去記錄有效的num
* 判斷每一個ops
  * 若是整數，則丟進num\_stack
  * 若是C，則pop num\_stack
  * 若是D，則double num\_stack中最後放入的value，在push進num\_stack
  * 若是+，則把num\_stack最後放入的兩筆相加，把得到的value push進num\_stack

Language: Ruby

Method:

* String to\_i: [https://ruby-doc.org/core-2.0.0/String.html\#method-i-to\_i](https://ruby-doc.org/core-2.0.0/String.html#method-i-to_i)
* String is\_a? Integer: [https://stackoverflow.com/questions/4589968/checking-if-a-variable-is-an-integer](https://stackoverflow.com/questions/4589968/checking-if-a-variable-is-an-integer)
* Array pop: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-pop](http://ruby-doc.org/core-2.2.0/Array.html#method-i-pop)

```
# @param {String[]} ops
# @return {Integer}
def cal_points(ops)
    
    # 想法：
    # 用一個num_stack去記錄有效的num
    # 判斷每一個ops
    #     若是整數，則丟進num_stack
    #     若是C，則pop num_stack
    #     若是D，則double num_stack中最後放入的value，在push進num_stack
    #     若是+，則把num_stack最後放入的兩筆相加，把得到的value push進num_stack
    
    ans = 0
    num_stack = []
    
    for i in 0...ops.length
        
        if ((ops[i].to_i.is_a? Integer) && (ops[i].to_i != 0))                        
            num_stack.push(ops[i].to_i)
        end
                                        
        if ops[i] == 'C'                                               
            num_stack.pop
        end
        
        if ops[i] == 'D'
            num_stack.push(num_stack[num_stack.length-1]*2)          
        end
        
        if ops[i] == '+'
            num_stack.push((num_stack[num_stack.length-1]+num_stack[num_stack.length-2]))            
        end                
                        
    end
    
    for i in 0...num_stack.length
        ans = ans + num_stack[i]
    end
    
    return ans
            
    
end
```





