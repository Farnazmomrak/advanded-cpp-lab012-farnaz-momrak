# Binary Search Tree Analysis Laboratory

## Core goal
Students must implement a binary search tree storing integer values and supporting insertion, search, removal, height, traversal, and balancing checks.

## Required operations
Students must implement and analyze:

- `insert(value)`
- `remove(value)`
- `contains(value)`
- `search(value)`
- `min()` and `max()`
- `height()`
- `isBalanced()`
- `clear()`
- traversal methods: inorder, preorder, postorder, and level-order

## Analysis expectations
Students should explain:

- average-case and worst-case complexity of insertion, search, and deletion;
- how tree shape affects cost;
- why balanced trees improve performance;
- traversal behavior and the ordering guarantees of different traversals;
- what happens when the tree becomes skewed.

## Big-O focus
Students should describe Big-O for:

- insert
- search
- remove
- min/max traversal
- height
- inorder/preorder/postorder
- level-order traversal

A rigorous answer should include both average and worst-case behavior.

## Analysis
A BST desing is when the root has two child (one left and one right), and smaller values go to the left and larger values go to the right. insert puts a new value in the correct position and rejects duplicates. contains and search follow the left or right path until the value is found or a null pointer is reached. remove handles three cases: a node with no left child, a node with no right child, and a node with two children. In the two-child case, the node takes the value of its inorder successor (the smallest value in its right subtree), and then that successor is removed. min() and max() follow the left-most and right-most path, height() measures the longest path from the root, isBalanced() checks that the left and right heights differ by at most 1 at every node, and clear() deletes all nodes.

Tree shape and cost: insert, search, contains, and remove all follow one path from the root down, so their cost depends on the height of the tree. In a balanced tree the height is about log n, so these take O(log n) on average. If the values are inserted in sorted order, the tree becomes skewed and looks like a linked list. The height is then n, and the worst case is O(n). Balanced trees are faster because each step cuts the remaining search space roughly in half. min() and max() are O(log n) on a balanced tree and O(n) on a skewed tree, since they follow one side of the tree. height() is O(n), because it visits every node. isBalanced() is O(n²) in the worst case in my code, because it recalculates the height at every node. clear() is O(n).

Traversals: All four traversals visit every node once, so each is O(n).
Inorder  gives the values in sorted order.
Preorder visits the parent before its children.
Postorder visits the children before the parent.
Level-order visits the tree level by level using a queue.
