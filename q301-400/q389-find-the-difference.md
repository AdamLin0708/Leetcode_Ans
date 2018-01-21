# 389. Find The Difference

Problem: [https://leetcode.com/problems/find-the-difference/description/](https://leetcode.com/problems/find-the-difference/description/)

作法：

* loop，先用一個index\_s紀錄在s中t\[i\]出現的index
  * 若是nil，代表在s中不存在t\[i\]，直接回傳t\[i\]
  *  若不是nil，則計算該字元分別在s, t中出現的次數
    * 若相同，則loop繼續
    * 若不同，則回傳t\[i\]

Language: Ruby

```
# @param {String} s
# @param {String} t
# @return {Character}
def find_the_difference(s, t)
        
    # 想法：
    # loop，先用一個index_s紀錄在s中t[i]出現的index
    #     若是nil，代表在s中不存在t[i]，直接回傳t[i]
    #     若不是nil，則計算該字元分別在s, t中出現的次數
    #         若相同，則loop繼續
    #         若不同，則回傳t[i]
    
    for i in 0...t.length
        
        index_s = s.index(t[i])
        if index_s == nil
            return t[i]
        else
            count_s = s.count(s[index_s])
            count_t = t.count(t[i])
            
            return t[i] if count_s != count_t
        end
        
    end            
        
end
```



