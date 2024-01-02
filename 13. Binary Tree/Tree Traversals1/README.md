# Tree Traversals

### Problem statement
```
You have been given a Binary Tree of 'N' nodes, where the nodes have integer values.

Your task is to return the ln-Order, Pre-Order, and Post-Order traversals of the given binary tree.

```

## Java
```
/*********************************************************

 Following is the TreeNode structure:

 class TreeNode {
     int data;
     TreeNode left;
     TreeNode right;
     TreeNode() {
         this.data = 0;
         this.left = null;
         this.right = null;
     }
     TreeNode(int data) {
         this.data = data;
         this.left = null;
         this.right = null;
     }
     TreeNode(int data, TreeNode left, TreeNode right) {
         this.data = data;
         this.left = left;
         this.right = right;
     }
 };
 ********************************************************/

import java.util.List;

import java.util.ArrayList;
public class Solution {

    public static void InOrder(TreeNode root, List<Integer> result) {
        if(root == null) {
            return;
        }

        InOrder(root.left, result);
        result.add(root.data);
        InOrder(root.right, result);
    }

    public static void PreOrder(TreeNode root, List<Integer> result) {
        if(root == null) {
            return;
        }

        result.add(root.data);
        PreOrder(root.left, result);
        PreOrder(root.right, result);
    }

    public static void PostOrder(TreeNode root, List<Integer> result) {
        if(root == null) {
            return;
        }

        PostOrder(root.left, result);
        PostOrder(root.right, result);
        result.add(root.data);
    }
    public static List<List<Integer>> getTreeTraversal(TreeNode root) {
        // Write your code here.
        List<List<Integer>> ans = new ArrayList<>();
        List<Integer> inOrd = new ArrayList<>();
        List<Integer> preOrd = new ArrayList<>();
        List<Integer> postOrd = new ArrayList<>();

        InOrder(root, inOrd);
        PreOrder(root, preOrd);
        PostOrder(root, postOrd);

        ans.add(inOrd);
        ans.add(preOrd);
        ans.add(postOrd);

        return ans;
    }
}


/* 
1. Implement Recursive Inorder function
    a. instead of print root.data, we add in a result list
2. Implement Recursive Preorder function
    a. instead of print root.data, we add in a result list
3. Implement Recursive PostOrder function
    a. instead of print root.data, we add in a result list
4. Implement getTreeTraversal function
    a. create a ans list to store final 3 traversals
    b. create an inOrd list to store inorder traversal
    c. create a preOrd list to store preorder traversal
    d. create a postOrd list to store postorder traversal
    e. call InOrder(), PreOrder(), PostOrder()
    f. store values in ans list.
    g. return ans List



*/
```

