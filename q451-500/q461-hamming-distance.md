# 461. Hamming Distance

Problem: [https://leetcode.com/problems/hamming-distance/description/](https://leetcode.com/problems/hamming-distance/description/)

作法一：

* 將兩者先轉成二進位字串
* 並且將長度較短的補上0
* 比較兩字串同長度的部分，不一樣先count
* 剩下字串，有1就加
* 確保x&lt;y 

Language: Javascript

```
/**
 * @param {number} x
 * @param {number} y
 * @return {number}
 */
var hammingDistance = function(x, y) {
    //想法：將兩者先轉成二進位字串，並且將長度較短的補上0，比較兩字串同長度的部分，不一樣先count，剩下字串，有1就加上
    //     且確保x<y 

    //確保x<y
    if(x>y){
        var tmp = x;
        x = y;
        y = tmp;    
    }

    //轉為2進位字串
    x2Bi = x.toString(2);    
    y2Bi = y.toString(2);    

    //找長度差異
    var diff = y2Bi.length - x2Bi.length;

    //將x補0
    x2Bi = padLeft(x2Bi, diff+1);

    //比較每一位數，遇到不同的，count加上1
    var count = 0;
    for(var i=0;i<y2Bi.length;i++){
        if(x2Bi[i]!=y2Bi[i]){
            count++;
        }
    }

    return count;


};

function padLeft(str, len) {
    str = '' + str;    
    return new Array(len).join("0") + str;
}
```

作法二：參考討論區

* 使用XOR處理

Language: Ruby

Logic:

* XOR:  1^1 = 0, 1^0 = 1, 0^1 = 1, 0^0 = 0
* AND:  1&5 = 001&101 = 001 = 1
* &gt;&gt;:  5 = 101\(2\),  5 &gt;&gt; 1 = 010\(2\) = 2

```
# @param {Integer} x
# @param {Integer} y
# @return {Integer}
def hamming_distance(x, y)

    xor = x^y
    ans = 0

    while xor != 0 do
        ans = ans + (xor&1)
        xor = xor >> 1
    end

    return ans

end
```



