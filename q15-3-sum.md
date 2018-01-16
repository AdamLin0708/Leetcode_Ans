# 15. 3Sum

Problems: [https://leetcode.com/problems/3sum/description/](https://leetcode.com/problems/3sum/description/)

作法：參考討論區的做法

---

1. 跑 for 迴圈，並且範圍是 0 .. nums.length-2  \(因為最少要三個一組，小於三個直接return）
2. 每跑一個iterate，先找出target值\(target = 0 - nums\[i\]\)
3. 接下來從剩下的Array前後開始找  \(  lo = i+1 ,   hi = nums.length-1  \)
4. 當nums\[lo\] + nums\[hi\] == target時，就將 nums\[i\], nums\[lo\], nums\[hi\] 放入ans array
   1. 處理lo跟hi的調整（當lo&lt;hi 且 nums\[lo\] == nums\[lo+1\] 則 lo = lo+1，同理處理hi，但hi = hi-1）
   2. 跑完兩個while之後，還要再處理一次lo++, hi--，不然最新的nums\[lo\], nums\[hi\]還是會跟原本的一樣
5. 當nums\[lo\] + nums\[hi\] &lt; target
   1. lo++
6. 當nums\[lo\] + nums\[hi\] &gt; target
   1. hi--

---

Language: Ruby

Method: 

* while loop in one line: [https://teamtreehouse.com/community/single-line-while-loop-with-brackets](https://teamtreehouse.com/community/single-line-while-loop-with-brackets)

```
# @param {Integer[]} nums
# @return {Integer[][]}
def three_sum(nums)

    # 先排序原本的nums
    nums = nums.sort            
    ans = []

    for i in 0...nums.length-2
        if ( i==0 || (i>0 && nums[i] != nums[i-1]) )
            lo = i+1
            hi = nums.length-1
            target = 0 - nums[i]                        

            while lo<hi do
                if nums[lo]+nums[hi] == target
                    ans.push([nums[i], nums[lo], nums[hi]])
                    lo = lo+1 while (lo<hi && nums[lo] == nums[lo+1])
                    hi = hi-1 while (lo<hi && nums[hi] == nums[hi-1])                                     
                    lo = lo+1
                    hi = hi-1
                elsif (nums[lo] + nums[hi] < target)
                    lo = lo+1
                else
                    hi = hi-1
                end
            end
        end
    end

    return ans

end
```



