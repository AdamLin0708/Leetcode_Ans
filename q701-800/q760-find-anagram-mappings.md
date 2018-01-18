# 760. Find Anagram Mappings

Problems: [https://leetcode.com/problems/find-anagram-mappings/description/](https://leetcode.com/problems/find-anagram-mappings/description/)

作法：

* 對 a 跑 for 迴圈，並且找到b中對應a\[i\]值的index值，push到ans內即可

Languages: Ruby

Method:

* array.push [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-push](http://ruby-doc.org/core-2.2.0/Array.html#method-i-push) 
* array.index [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-index](http://ruby-doc.org/core-2.2.0/Array.html#method-i-index)

```
# @param {Integer[]} a
# @param {Integer[]} b
# @return {Integer[]}
def anagram_mappings(a, b)

    ans = []

    for i in 0...a.length
        ans.push(b.index(a[i]))
    end

    return ans
end
```



