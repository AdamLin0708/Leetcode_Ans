# 693. Binary Number With Alternating Bits

Problem: [https://leetcode.com/problems/binary-number-with-alternating-bits/description/](https://leetcode.com/problems/binary-number-with-alternating-bits/description/)

作法：

* 轉成二進位
* 跟相鄰bit比較是否相同
  * 相同， return false
  * 都不同，return true

Language: Ruby

```
# @param {Integer} n
# @return {Boolean}
def has_alternating_bits(n)
    
    bi = n.to_s(2)
    
    for i in 0...bi.length-1
        if bi[i] == bi[i+1]
            return false
        end
    end
    
    return true
    
end
```





