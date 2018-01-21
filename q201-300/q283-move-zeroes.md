# 283. Move Zeroes

Problem: [https://leetcode.com/problems/move-zeroes/description/](https://leetcode.com/problems/move-zeroes/description/)

作法：

* iterate with while loop
* 當碰到0，則delete，並讓num\_0 ++
* 最後再 push num\_0次 個 0 到 nums中即可完成

Language: Ruby

```
# @param {Integer[]} nums
# @return {Void} Do not return anything, modify nums in-place instead.
def move_zeroes(nums)
    
    iterate_time = nums.length
    num_0 = 0
    index = 0
    
    while iterate_time > 0 do 
        
        if nums[index] == 0
            nums.delete_at(index)
            num_0 = num_0 + 1
        else
            index = index + 1            
        end
        
        iterate_time = iterate_time-1        
        
    end
    
    for i in 0...num_0
        nums.push(0)
    end
    
    return nums
    
end
```



