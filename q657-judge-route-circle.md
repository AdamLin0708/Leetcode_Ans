# 657. Judge Route Circle

Problem: [https://leetcode.com/problems/judge-route-circle/description    ](https://leetcode.com/problems/judge-route-circle/description/)

作法：

* 用hash記錄每一個走法走了幾次
* 比較hash\['U'\] == hash\['D'\] && hash\['L'\] == hash\['R'\] 
* 若一樣，則return true
* 若不一樣，則return false

Language: Ruby

Method: 

* hash 初始化: [https://docs.ruby-lang.org/en/2.4.0/Hash.html](https://docs.ruby-lang.org/en/2.4.0/Hash.html)

```
# @param {String} moves
# @return {Boolean}
def judge_circle(moves)

    # 想法：用hash記錄每一個走法走了幾次，最後在比較UD, LR次數是否一樣

    hash = { 'U'=>0, 'D'=>0, 'L'=>0, 'R'=>0 }

    for i in 0...moves.length        
        hash[moves[i]] = hash[moves[i]] + 1        
    end

    if hash['U'] == hash['D'] && hash['L'] == hash['R']
        return true
    else
        return false
    end

end
```



























