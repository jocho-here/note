# General Algorithm Notes

## Things I learned from Young Cho Lee's solution to rottening oranges
1. When working with grids, instead of checking whether indices around the current index are in the range, check the following:
```
...
row, col = queue.pop()

for adjacent_cell in (
    (row+1, col),
    (row-1, col),
    (row, col+1),
    (row, col-1)
):
...
```
2. When working with queue, use python's built-in queue for a faster processing time
```
from collections import deque as queue

q = queue()
q.insert(0, 1)  # O(1) run time compared to O(n) of list
q.insert(0, 2)
q.insert(0, 3)
print(q.pop())  # will print 1, as this is FIFO queue
```

## Tips on solving problems
- Try to lower re-calculating what's been calculated already

## Largest Rectangle in Histogram

## Graphs
- Remember what you did for Bloomberg

## Finding unique paths through grid
- X * Y rectangle grid
- Using binomial coefficient (combinatorics)
    - (X+Y) choose X,
- Using memoization
    - Value at the origin is 1
    - For all other nodes, the value is the sum of its top and left neighbors

## Binary search or binary sort
- Whenever you see runtime limit of something log(n), then consider using whatever binary
- Be careful of the edge case
    - `l` and `r` are one index apart
        - if list[l] < val, list.insert(l+1,val)
        - else, list.insert(l, val)

## Priority Queue
- Whenever there's a chance to have lowest priority element repeatedly, use a priority queue.
    - Heap is usually used to implement a priority queue.  Each parent node can have at most n many children (generally up to 2).  At all time, a parent node must be smaller than its child nodes.
        - Implementation: Usually with array, and children of a parent node at `x` are at `2*x + 1` and `2*x + 2`.
        - Insert: It puts the added element at the very back and heapify to balance the heap
        - Pop: It pops the root, brings the last element in the array to the 0 index, start heapifying to balance the tree.  It usually compares the recently moved one with the smallest child of itself and see if the number is smaller than that.  If it finds a number that's smaller than itself, it changes places with it.
    - Using in Python
        - q = queue.PriorityQueue()
        - put(item)
        - get()
            - remove and return and item

## Solving Dynamic Programming
(a) Identify the subproblems
    - What are all the different ways can your recursive algorithm call itself, starting with some initial input? For example, the argument to RecFibo is always an integer between 0 and n.
(b) Choose a memoization data structure
    - Find a data structure that can store the solution to every subproblem you identified in step (a). This is usually but not always a multidimensional array.
(c) Identify dependencies
    - Except for the base cases, every subproblem depends on other subproblems—which ones? Draw a picture of your data structure, pick a generic element, and draw arrows from each of the other elements it depends on. Then formalize your picture.
(d) Find a good evaluation order
    - Order the subproblems so that each one comes after the subproblems it depends on. You should consider the base cases first, then the subproblems that depends only on base cases, and so on, eventually building up to the original top-level problem. The dependencies you identified in the previous step define a partial order over the subproblems; you need to find a linear extension of that partial order. Be careful!
(e) Analyze space and running time
    - The number of distinct subproblems deter- mines the space complexity of your memoized algorithm. To compute the total running time, add up the running times of all possible subproblems, assuming deeper recursive calls are already memoized. You can actually do this immediately after step (a).
(f) Write down the algorithm
    - You know what order to consider the subproblems, and you know how to solve each subproblem. So do that! If your data structure is an array, this usually means writing a few nested for-loops around your original recurrence.
