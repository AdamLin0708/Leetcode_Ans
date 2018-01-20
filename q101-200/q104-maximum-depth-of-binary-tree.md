# 104. Maximum Depth Of Binary Tree

Problem: [https://leetcode.com/problems/maximum-depth-of-binary-tree/description/](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

作法：

* 在max\_depth內
  * 先處理特殊狀況
    * return 0 if root == nill
  * 將level預設為1，並透過find\_depth找尋左右兩個子樹的深度
* 在find\_depth內
  * return level if == nil

  * level++，並遞迴搜尋下去，回傳左子樹深度以及右子樹深度的最大值

Language: Ruby

Method: 

* Array Max: [https://ubuntuforums.org/showthread.php?t=368348](https://ubuntuforums.org/showthread.php?t=368348)

```
# Definition for a binary tree node.
# class TreeNode
#     attr_accessor :val, :left, :right
#     def initialize(val)
#         @val = val
#         @left, @right = nil, nil
#     end
# end

# @param {TreeNode} root
# @return {Integer}
def max_depth(root)
    
    return 0 if root == nil
    
    level = 1
    left = find_depth(root.left, level)
    right = find_depth(root.right, level)
    
    return [left, right].max
    
end

def find_depth(root, level)
    
    return level if root == nil
    
    level = level+1
    return [find_depth(root.left, level), find_depth(root.right, level)].max
    
end
```





