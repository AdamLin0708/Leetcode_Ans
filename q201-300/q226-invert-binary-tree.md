# 226. Invert Binary Tree

Problem: [https://leetcode.com/problems/invert-binary-tree/description/](https://leetcode.com/problems/invert-binary-tree/description/)

作法：

* basic case
  * return nil if root == 1 
* recursive case
  * 用一個tmp = TreeNode.new\(1\) 來做替換
  * tmp = left
  * left = invert\(right\)
  * right = invert\(left\)
* 完成

Langauge: Ruby

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
# @return {TreeNode}
def invert_tree(root)
    
    #basic case
    return nil if root == nil
    
    #recursive case
    tmp = TreeNode.new(1)
    tmp = root.left
    root.left = invert_tree(root.right)
    root.right = invert_tree(tmp)
    
    return root
end
```



