# 496. Next Greater Element I

Problem: [https://leetcode.com/problems/next-greater-element-i/description/](https://leetcode.com/problems/next-greater-element-i/description/)

作法一：不用hash但是用ruby function去處理

* iterate find\_nums
* 看find\_nums每一個element在nums中的index為何，從該index ~ nums.length找看看有無大於nums\[index\]的數字
  * 若有，則push到ans
  * 若無，則push -1到ans

Language: Ruby

```
# @param {Integer[]} find_nums
# @param {Integer[]} nums
# @return {Integer[]}
def next_greater_element(find_nums, nums)
    
    ans = []    
    for i in 0...find_nums.length
        for j in nums.index(find_nums[i])...nums.length
            if nums[j] > find_nums[i]
                ans.push(nums[j]) 
                break
            end
            if (j == nums.length-1) && (nums[j] <= find_nums[i])
                ans.push(-1)
            end                
        end               
    end
    
    return ans
end
```

作法二：用hashTable 紀錄 每一個find\_nums中的element在nums中的index

Language: Ruby

```
# @param {Integer[]} find_nums
# @param {Integer[]} nums
# @return {Integer[]}
def next_greater_element(find_nums, nums)
    
    ans = []
    
    hash = {}
    for i in 0...nums.length
        hash[nums[i]] = i
    end
    
    for i in 0...find_nums.length
        index = hash[find_nums[i]]
        for j in index...nums.length
            if nums[j] > find_nums[i]
                ans.push(nums[j]) 
                break
            end
            if (j == nums.length-1) && (nums[j] <= find_nums[i])
                ans.push(-1)
            end   
        end
    end
    
    return ans

end
```









