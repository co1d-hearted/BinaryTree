# BinaryTree


## Intro

A tree is a popular data structure that is non-linear in nature. Unlike other data structures like array, stack, queue, and linked list which are linear in nature, a tree represents a hierarchical structure. The ordering information of a tree is not important. A tree contains nodes and 2 pointers. These two pointers are the left child and the right child of the parent node. 
  - Root: The root of a tree is the topmost node of the tree that has no parent node. There is only one root node in every tree. 
  - Edge: Edge acts as a link between the parent node and the child node.
  - Leaf: A node that has no child is known as the leaf node. It is the last node of the tree. There can be multiple leaf nodes in a tree.
  - Subtree: The subtree of a node is the tree considering that particular node as the root node.
  - Depth: The depth of the node is the distance from the root node to that particular node.
  - Height: The height of the node is the distance from that node to the deepest node of that subtree.
  - Height of tree: The Height of the tree is the maximum height of any node. This is same as the height of root node.

Why would a programmer want to uses trees. Well, here are a few reasons:
  - One reason to use trees might be because you want to store information that naturally forms a hierarchy. 
  - Trees (with some ordering e.g., BST) provide moderate access/search (quicker than Linked List and slower than arrays). 
  - Trees provide moderate insertion/deletion (quicker than Arrays and slower than Unordered Linked Lists). 
  - Like Linked Lists and unlike Arrays, Trees don’t have an upper limit on the number of nodes as nodes are linked using pointers.

## How do Binary Trees Work

![Binary Tree](Binary-Tree-in-Data-Structure-1.png.png)

In above show the binary tree; see here above tree contains at most two child nodes as shown in the above figure. Some important terms are used in binary trees as follows.

### Path: 
Path is used to represent the sequence of nodes either the left side or right side.
### Root: 
The topmost node of the tree we call a root node and each tree has only one root node for example A is a root node.
### Parent: 
We can consider any node as a parent node except the root node for example B as a parent node.
### Child: 
Below parent node tree contains the child node for example D and E is a child node of B.
### Leaf: 
In a binary tree the node does not have any child node that node we called a leaf node for example D.
### Subtree: 
Binary we contain the subtree for example in the above binary we show the subtree by using the square.
### Keys: 
It is used to represent the value of a node and that is used to perform the search and insert operation.

### Now let’s see the basic operation of the Binary tree as follows.

### Insert Operation:

It is very similar to the search function. You again start at the root of the tree and go down recursively, searching for the right place to insert our new node, in the same way as explained in the search function. If a node with the same value is already in the tree, you can choose to either insert the duplicate or not. Some trees allow duplicates, some don't. It depends on the certain implementation.

### Search Operation:

When we need to search an element in the binary tree, we start the searching from the root node and then compare the item value or element value with key values. If the search value is less than the key value, then we perform the search on the left side and if the search value is greater than key value then we perform a search at the right side.

### Deletion:

There are 3 cases that can happen when you are trying to delete a node. If it has,

  - No subtree (no children): This one is the easiest one. You can simply just delete the node, without any additional actions required.
  - One subtree (one child): You have to make sure that after the node is deleted, its child is then connected to the deleted node's parent.
  - Two subtrees (two children): You have to find and replace the node you want to delete with its inorder successor (the leftmost node in the right  subtree).

The time complexity for creating a tree is  O(1) . The time complexity for searching, inserting or deleting a node depends on the height of the tree  h , so the worst case is  O(h)  in case of skewed trees.

### Preorder Traversal:

We traverse the node in a pre-order manner as per requirement.

### Inorder Traversal:

We traverse the node in an in-order manner as per requirement.

### Postorder Traversal:

We traverse the node in a post-order manner as per requirement.
