# 476. Number Complement

Problem: [https://leetcode.com/problems/number-complement/description/](https://leetcode.com/problems/number-complement/description/)

作法：使用XOR

* 如5 \(101\) 需 output 2\(010\)
  * 也就是 101 -&gt; 010 
  * 當 101^111 = 010
* 因此需要先找出input轉成二進位之後bit的長度\(bi\_len\)
* 再將 2 的 \(bi\_len\)次方 -1 設定給 x   
* 答案就是  x^num

Language: Ruby

Method:

* 轉成不同進位\(fixnum\): [http://ruby-doc.org/core-2.1.0/Fixnum.html\#method-i-to\_s](http://ruby-doc.org/core-2.1.0/Fixnum.html#method-i-to_s) 
* x的y次方: [http://ruby-doc.org/core-2.1.0/Fixnum.html\#method-i-2A-2A](http://ruby-doc.org/core-2.1.0/Fixnum.html#method-i-2A-2A)

```
# @param {Integer} num
# @return {Integer}
def find_complement(num)

    bi_len = num.to_s(2).length
    x = 2 ** bi_len - 1

    ans = x^num

    return ans

end
```



