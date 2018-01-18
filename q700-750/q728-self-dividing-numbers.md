# 728. Self Dividing Numbers

Problems: [https://leetcode.com/problems/self-dividing-numbers/description/](https://leetcode.com/problems/self-dividing-numbers/description/)

作法一： 暴力解

* 當&lt;10時，一定是self dividing
* 當&gt;=10時，將每一個位數的digit存起來，然後個別去除看看會不會都整除，都會的話就是self digit

Languages: Ruby

```
# @param {Integer} left
# @param {Integer} right
# @return {Integer[]}
def self_dividing_numbers(left, right)

    #Brute-Force
    #想法：
    # - 當<10時，一定是self dividing
    # - 當>=10時，將每一個位數的digit存起來，然後個別去除看看會不會都整除，都會的話就是self digit

    ans = []

    for i in left..right

        if i%10 == i
            ans.push(i)
        else            
            digit = []
            tmp = i
            check = 0

            while tmp/10 > 0 do                 
                digit.push(tmp%10)
                tmp = tmp/10                                
            end            
            digit.push(tmp)                          

            for j in 0...digit.length                        
                if digit[j] == 0                     
                    break
                else
                    check = check+1 if i%digit[j] == 0                                    
                end
            end

            ans.push(i) if check == digit.length
        end                
    end

    return ans

end
```

作法二：減少digit陣列的空間，參考討論區

* &lt; 10的數
  * i%\(j%10\) 必為 0，因此， j = j/10 = 0，跳出迴圈之後，透過if判斷式即可加入ans array
* &gt;= 10的數
  * 針對每一個digit去處理，遇到其中一個不整除的digit，就break，break當下的 j 未經過 j = j/10處理因此必不為0，因此不會通過if判斷式，也就不會加入ans array

Languages: Ruby

```
# @param {Integer} left
# @param {Integer} right
# @return {Integer[]}
def self_dividing_numbers(left, right)    

    ans = []

    for i in left..right
        j = i
        while j>0 do


            if (j%10 == 0 || (i % (j%10) != 0)) 
                break
            end
            j = j/10
        end
        if j == 0 
            ans.push(i)
        end
    end

    return ans

end
```



