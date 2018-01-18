# 617. Merge Two Binary Tree

Problem: [https://leetcode.com/problems/merge-two-binary-trees/description/](https://leetcode.com/problems/merge-two-binary-trees/description/)

作法:

* 透過recursive方式得到解
* 先設定base case
  * if t1 = nil, return t2
  * if t2 = nil, return t1
* 在設定rules
  * 新增一個node，val為當下的t1.val + t2.val
  * 對於node的left / right，再去跑遞迴

Languages: Ruby

Method: 由於Ruby並沒有Pointer，因此對於樹的建立會比較不同

* Implement tree with Ruby: [https://stackoverflow.com/questions/7196430/implementing-tree-with-ruby](https://stackoverflow.com/questions/7196430/implementing-tree-with-ruby)

```
# Definition for a binary tree node.
# class TreeNode
#     attr_accessor :val, :left, :right
#     def initialize(val)
#         @val = val
#         @left, @right = nil, nil
#     end
# end

# @param {TreeNode} t1
# @param {TreeNode} t2
# @return {TreeNode}
def merge_trees(t1, t2)
    
    # base case
    return t2 if t1 == nil
    return t1 if t2 == nil
    
    #rules
    node = TreeNode.new(t1.val+t2.val);
    node.left = merge_trees(t1.left, t2.left)
    node.right = merge_trees(t1.right, t2.right)
        
    return node
end
```





