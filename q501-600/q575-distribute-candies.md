# 575. Distributed Candies

Problem: [https://leetcode.com/problems/distribute-candies/description/](https://leetcode.com/problems/distribute-candies/description/)

作法：

* 先用hash存取目前共有幾種
* 比較hash.length跟candies.length/2
  * 若是hash.length大，表示最多只能拿到candies.length/2種 \(\[1,1,2,2,3,4\]\)
  * 若非，則表示最多就是hash.length種 \( \[1,1,1,1\] \)

Language: Ruby

```
# @param {Integer[]} candies
# @return {Integer}
def distribute_candies(candies)
    
    # 想法：
    # 先用hash存取目前共有幾種
    # 比較hash.length跟candies.length/2
    #     若是hash.length大，表示最多只能拿到candies.length/2種 ([1,1,2,2,3,4])
    #     若非，則表示最多就是hash.length種 ( [1,1,1,1] )
    
    hash = {}
    
    candies.each {|t| hash[t] = 0}
    candies.each {|t| hash[t] = hash[t] + 1 }
    
    return hash.length > candies.length/2 ? candies.length/2 : hash.length
                
end
```





