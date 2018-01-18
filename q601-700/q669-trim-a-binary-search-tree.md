# 669. Trim A Binary Search Tree

Problem: [https://leetcode.com/problems/trim-a-binary-search-tree/description/](https://leetcode.com/problems/trim-a-binary-search-tree/description/)

作法: 參考討論區 

* Base case: 
  * 當root為nil，則return nil
  * 當root.val != l && root.val != r，則return root
  * 當root.val &lt; l，代表自己和本身的左子樹都已經不符合，因此return trim\_bst\(root.right, l, r\)
  * 當root.val &lt; r，代表自己和本身的右子樹都已經不符合，因此return trim\_bst\(root.left, l, r\)
* Recursive:
  * root.left = trim\_bst\(root.left, l, r\)
  * root.right = trim\_bst\(root.right, l, r\)

Language: Ruby

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
# @param {Integer} l
# @param {Integer} r
# @return {TreeNode}
def trim_bst(root, l, r)
    
    return nil if root == nil
    
    return trim_bst(root.right, l, r) if root.val < l
    return trim_bst(root.left, l, r) if root.val > r
    
    root.left = trim_bst(root.left, l, r)
    root.right = trim_bst(root.right, l, r)
    
    return root    
    
end
```



