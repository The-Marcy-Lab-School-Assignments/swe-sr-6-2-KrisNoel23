# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson, make sure to include the following:

* A formal definition of recursion (feel free to quote an official source like MDN)
* An example in code.
* An explanation of the code example.
* An explanation of the kinds of functions that are best solved using recursion.

### Response 1

According to MDN Docs, "Recursion is a process in which a function calls itself as a subroutine. This allows the function to be repeated several times, as it can call itself during its execution."


Here's an example of recursion:


```
const sum = (arr) => {
   if (arr.length === 0) { // Base case: if the array is empty, return 0
       return 0;
   }
   return arr[0] + sum(arr.slice(1)); // Take the first number and add it to the sum of the rest
};
```
The function ```sum(arr)``` calculates the sum of all numbers in an array using recursion.


The functions best solved using recursion are problems that can be broken down into smaller subproblems of the same type, such as mathematical problems and trees.


## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of a Tree (feel free to quote an official source like MDN)
* Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
* An example in code.
* An explanation of the code example.

### Response 2



According to MDN Docs, "A tree is a data structure composed of nodes. Each tree has a root node that serves as the starting point, and each node may have child nodes that branch out, forming a hierarchy."


The root is the topmost node in a tree.


A leaf node has no children.


The depth of a node is based on the number of edges from the root to that node.


The height of a node  is based on the longest path from the root to a leaf.


Here's an example in code:
```
constructor(value, left = null, right = null) {
   this.root = value;
   this.left = left;
   this.right = right;
 }


 getRootValue() {
   return this.root;
 }


 setRootValue(value) {
   this.root = value;
 }


 insertLeft(value) {
   this.left = new BinaryTree(value);
   return this.left;
 }


 insertRight(value) {
   this.right = new BinaryTree(value);
   return this.right;
 }


 getLeftChildValue() {
   return this.left.root;
 }


 getRightChildValue() {
   return this.right.root;


 };


```


## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

### Response 3

One example of an iterative function adds any given number to the variable total.


//Written as an iterative function:
function addToTotal(total, num) {
    for (let i = 0; i < num; i++) {
        total += 1;
    }
    return n
}

You can tell this is iterative because it uses a for loop to add the given number num to the total continuously.

//Rewritten recursively:
function addToTotalR(totalR, num) {
    if (num === 0) {
        return totalR
    } else {
        return addToTotalR(totalR + 1, num - 1)
    }
}

You can tell this is recursive because the function is calling on itself (until num equals 0).

Overall using a recursive method adds to readability and problem breakdown. A huge downside is if too many recursive calls are made and a memory limit is reached. This will cause the call stack to ‘overflow’ and crash with an error.

## Prompt 4

Depth-first-search is an algorithm of traversing through a tree that explores as far as possible along a single branch before backtracking and exploring other branches. The three approaches for depth-first-search are "inorder", "preorder", and "postorder". 

Using this tree as an example, explain the differences between these three approaches, providing implementations of each (recursive or iterative, its up to you but one of them is definitely cleaner).

```
    A
   / \
  B   C
 / \   \
D   E   F
```

### Response 4

(Assuming you’ve set the tree node as a class up, set the root at A then continue setting the rest of the letters using .left and .right)

In order recursive will go down the left subtree to the root, then to the right subtree.
D > B > E > A > C > F
function inorder(root) {
    inorderTraversal(root.left)
    console.log(root.value)
    inorderTraversal(root.right)
}

Preorder recursive will visit the root, then travel the left then right subtrees.
A > B > D > E > C > F
function preorderTraversal(root) {

    console.log(root.value)
    preorderTraversal(root.left)
    preorderTraversal(root.right)
}

Post order recursive will travel the left then right subtrees then travel to the root.
D > E > B > F > C > A
function postorderTraversal(root) {

    postorderTraversal(root.left)
    postorderTraversal(root.right)
    console.log(root.value)
}



