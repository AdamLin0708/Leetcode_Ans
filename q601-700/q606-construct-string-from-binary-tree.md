# 606. Construct String From Binary Tree

Problem: [https://leetcode.com/problems/construct-string-from-binary-tree/description/](https://leetcode.com/problems/construct-string-from-binary-tree/description/)

作法：

* 分成四種狀況
  * 左、右子樹 皆為 nil
  * 左子樹 nil，右子樹 != nil
  * 左子樹 = nil，右子樹 != nil
  * 左、右子樹 皆 != nil
* 按照四種狀況去做tree traversal

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

# @param {TreeNode} t
# @return {String}
def tree2str(t)
    
    return "" if t == nil
    
    s = []
    s.push(t.val)
    
    if t.right != nil && t.left != nil
        s.push('(')
        s.push(tree2str(t.left))
        s.push(')')
        s.push('(')
        s.push(tree2str(t.right))
        s.push(')')
    end
    if t.right != nil && t.left == nil
        s.push('(')        
        s.push(')')
        s.push('(')
        s.push(tree2str(t.right))
        s.push(')')
    end
    if t.right == nil
        if t.left != nil
            s.push('(')        
            s.push(tree2str(t.left))
            s.push(')')
        end
    end
        
    return s.join('')        
    
end

```



