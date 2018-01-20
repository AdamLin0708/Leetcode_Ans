# 485. Max Consecutive Ones

Problem: [https://leetcode.com/problems/max-consecutive-ones/description/](https://leetcode.com/problems/max-consecutive-ones/description/)

作法：

* 遇到bit 0，就去比較累積的check跟目前max誰大
  * check大，就更換max = check
* 遇到bit 1，check++

Language: Ruby

Method:

* Loop Next 等同於 continue

```
# @param {Integer[]} nums
# @return {Integer}
def find_max_consecutive_ones(nums)
    
    # 想法：
    # 遇到bit 0，就去比較累積的check跟目前max誰大
    #     check大，就更換max = check
    # 遇到bit 1，check++
        
    max = 0
    check = 0
    
    for i in 0...nums.length
        if nums[i] == 0
            if check > max
                max = check                
            end
            check = 0
            next
        else
            check = check+1
        end            
    end
    
    max = check if check > max
        
    return max
        
end
```





