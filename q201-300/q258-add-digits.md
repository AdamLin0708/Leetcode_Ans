# 258. Add Digits

Problem: [https://leetcode.com/problems/add-digits/description/](https://leetcode.com/problems/add-digits/description/)

作法：參考討論區

* 按照數學餘式定理來看 10^n Ξ 1\(mod 9\)
* 因此 a_n \* 10^n + ..... + a\_1 \* 10 + a\_0 _Ξ an + ..... + a1 + a0 \(mod 9\)
* 也就是說，只要找出 num % 9 即可
* 特殊狀況為  num == 0 要 return 0

Language: Ruby

```
# @param {Integer} num
# @return {Integer}
def add_digits(num)
    return num%9 != 0 ? num%9 : num == 0 ? 0 : 9
end
```



