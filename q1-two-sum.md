# 1. Two Sum

Problems: [https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

作法一：暴力法

Languages: JS

```
var twoSum = function(nums, target) {
    // 想法一：
    // for loop依序去檢查 若有就output，不然跑完for loop就return false

    //從index 0~nums.length 去配對 看有沒有答案
    for(i=0;i<=nums.length;i++){
        for(var j=i+1;j<=nums.length;j++){
            if(nums[i] + nums[j] == target){
                return [i,j];
            }
        }
    }        
};
```

作法二：透過Hash紀錄index跟value

1. 以一個hash table 紀錄每一筆對應的index跟value
2. 每一次iterate，先找number\_t_o\__find是否有在hash table內 \(number\_t_o\__find = target - nums\[i\]
3. 若有，則回傳該number\_t_o\__find在hash內的index，跟當下iterate number
4. 若無，則將該iterate number跟nums\[i\]加到hash table內

Languages: Ruby

```
def two_sum(nums, target)
    
    hash = {}
    ans = []
        
    for i in 0...nums.length
        number_to_find = target - nums[i]
        if hash.has_value?(number_to_find)
            ans = [hash.key(number_to_find), i]
        else
            hash[i] = nums[i]
        end        
    end
    
    return ans
    
end
```



