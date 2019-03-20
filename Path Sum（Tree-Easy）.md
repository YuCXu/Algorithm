# Path Sum（Tree-Easy）

Given a binary tree and a sum, determine if the tree has a root-to-leaf path such that adding up all the values along the path equals the given sum.

For example:

Given the below binary tree and `sum = 22`

```
              5
             / \
            4  8
           /  / \
          11  13 4
         /  \     \
        7    2     1
```

return true, as there exist a root-to-leaf path `5->4->11->2` which sum is 22. 

```java
public class Solution{
    public boolean mark = false;
    public boolean hasPathSum(TreeNode root,int sum){
        if(root == null){
            return false;
        }
        Stack<Integer> path = new Stack<Integer>();
        int currentSum = 0;
        findPath(root,sum,path,currentSum);
        return mark;
    }
    public void findPath(TreeNode root,int sum,Stack<Integer> path,int currentSum){
        currentSum += root.val;
        path.push(root.val);
        boolean isLeaf = root.left==null && root.right == null;
        if(currentSum == sum && isLeaf){
            mark = true;
        }
        if(root.left != null){
            findPath(root.left,sum,path,currentSum);
        }
        if(root.right != null){
            findPath(root.right,sum,path,currentSum);
        }
        path.pop();
    }
}
```

