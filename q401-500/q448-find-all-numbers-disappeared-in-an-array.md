# 448. Find All Numbers Disappeared In an Array

Problem: [https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/)

作法：參考討論區

* 透過兩次loop去完成
* 第一次loop
  * 根據nums\[i\] 找到對應的index，把該nums\[index\] 變成負數
* 第二次loop
  * 把nums中為正數的index，放到ans中，ans即為答案

Language: Ruby

```
# @param {Integer[]} nums
# @return {Integer[]}
def find_disappeared_numbers(nums)
    
    ans = []
    
    for i in 0...nums.length
        index = nums[i].abs-1
        nums[index] = -nums[index].abs
    end
    
    for i in 0...nums.length
        if nums[i] > 0
            ans.push(i+1)
        end
    end
    
    return ans
    
end
```





