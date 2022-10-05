---
title: 'Binary Tree'
description: 'Binary Tree is a tree structure in which eacho node only contains at most two children'
keywords:
  - leetcode
  - tutorial
  - binary tree
  - data structure
---

<TutorialAuthors names="@wingkwong"/>

## Overview

Binary Tree is a tree structure in which each node only contains at most two children, often referred as left and right child.

<!-- TODO: properties -->
## Properties
- The number on nodes on level '_l_' is equal to the 2<sup>_l_</sup>, like on level 0 (root node) we got 2<sup>0</sup>=1 node only.
- The Maximum number of nodes in a binary tree of height ‘h’ is 2<sup>h</sup> – 1. 

## Traversal 

There are different ways to traverse trees - In-order, Pre-order, and Post-order. Supposing we have a binary tree with 5 nodes,

![image](https://user-images.githubusercontent.com/35857179/180000691-7634f6e6-1c2b-4e6e-a52a-83f3218e2d6b.png)

### Pre-order

- Visit the root
- Traverse the left sub-tree
- Traverse the right sub-tree

```cpp
void preorder(TreeNode* node) {
    if (node == NULL) return;
    s.push_back(node->val);
    preorder(node->left);
    preorder(node->right);
}
```

### In-order

- Traverse the left sub-tree
- Visit the root
- Traverse the right sub-tree

<Tabs>

<TabItem value="cpp" label="C++">

```cpp
void inorder(TreeNode* node) {
    if (node == NULL) return;
    inorder(node->left);
    s.push_back(node->val);
    inorder(node->right);
}
```
</TabItem>

<TabItem value="py" label="Python">

```py
def dfs(node):
    if(node == None):
        return
        
    dfs(node.left)
    
    print("I just visited the left branch!")
    print("I am number: " + str(node.val))
    print("I am visiting the right branch now!")
    
    dfs(node.right)
```
</TabItem>
</Tabs>

### Post-order

- Traverse the left sub-tree
- Traverse the right sub-tree
- Visit the root

```cpp
void postorder(TreeNode* node) {
    if (node == NULL) return;
    postorder(node->left);
    postorder(node->right);
    s.push_back(node->val);
}
```

### Summary

| Traversal  | Path               | Order               |
| ---------- | ------------------ | ------------------- |
| Pre-order  | 1 -> 2 -> 4 -> 5 -> 3 | Root -> Left -> Right |
| In-order   | 4 -> 2 -> 5 -> 1 -> 3 | Left -> Root -> Right |
| Post-order | 4 -> 5 -> 2 -> 3 -> 1 | Left -> Right -> Root  |
