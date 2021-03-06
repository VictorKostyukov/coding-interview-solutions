# Maximum Depth of Binary Tree

## Problem

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

## Example

Given a binary tree as follow:

```
      1
     / \
    2   3
       / \
      4   5
```

The maximum depth is `3`.

## Code(Java)

```java
/**
 * Definition of TreeNode:
 * public class TreeNode {
 *   public int val;
 *   public TreeNode left, right;
 *   public TreeNode(int val) {
 *     this.val = val;
 *     this.left = this.right = null;
 *   }
 * }
 */
public class Solution {
    /**
     * @param root: The root of binary tree.
     * @return: An integer.
     */
    public int maxDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }
        return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
    }
}
```
