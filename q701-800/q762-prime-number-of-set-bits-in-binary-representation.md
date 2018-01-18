# 762. Prime Number Of Set Bits In Binary Representation

Problem: [https://leetcode.com/problems/prime-number-of-set-bits-in-binary-representation/description/](https://leetcode.com/problems/prime-number-of-set-bits-in-binary-representation/description/)

作法：

* for loop from l..r
* 每一筆element轉換成二進位制
* count 該二進位有幾個1
  * 若為prime，ans++
* 另外要自己寫一個 prime? function 去判斷是否為質數

Language: Ruby

Method:

* Array count: [http://ruby-doc.org/core-2.2.0/Array.html\#method-i-count](http://ruby-doc.org/core-2.2.0/Array.html#method-i-count)
* Math.sqrt: [https://ruby-doc.org/core-2.2.0/Math.html\#method-c-sqrt](https://ruby-doc.org/core-2.2.0/Math.html#method-c-sqrt)
* prime?: [https://stackoverflow.com/questions/11762043/how-can-i-test-if-a-value-is-a-prime-number-in-ruby-both-the-easy-and-the-hard/30196127](https://stackoverflow.com/questions/11762043/how-can-i-test-if-a-value-is-a-prime-number-in-ruby-both-the-easy-and-the-hard/30196127)

```
# @param {Integer} l
# @param {Integer} r
# @return {Integer}

def count_prime_set_bits(l, r)
    
    ans = 0
    
    for i in l..r
        bi = i.to_s(2)
        num_1 = bi.count('1')    
        if prime?(num_1)
            ans = ans+1
        end
    end
        
    return ans
    
end

def prime?(num)
    return false if num == 1
    
    for i in 2..Math.sqrt(num)
        return false if num % i == 0            
    end
    
    return true    
end
```



