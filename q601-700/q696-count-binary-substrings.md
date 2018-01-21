# 696. Count Binary Substrings

Problem: [https://leetcode.com/problems/count-binary-substrings/description/](https://leetcode.com/problems/count-binary-substrings/description/)

作法：參考討論區

* 如 「1100110111」可以把它拆成同樣bit一組的長度 group = 「2,2,2,1,3」
* 所以可以由group 去 iterate，group\[2\] = 2, group\[3\] = 1，代表可能為「110」或「001」，但不管是哪一種，可能的substrings就是min\(group\[2\], group\[3\]\)，也就是min\( group\[i\], group\[i+1\] \)
* 全部加起來即是所有的substrings數

Language: Ruby

```
# @param {String} s
# @return {Integer}
def count_binary_substrings(s)
    
    group = []
    
    check = 0
    
    for i in 0...s.length        
        check = check+1
        if i < s.length-1
            if s[i] == s[i+1]
                next
            else
                group.push(check)
                check = 0
            end
        else
            group.push(check)
        end
    end
    
    ans = 0
    
    for i in 0...group.length-1
        ans = ans + [group[i], group[i+1]].min
    end
    
    return ans
    
end
```



