# 136. Single Number

Problem: [https://leetcode.com/problems/single-number/description/](https://leetcode.com/problems/single-number/description/)

作法一：用hash解決（但不符合 without extra space的條件）

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

作法二：用XOR

* 如 input是 11223
* 1^1^2^2^3 =&gt; \(1^1\)^\(2^2\)^3 =&gt; 0^0^3 =&gt; 3 

```
# @param {Integer[]} nums
# @return {Integer}
def single_number(nums)
    
    c = nums[0]
    
    for i in 1...nums.length
        
        c = c^nums[i]
        
    end
    
    return c
    
end
```



