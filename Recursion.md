# Recursion

## Pattern

* Base case
* Recursive invocation

## Recursion and computations

* Fibonacci
* Power

## Recursion and 1-d array, 2-d array

* 1-d array
  * merge sort
  * quick sort
* 2-d array
  * N-queens
  * print spiral 2-d array

## Recursion and linked list

* reverse linked list
* reverse linked list by pairs

## Recursion and string

* reverse a string
  * swap two characters
    * iterative, two pointers
    * recursive, swap head and tail, then recursively apply to substring
* word abbreviation

## Recursion and tree

* Idea
  * What do you expect from left child and right child
  * What do you want to do in current layer
  * What to report to the parent

* Examples
  * Get height
    * expect from left and right: Max(leftHeight, rightHeight)
    * current layer: none
    * report: max + 1
  * Store descendants of current node to its left subtree
    * expect from left and right: subtotal from children respectively
    * current layer: current->Left = sum
    * report: leftTotal + rightTotal + 1
  * Maximum difference between sibling nodes
    * expect from left and right: max difference of left and right, respectively
    * current layer: select the bigger one
    * report: current + 1
