# 1. Two Sum

Languages: JS

Problems: [https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

```
var twoSum = function(nums, target) {
    // 想法：
    //  for loop依序去檢查 若有就output，不然跑完for loop就return false

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



