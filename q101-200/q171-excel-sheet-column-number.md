# 171. Excel Sheet Column Number

Problem: [https://leetcode.com/problems/excel-sheet-column-number/description/](https://leetcode.com/problems/excel-sheet-column-number/description/)

作法：

* 每一個字元去對照表找到對應的index
* 再用該index \* 對應的26次方數
* 即是答案

Language: Ruby

```
# @param {String} s
# @return {Integer}
def title_to_number(s)

    comp = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'

    ans = 0

    for i in 0...s.length

        index = comp.index(s[i])+1

        ans = ans + index*26**(s.length-i-1)

    end

    return ans


end
```



