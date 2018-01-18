# 500. Keyboard Row

Problem: [https://leetcode.com/problems/keyboard-row/description/](https://leetcode.com/problems/keyboard-row/description/)

作法一：暴力法

* 檢查words中每一個word中的字元，是否有出現在line1 ~ line3，並用一個check紀錄
* 若是check = 1，代表僅在一種line出現，符合
* 若是check != 1，代表出現多次，或是根本不是符合的字元，則不符合

Language: Ruby

Method:

* String downcase: [https://ruby-doc.org/core-2.1.0/String.html\#method-i-downcase](https://ruby-doc.org/core-2.1.0/String.html#method-i-downcase)
* Array include?: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-include-3F](http://ruby-doc.org/core-2.2.0/Array.html#method-i-include-3F)
* \(補充\) String upcase: [https://ruby-doc.org/core-2.2.0/String.html\#method-i-upcase](https://ruby-doc.org/core-2.2.0/String.html#method-i-upcase)
* \(補充\) String capitalize: [https://ruby-doc.org/core-2.2.0/String.html\#method-i-capitalize](https://ruby-doc.org/core-2.2.0/String.html#method-i-capitalize)

```
# @param {String[]} words
# @return {String[]}
def find_words(words)

    # 想法：
    # 檢查words中每一個word中的字元，是否有出現在line1 ~ line3，並用一個check紀錄
    # 若是check = 1，代表僅在一種line出現，符合
    # 若是check != 1，代表出現多次，或是根本不是符合的字元，則不符合


    line1 = 'qwertyuiop'
    line2 = 'asdfghjkl'
    line3 = 'zxcvbnm'

    ans = []

    for i in 0...words.length
        word = words[i].downcase
        check = 0

        for j in 0...word.length
            x = line1.include?(word[j])
            if x == true
                check = check+1
                break 
            end 
        end
        for j in 0...word.length
            y = line2.include?(word[j])
            if y == true
                check = check+1
                break 
            end
        end
        for j in 0...word.length
            z = line3.include?(word[j])
            if z == true
                check = check+1
                break 
            end
        end                

        if check == 1
            ans.push(words[i])
        end
    end    

    return ans


end
```

作法二：使用 RegExp

Language: Ruby

RegExp Explain:

* "=~" 表示 match: [https://ruby-doc.org/core-2.1.1/Regexp.html\#class-Regexp-label-Alternation](https://ruby-doc.org/core-2.1.1/Regexp.html#class-Regexp-label-Alternation)
* "\[\]" 表示 裡面的字元都可以取: \[abcde\] =&gt; a or b or c or d or e 
* "\*" 表示 可以取多組: a\* =&gt; a, aa, aaa, aaa....
* "\|" 表示 or:   /\(condition1\) \| \(condition2\)/ 
* "^" 表示 開始
* "$" 表示 結束
* "/i" 表示 case sensitive

Method:

* Array select: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-select](http://ruby-doc.org/core-2.2.0/Array.html#method-i-select)

```
# @param {String[]} words
# @return {String[]}
def find_words(words)

    return words.select { |w| w =~ /^([qwertyuiop]*|[asdfghjkl]*|[zxcvbnm]*)$/i }    

end
```



