# Node Depth

This repository contains a function nodeDepths that calculates the sum of the depths of all nodes in a binary tree. It is implemented in JavaScript and uses a recursive approach to traverse the tree and accumulate the depth of each node.

Problem Description: Given a binary tree, the depth of a node is defined as the distance between the node and the tree's root. The root node has a depth of 0, its children have a depth of 1, and so on.

The task is to calculate the sum of all node depths in a binary tree. For example:


          1
         / \
        2   3
       / \
      4   5
      
For the above binary tree, the node depths are:

	Depth of node 1 = 0
	Depth of node 2 = 1
	Depth of node 3 = 1
	Depth of node 4 = 2
	Depth of node 5 = 2
	The total sum of node depths = 0 + 1 + 1 + 2 + 2 = 6.

Solution: The nodeDepths function uses a recursive approach to calculate the sum of depths of all nodes. At each recursive step, it adds the current node's depth to the sum of depths of its left and right subtrees.

Code Explanation

	function nodeDepths(root, depth = 0) {
	  if (root === null) return 0;
	  return depth + nodeDepths(root.left, depth + 1) + nodeDepths(root.right, depth + 1);
	}
Base Case: If the current node is null, return 0 (no depth to accumulate).

Recursive Case: At each node, add its current depth to the sum of depths of its left and right children. Recursively call nodeDepths for the left and right subtrees, incrementing the depth by 1 for each level.

Binary Tree Class

	class BinaryTree {
	  constructor(value) {
	    this.value = value;
	    this.left = null;
	    this.right = null;
	  }
	}
 
The BinaryTree class represents a simple binary tree node structure, with value, left, and right properties.


Example

	const root = new BinaryTree(1);
	root.left = new BinaryTree(2);
	root.right = new BinaryTree(3);
	root.left.left = new BinaryTree(4);
	root.left.right = new BinaryTree(5);

	console.log(nodeDepths(root)); // Output: 6
 
Time and Space Complexity:

Time Complexity: O(n), where n is the number of nodes in the tree. Each node is visited once.

Space Complexity: O(h), where h is the height of the tree due to the recursive call stack. In the worst case (a completely unbalanced tree), this could be O(n), but for a balanced tree, it is O(log n).

License: This project is open-source and available under the MIT License.
