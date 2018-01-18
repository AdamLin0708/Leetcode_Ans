# 412. Fizz Buzz

Problems: [https://leetcode.com/problems/fizz-buzz/description/](https://leetcode.com/problems/fizz-buzz/description/)

作法：

* 判斷是否為3或5的倍數，再將對應的字串放到ans

Language: Ruby

```
# @param {Integer} n
# @return {String[]}
def fizz_buzz(n)
    
    ans = []
    
    for i in 1..n        
        ans.push(i.to_s) if (i%3!=0 && i%5!=0)
        ans.push('Fizz') if (i%3==0 && i%5!=0)
        ans.push('Buzz') if (i%3!=0 && i%5==0)
        ans.push('FizzBuzz') if (i%3==0 && i%5==0)        
    end
    
    return ans
    
end
```





