# Algorithm

Questions from LeetCode.


## Binary Tree

### 104. Maximum Depth of Binary Tree

Given the root of a binary tree, return its maximum depth. A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

  1. BFS
  
    ```
    var maxDepth = function(root) {
    
    if (root == null) return 0;
    const queue = [root];
    let depth = 1;
    
    while (queue.length) {
    
      const levelSize = queue.length;
    
      for (let i = 0; i< levelSize; i++) {
    
        const current = queue.shift();
    
        if (current.left) queue.push (current.left);
        if (current.right) queue.push (current.right);
    
        }
    
      if (queue.length) {depth++}
    }
    
    return depth;
    
    }
    ```

  2. Recursion
     ```
     var maxDepth = function(root) {

     if (root == null) return 0;

     const maxLeftDepth = maxDepth(root.left);
     const maxRightDepth = maxDepth(root.right);

     return 1 + Math.max(maxLeftDepth, maxRightDepth)

     }
     ```

## Double Pointers

### 167. Two Sum II - Input Array Is Sorted

  * Sorted array, only need to iterate one round
  * Two pointers, one starts from the first number and one startsfrom the ending number; Iterate and each time compare the sum of the pointers' values and target, move the pointers based on the result.

  ```
  var twoSum = function(numbers, target) {
      const total = numbers.length;
      let start = 0;
      let end = total - 1;
  
      for (let i = 0; i<total; i++) {
          if (numbers[start]+numbers[end] < target) {
              start++;
          } else if (numbers[start]+numbers[end] > target) {
              end--;
          } else {return [start+1, end+1]}
      }
  ```


   
