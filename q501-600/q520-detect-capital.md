# 520. Detect Capital

Problem: [https://leetcode.com/problems/detect-capital/description/](https://leetcode.com/problems/detect-capital/description/)

作法：RegExp

* 要以/^開頭 $/結尾
* 中間的各種可能性要用 \| 串接
* 三種可能性
  * 全部大寫 \[A-Z\]\*
  * 第一個大寫，後面都小寫 \[A-Z\]\[a-z\]\*
  * 全部小寫 \[a-z\]\*

Language: Ruby

```
# @param {String} word
# @return {Boolean}
def detect_capital_use(word)

    # if word =~ /^[A-Z]*$/
    #     return true
    # end
    # if word =~ /^[a-z]*$/
    #     return true
    # end
    # if word =~ /^[A-Z][a-z]*$/
    #     return true
    # end

    return word =~ /^([A-Z]*|[a-z]*|[A-Z][a-z]*)$/ ? true: false

end
```



