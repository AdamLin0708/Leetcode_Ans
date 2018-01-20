# 292. Nim Game

Problem: [https://leetcode.com/problems/nim-game/description/](https://leetcode.com/problems/nim-game/description/)

作法：

* 觀察後可發現，只要是4的倍數，就會輸

Language: Ruby

```
# @param {Integer} n
# @return {Boolean}
def can_win_nim(n)
    return n%4 == 0 ? false : true
end
```



