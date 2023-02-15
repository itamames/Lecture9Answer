# Lecture 9 Answers

```java
// Recursive function to check if a given binary tree is height-balanced or not
    public static int isHeightBalanced(Node root, AtomicBoolean isBalanced)
    {
        // base case: tree is empty or not balanced
        if (root == null || !isBalanced.get()) {
            return 0;
        }
 
        // get the height of the left subtree
        int left_height = isHeightBalanced(root.left, isBalanced);
 
        // get the height of the right subtree
        int right_height = isHeightBalanced(root.right, isBalanced);
 
        // tree is unbalanced if the absolute difference between the height of
        // its left and right subtree is more than 1
        if (Math.abs(left_height - right_height) > 1) {
            isBalanced.set(false);
        }
 
        // return height of subtree rooted at the current node
        return Math.max(left_height, right_height) + 1;
    }

```
