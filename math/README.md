[Back](../README.md)

# Math questions

## Sorting algorytms

| ALGORYTHM | IDEA | COMPLEXITY | ADVANTAGE / DRAWBACK |
| :-------- | :--- | :--------: | :------------------- |
| Mergesort | The sorting algorithm produces a sorted sequence by sorting its two halves and merging them. | O(n log(n)) | It needs an additional space of Θ(n) for the temporary array b. |
| Shellsort | Arrange the data sequence in a two-dimensional array and sort the columns of the array. | O(n·log(n))2 | |
| Heapsort  | The data structure of the heapsort algorithm is a heap. | O(n·log(n)) | Heapsort is not stable. A sorting algorithm is stable, if it leaves the order of equal elements unchanged.|
| Insertion | At the beginning and after each iteration of the algorithm the sequence consists of two parts: the first part a0, ..., ai-1 is already sorted, the second part ai, ..., an-1 is still unsorted | Θ(n2) | |
| Quicksort | The first step of the partition procedure is choosing a comparison element x. All elements of the sequence that are less than x are placed in the first part, all elements greater than x are placed in the second part. | Θ(n log(n)) in the average case and in Θ(n2) in the worst case | |

## Graph traversing

*Depth-first search (DFS)* is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

### Depth First Traversals:

#### Inorder (Left, Root, Right)

 * Traverse the left subtree, i.e., call Inorder(left-subtree)
 * Visit the root.
 * Traverse the right subtree, i.e., call Inorder(right-subtree)
 
#### Preorder (Root, Left, Right)

 * Visit the root.
 * Traverse the left subtree, i.e., call Preorder(left-subtree)
 * Traverse the right subtree, i.e., call Preorder(right-subtree) 
 
#### Postorder (Left, Right, Root)

 * Traverse the left subtree, i.e., call Postorder(left-subtree)
 * Traverse the right subtree, i.e., call Postorder(right-subtree)
 * Visit the root.
 
### Breadth First or Level Order Traversal

 * Level by level (horisontally)
