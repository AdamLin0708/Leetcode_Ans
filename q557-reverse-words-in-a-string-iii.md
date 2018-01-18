# 557. Reverse Words In A String III

Problem: [https://leetcode.com/problems/reverse-words-in-a-string-iii/description/](https://leetcode.com/problems/reverse-words-in-a-string-iii/description/)

作法：

* 先將word從string中切開
* 個別去反轉後join再一起即是答案

Language: Ruby

Method:

* String split: [https://ruby-doc.org/core-2.2.0/String.html\#method-i-split](https://ruby-doc.org/core-2.2.0/String.html#method-i-split)
* String reverse: [https://ruby-doc.org/core-2.2.0/String.html\#method-i-reverse](https://ruby-doc.org/core-2.2.0/String.html#method-i-reverse)
* Array join: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-join](http://ruby-doc.org/core-2.2.0/Array.html#method-i-join)
* \(本題可加可不加\)String squeeze: [https://ruby-doc.org/core-2.4.0/String.html\#method-i-squeeze](https://ruby-doc.org/core-2.4.0/String.html#method-i-squeeze)

```
# @param {String} s
# @return {String}
def reverse_words(s)
    
    # 作法：
    # 先將word從string中切開
    # 個別去反轉後join再一起即是答案
   
    s_split = s.split    
    res = []
    
    for i in 0...s_split.length
        s_split[i] = s_split[i].reverse        
        res.push(s_split[i])
    end
    
    ans = res.join(' ').squeeze(' ')
    
    return ans
        
end
```





