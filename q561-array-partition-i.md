561. Array Partition I

Problems: [https://leetcode.com/problems/array-partition-i/description/](https://leetcode.com/problems/array-partition-i/description/)

作法：

* 先按照順序排好 nums array
* 把奇數位的相加即是答案

Languages: Ruby

```
# @param {Integer[]} nums
# @return {Integer}
def array_pair_sum(nums)
    
    return false if nums.length%2 != 0
    
    nums = nums.sort()
    
    i = 0
    ans = 0
    
    while i<nums.length do
        
        ans = ans + nums[i]
        i = i+2
        
    end
    
    return ans
    
    
end
```



