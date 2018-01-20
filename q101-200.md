# 136. Single Number

Problem: [https://leetcode.com/problems/single-number/description/](https://leetcode.com/problems/single-number/description/)

作法：用hash解決

Language: Ruby

```
# @param {Integer[]} nums
# @return {Integer}
def single_number(nums)
    
    hash = {}
    
    for i in 0...nums.length
        hash[nums[i]] = 0
    end
    
    for i in 0...nums.length
        hash[nums[i]] = hash[nums[i]]+1
    end
    
    hash.each do |key, value|
        if value == 1
            return key
        end
    end
    
end
```



