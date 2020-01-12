# Binary Tree Preorder Traversal 🌲
## https://leetcode.com/problems/binary-tree-preorder-traversal

Given a binary tree, return the preorder traversal of its nodes' values.
```
Example:

Input: [1,null,2,3]
   1
    \
     2
    /
   3

Output: [1,2,3]
```
**Follow up: Recursive solution is trivial, could you do it iteratively?**

# Preorder Traversal :
![Binary Tree](binary-tree.PNG?raw=true "Binary Tree")

Note that node 75 doesn't have left child and node 29 doesn't have right child.

The preorder traversal for above binary tree will be **[70, 67, 35, 21, 20, 75, 30, 43, 29, 50, 24, 60, 65]**


## Implementation :

```java
import java.util.ArrayList;
import java.util.List;

public class App {

	public static void main(String[] args) {
		TreeNode root = new TreeNode(70);
		root.left = new TreeNode(67); root.right = new TreeNode(43);
		
		root.left.left = new TreeNode(35); root.left.right = new TreeNode(75); 
		
		root.left.left.left = new TreeNode(21); root.left.left.right = new TreeNode(20);
		
		root.left.right.right = new TreeNode(30);
		
		root.right.left = new TreeNode(29); root.right.left.left = new TreeNode(50);
		
		root.right.right = new TreeNode(24); 
		
		root.right.right.left = new TreeNode(60); root.right.right.right = new TreeNode(65);
		System.out.println(inorderTraversal(root));
	}
	
	
	// Definition for a binary tree node.
	static public class TreeNode {
	      int val;
	      TreeNode left;
	      TreeNode right;
	      TreeNode(int x) { val = x; }
	}
	 
	
	public static List <Integer> inorderTraversal(TreeNode root) {
        List <Integer> res = new ArrayList<Integer>();
        helper(root, res);
        return res;
    }

  public static void helper(TreeNode root, List <Integer> res) {
        if (root != null) {
        	res.add(root.val);
            if (root.left != null) {
                helper(root.left, res);
            }
            
            if (root.right != null) {
                helper(root.right, res);
            }
        }
   }
}

```
