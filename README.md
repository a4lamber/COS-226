# LeetCode Grind Journey

> Need a systematic way to grind LC so i have more time to work on other interesting stuff.


*Table of contents*
- [LeetCode Grind Journey](#leetcode-grind-journey)
- [Tree](#tree)
  - [Depth-first Traversal](#depth-first-traversal)
  - [Level-first Traversal](#level-first-traversal)
  - [Others](#others)
  - [Binary Search Tree Problems](#binary-search-tree-problems)
  - [Path Problems](#path-problems)
  - [Construct BT \& BST](#construct-bt--bst)
  - [Tree Summary and Reference](#tree-summary-and-reference)
- [Linked List](#linked-list)
    - [Cycle detection](#cycle-detection)
    - [Cache Series](#cache-series)
  - [Linked List reference](#linked-list-reference)
- [Reference](#reference)



# Tree

Tree problems on LC are categorized into two fold
- depth first approach
- breadth first approach

## Depth-first Traversal

Tree depth-first traversal is summarized as:
- recursive solution is the easiest
- iteration solution relies on auxillary data structure `stack` to store the nodes in a order that corresponds to the visiting order


 - [x] [94 Binary Tree Inorder traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)
	- [ ] recursion
	- [x] [iteration with stack](https://github.com/a4lamber/Leetcode/blob/d006a304d8d861819ee1e5f1a02eb30988e51d89/LeetCode/94-binary-tree-inorder-traversal)
	- [ ] morris
- [x] [144 Binary Tree Preorder traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)
	- [ ] recursion
	- [x] [iteration with stack](https://github.com/a4lamber/Leetcode/blob/d04c98fa7e2d0f752301b4bee262be8799d2e996/LeetCode/144-binary-tree-preorder-traversal)
	- [ ] morris
- [x] [145 Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/)
	- [ ] recursion
	- [x] iterative solution
		- [approach1: reverse modified pre-order](LeetCode/145-binary-tree-postorder-traversal/145-iteration-flip-modified-pre-order.py): post-order traversal (left, right, root) if we reverse it, it's (root, right, left). This becomes "modified" pre-order. Merge the solution to the some knowledge we already know. 
	- [ ] morris

## Level-first Traversal

level-first traversal typically,
- uses `queue` as auxillary data structure to temporarily store nodes in the current level

- [x] [102 Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
  - BFS, something you should mark in your head. [solution here](LeetCode/102-binary-tree-level-order-traversal/102-queue.py)
- [x] [103 Binary Tree Zigzag Level Order Traversal](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)
	- trick在于有一种方法计算在目前在哪一层，for a perfect tree, 1 --> 2 --> 4, 可以每一次append完children之后，求一下总数, [solution](LeetCode/103-binary-tree-zigzag-level-order-traversal/103-queue.py) is here
- [x] [107 Binary Tree Level Order Traversal II](https://leetcode.com/problems/binary-tree-level-order-traversal-ii/)
  - Using regular DFS, but we use deque for output `res = deque()`. We `appendleft` at the end of each layer. [Solution](./LeetCode/107-binary-tree-level-order-traversal-II/107_double_queue.py) and [note](./LeetCode/107-binary-tree-level-order-traversal-II/README.md) are here.


## Others
---
- [x]  [100 Same Tree](https://leetcode.com/problems/same-tree/)
	- [x] recursion
	- [x] [BFS with queue](./LeetCode/100-same-tree/README.md)
- [x]  [101 Symmetric Tree](https://leetcode.com/problems/symmetric-tree/)
	- [x] [BFS solution](./LeetCode/101-symmetric-tree/README.md), symmetric tree is very similar with same tree. Just remember comparing medial sides then lateral side.
- [x]  [104 Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
	- [x] [BFS solution. It's easier with BFS. Just set a counter](./LeetCode/104-maximum-depth-of-binary-tree/104-BFS.py)
	- [ ] recursion
	- [ ] DFS to really work with ur brain on tracking depth. 
- [ ]  [110 Balanced Binary Tree](https://leetcode.com/problems/balanced-binary-tree/)
  - [ ] bottom-up
  - [ ] top-down  
- [x]  [111 Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/)
  - First thought: BFS with auxillary DS (stack) to track all leaf node's height. [Solution](./LeetCode/111-minimum-depth-of-binary-tree/111-BFS.py).
  - optimized: If we use BFS, the first encounter of leaf node will have the minimum depth, [solution here](./LeetCode/111-minimum-depth-of-binary-tree/111-BFS-optimized.py).
- [x]  [617 Merge Two Binary Trees](https://leetcode.com/problems/merge-two-binary-trees)
  - BFS on left tree. Left tree absorb right tree. The control flow is kinda tricky. [Solution here](./LeetCode/617-merge-two-binary-trees/README.md).  
- [ ]  [543 Diameter of Binary Tree](https://leetcode.com/problems/diameter-of-binary-tree/)
- [ ]  [563 Binary Tree Tilt](https://leetcode.com/problems/binary-tree-tilt)
- [x]  [226 Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)
  - [BFS but insert right node first at each level](./LeetCode/226-invert-binary-tree/README.md)


## Binary Search Tree Problems
---
- [x] [700 Search in a Binary Search Tree](https://leetcode.com/problems/search-in-a-binary-search-tree)
  - very basic BST, [solution](./LeetCode/700-search-in-a-binary-search-tree/700.py)
- [x] [653 Two Sum IV - Input is a BST](https://leetcode.com/problems/two-sum-iv-input-is-a-bst/)
  - two sum variation. Instead of array + hash --> tree + hash; instead of iteration to traverse array, we do inorder traversal (or others). [Solution here](./LeetCode/653-two-sum-IV-input-is-a-BST/653-two-sum-BST.py) 
- [x] [530 Minimum Absolute Difference in BST](https://leetcode.com/problems/minimum-absolute-difference-in-bst/)
  - trick is to use the property of BST. in-order depth first DFS on BST will output sorted list. [Solution here](./LeetCode/530-minimum-absolute-difference-in-BST/530-DFS-inorder.py)
- [x] [938 Range Sum of BST](https://leetcode.com/problems/range-sum-of-bst/)
  - DFS to a list, then traverse. [solution here](./LeetCode/938-range-sum-of-BST/938.py). 
- [ ] [450 Delete Node in a BST](https://leetcode.com/problems/delete-node-in-a-bst/)
- [ ] [669 Trim a Binary Search Tree](https://leetcode.com/problems/trim-a-binary-search-tree)
- [ ] [701 Insert into a Binary Search Tree](https://leetcode.com/problems/insert-into-a-binary-search-tree)
- [x] [230 Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst)
  - in order traversal, [solution here](./LeetCode/230-kth-smallest-element-in-BST/230-in-order-DFS.py)
- [ ] [1305 All Elements in Two Binary Search Trees](https://leetcode.com/problems/all-elements-in-two-binary-search-trees)
  - $O\left((m+n)log(m+n)\right)$ in time and $O(m+n)$ in space by in-order traversal twice then merge with quick sort, kinda dumb but solution is [here](./LeetCode/1305-all-elements-in-two-binary-search-trees/1305-dumb-solution.py)
  - [ ] this question must be solved with optimal solution. Go back to this when i have more time.

## Path Problems
---
- [x] [257 Binary Tree Paths](https://leetcode.com/problems/binary-tree-paths/)
  - [DFS, iterative solution with a stack of tuple](./LeetCode/257-binary-tree-paths/257-iterative.py). Also avoid overclustering heap with intermediate string causes by `+`, use `join()` instead, reason [here](./LeetCode/257-binary-tree-paths/README.md).
- [x] [112 Path Sum](https://leetcode.com/problems/path-sum)
  - DFS solution with a stack of tuple, the tuple carries (node, currSum), node is for traversing and providing value for this iteration, currSum carries the state variable of path sum until this current node. [Solution here](./LeetCode/112-path-sum/112-DFS.py).
  - [ ] Alternatively, you could use BFS to solve. Put a placeholder here.
- [x] [113 Path Sum II](https://leetcode.com/problems/path-sum-ii)
  - [DFS solution here](./LeetCode/113-path-sum-II/113_DFS.py), a tuple again but tracking three state 
- [x] [129 Sum root to leaf numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers/)
  - [DFS solution](./LeetCode/129-sum-root-to-leaf-numbers/129-DFS.py). Tuple contains current state info about node and a string representation of root-to-leaf path. 
- [ ] [124 Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/)
  - placeholder. 
- [ ] [437 Path Sum III](https://leetcode.com/problems/path-sum-iii) 
- [ ] [1457 Pseudo-Palindromic Paths in a Binary Tree](https://leetcode.com/problems/pseudo-palindromic-paths-in-a-binary-tree)
  - not palindromic again! 

## Construct BT & BST
- [ ] [105 Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal)
- [ ] [106 Construct Binary Tree from Inorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal)
- [ ] [889 Construct Binary Tree from Preorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal)
- [ ] [108 Convert Sorted Array to Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree)
- [ ] [1008 Construct Binary Search Tree from Preorder Traversal](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal)


## Tree Summary and Reference

> Note: Tree can be implemented by list of lists or nodes and reference.

Some good reference here to consolidate your understanding:
- [CSDN post: BST, AVL, 红黑树和伸展树](https://holmofy.blog.csdn.net/article/details/79692613?spm=1001.2014.3001.5502)
- [知乎: BST, 链表和数组的折中](https://www.zhihu.com/question/37381035)
- [知乎: BST入门](https://zhuanlan.zhihu.com/p/136758152)


# Linked List

Well, it's time to systematically do linked list!

![](https://www.section.io/engineering-education/linked-list-data-structure-python/thanosll.jpg)


- [x] [2 Add Two Numbers](https://leetcode.com/problems/add-two-numbers/?envType=list&envId=oqasfzsm)
  - the use of floor division for carry and tenary operation to make the code neater. Recommend neetcode for this question. [Solution here](./LeetCode/2-add-two-numbers/2-traverse-reverse.py)
- [ ] [19 Remove Nth Node From Rnd of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/?envType=list&envId=oqasfzsm)
- [ ] [21 Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/?envType=list&envId=oqasfzsm)
- [ ] [23 Merge k Sortd Lists](https://leetcode.com/problems/merge-k-sorted-lists/?envType=list&envId=oqasfzsm)
- [ ] [24 Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/?envType=list&envId=oqasfzsm)
- [ ] [25 Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/?envType=list&envId=oqasfzsm)
- [ ] [83 Remove Duplicates from sorted list](https://leetcode.com/problems/remove-duplicates-from-sorted-list/?envType=list&envId=oqasfzsm)
- [x] [92 Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/editorial/) 
  - Neetcode讲的很好，三部曲, [video here](https://www.youtube.com/watch?v=RF_M9tX4Eag&ab_channel=NeetCode) and [my explanation here](./LeetCode/92-reverse-linked-list-II/README.md).
    - advance till left node, `left - 1`
    - reverse `right - left + 1` 
    - reorganize which node points to which
- [ ] [138 Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/?envType=list&envId=oqasfzsm)
- [ ] 143
- [ ] [147 Insertion Sort List](https://leetcode.com/problems/insertion-sort-list/?envType=list&envId=oqasfzsm)
- [ ] [148 Sort List](https://leetcode.com/problems/sort-list/?envType=list&envId=oqasfzsm)
- [ ] [160 Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/?envType=list&envId=oqasfzsm)
- [x] [206 Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/?envType=list&envId=oqasfzsm)
  - joma meme, reverse linked list 必须会的. 
- [ ] [234 Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [237 Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [328 Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [725 Split Linked List in Parts](https://leetcode.com/problems/split-linked-list-in-parts/?envType=list&envId=oqasfzsm)
- [ ] [707 Design Linked List](https://leetcode.com/problems/design-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [876 Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [1171 Remove Zero Sum Consecutive Nodes from Linked List](https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [1721 Swapping Nodes in a Linked List](https://leetcode.com/problems/swapping-nodes-in-a-linked-list/?envType=list&envId=oqasfzsm)
- [ ] [1832 Find the Winner of the Circular Game](https://leetcode.com/problems/find-the-winner-of-the-circular-game/?envType=list&envId=oqasfzsm)
### Cycle detection
Cycle detection by flord's turtle and hare实际上是two pointer, same direction with different speed, 可以归纳为two pointer类型.

- [x] [141 Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/?envType=list&envId=oqasfzsm)
  - floyd's turtle and hare, classic question, [solution here](./LeetCode/141-linked-list-cycle/141-linked-list-cycle.py). 
- [ ] Follow-up Can you find the length of the cycle if it exists? 
- [x] [142 Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
  - [Youtuber Nikhil Lohia](https://www.youtube.com/watch?v=95ZfuoSAUPI&ab_channel=NikhilLohia)的思路最清楚, 这题最优解用兔八哥，王八和龙来解，[solution here](./LeetCode/142-linked-list-cycle-II/README.md), 空间非最优解可以放一个hashset来做.
- [ ] [202 Happy Number](https://leetcode.com/problems/happy-number/)

### Cache Series
Linked list在很多数据结构中，起部分作用，比如database b+ tree中的leaf nodes, 之间都用doubly linked list连接。

这一个系列LC题目是linked list在cache中的运用，难度不低，且比较冗长, 建议以理解为主，熟练度靠频率刷上去.
- [ ] [146 LRU Cache](https://leetcode.com/problems/lru-cache/?envType=list&envId=oqasfzsm)
- [ ] [460 LFU Cache](https://leetcode.com/problems/lfu-cache/?envType=list&envId=oqasfzsm)

## Linked List reference
The list generated here is from Neetcode Linkedlist playlist and a linkedlist post.

- [3 hour linked list with java bootcamp from Kunal Kushwaha](https://www.youtube.com/watch?v=70tx7KcMROc&ab_channel=KunalKushwaha)



# Reference
- [Runestone Python Data Structure](https://runestone.academy/ns/books/published/pythonds/index.html)
  - very detailed with follow along examples.
- https://blog.csdn.net/Holmofy/article/details/76401074
- [dictionary of algorithms and data structure](https://xlinux.nist.gov/dads/) 
  - This site has many definition for terminology used in data structure, especially u r confused about data structure in an academic setting.