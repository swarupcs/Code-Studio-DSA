# Preorder Binary Tree

### Problem statement
```
You are given a ‘Binary Tree’. 
Return the preorder traversal of the Binary Tree.

```
## Java Solution
### Approach 1 
```
public class Solution {

	public static void preOrder(BinaryTreeNode<Integer> root) {
		//Your code goes here
		if(root == null) {
			return;
		}

		System.out.print(root.data + " ");
		preOrder(root.left);
		preOrder(root.right);
	}

}
```

