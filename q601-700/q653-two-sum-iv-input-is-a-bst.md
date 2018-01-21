# 653. Two Sum IV - Input is a BST

Problem: [https://leetcode.com/problems/two-sum-iv-input-is-a-bst/description/](https://leetcode.com/problems/two-sum-iv-input-is-a-bst/description/)

作法：

* 先用 inorder 搜尋 tree，並且存取
* 再用  [Q1-Two-Sum](https://leetcode.com/problems/two-sum/description/)   的方式去找出答案

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
# @param {Integer} k
# @return {Boolean}
def find_target(root, k)
    
    # 代表是空樹，必為false
    return false if root == nil
    
    #使用一個array並透過left traversal存取tree element
    tree = []
    tree_push(root, tree)        
        
    #透過 #Q1-Two-Sum的方式，找出答案
    hash = {}
    
    for i in 0...tree.length
        number_to_find = k - tree[i]
        if hash.has_value?(number_to_find)
            return true
        else
            hash[i] = tree[i]
        end
    end
    
    return false
        
end

def tree_push(root, tree)
        
    return if root == nil
    
    tree_push(root.left, tree)
    tree.push(root.val)
    tree_push(root.right, tree)
    
    return    
end

```



