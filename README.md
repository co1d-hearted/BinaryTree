# BinaryTrees


## Intro

A Binary Tree is a popular data structure that is non-linear in nature. Unlike other data structures like array, stack, queue, and linked list which are linear in nature, a tree represents a hierarchical structure. The ordering information of a tree is not important. A tree contains nodes and 2 pointers. These two pointers are the left child and the right child of the parent node. 
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

Whenever an element is to be inserted, first locate its proper location. Start searching from the root node, then if the data is less than the key value, search for the empty location in the left subtree and insert the data. Otherwise, search for the empty location in the right subtree and insert the data.

    void insert(int data){
   	struct node *tempNode = (struct node*) malloc(sizeof(struct node));
   	struct node *current;
   	struct node *parent;

   	tempNode->data = data;
   	tempNode->leftChild = NULL;
   	tempNode->rightChild = NULL;

   	//if tree is empty
   	if(root == NULL) {
      root = tempNode;} 
      else {
      current = root;
      parent = NULL;

      while(1) {                
         parent = current;
			
         //go to left of the tree
         if(data < parent->data) {
            current = current->leftChild;                
            //insert to the left
				
            if(current == NULL) {
               parent->leftChild = tempNode;
               return;
            }
         }//go to right of the tree
         else {
            current = current->rightChild;
            
            //insert to the right
            if(current == NULL) {
               parent->rightChild = tempNode;
               return;
        }
        }
      	}            
   	}
	}        


### Search Operation:

When we need to search an element in the binary tree, we start the searching from the root node and then compare the item value or element value with key values. If the search value is less than the key value, then we perform the search on the left side and if the search value is greater than key value then we perform a search at the right side.

### Deletion:

There are 3 cases that can happen when you are trying to delete a node. If it has,

  - No subtree (no children): This one is the easiest one. You can simply just delete the node, without any additional actions required.
  - One subtree (one child): You have to make sure that after the node is deleted, its child is then connected to the deleted node's parent.
  - Two subtrees (two children): You have to find and replace the node you want to delete with its inorder successor (the leftmost node in the right  subtree).

The time complexity for creating a tree is  O(1) . The time complexity for searching, inserting or deleting a node depends on the height of the tree  h , so the worst case is  O(h)  in case of skewed trees.

	void deleteNode(struct node* root, int data){

    	if (root == NULL) root=tempnode; 

    	if (data < root->key) 
        root->left = deleteNode(root->left, key); 
  

    	else if (key > root->key) 
        	root->right = deleteNode(root->right, key); 

    	else
    	{ 
        	if (root->left == NULL) 
        	{ 
            	struct node *temp = root->right; 
            	free(root); 
            	return temp; 
        	} 
        	else if (root->right == NULL) 
        	{ 
            	struct node *temp = root->left; 
            	free(root); 
            	return temp; 
        	} 
  
        	struct node* temp = minValueNode(root->right); 
 
        	root->key = temp->key; 

        	root->right = deleteNode(root->right, temp->key); 
    	} 
    	return root; 

	}

### Preorder Traversal:

This traversal first accesses the current node value, then traverses the left and right sub-trees respectively.

	void preOrder(struct node* root) {
        if (root == null) {
                return;
        }
        // Print the current node value
        printf("%d ", root.data);
        // Travel the left sub-tree first.
        preOrder(root.left);
        // Travel the right sub-tree next.
        preOrder(root.right);
	}

### Inorder Traversal:

This traversal first goes over the left subtree of the root node, then accesses the current node, followed by the right subtree of the current node. The code represents the base case too, which says that an empty tree is also a binary search tree.

	void inOrder(struct node* root) {
        // Base case
        if (root == null) {
                return;
        }
        // Travel the left sub-tree first.
        inOrder(root.left);
        // Print the current node value
        printf("%d ", root.data);
        // Travel the right sub-tree next.
        inOrder(root.right);
	}

### Postorder Traversal:

This traversal puts the root value at last, and goes over the left and right sub-trees first. The relative order of the left and right sub-trees remain the same. Only the position of the root changes in all the above mentioned traversals.

	void postOrder(struct node* root) {
        if (root == null) {
                return;
        }
        // Travel the left sub-tree first.
        postOrder(root.left);
        // Travel the right sub-tree next.
        postOrder(root.right);
        // Print the current node value
        printf("%d ", root.data);
	}

## How are BSTs useful

Binary trees are mainly used for searching and sorting as they provide a means to store data hierarchically. Some common operations that can be conducted on binary trees include insertion, deletion, and traversal. The main advantage of using binary trees is simplicity. Binary trees possess a simple-to-understand structure for data management and organization. Additionally, some benefits of binary trees are:
	
	- They can be used to reflect relationships between data.
	- They can store an arbitrary number of data values.

