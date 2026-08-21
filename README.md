# DSA Patterns

A structured collection of **Data Structures & Algorithms (DSA) patterns** designed to help you recognize recurring problem-solving techniques instead of memorizing individual solutions.

The goal is simple:

> **Don't memorize solutions. Learn to recognize patterns.**

---

## 🎯 Why DSA Patterns?

Many DSA problems look different on the surface but use the same underlying technique.

For example:

* "Find a pair with a target sum"
* "Find two numbers satisfying a condition"
* "Find the longest substring satisfying a constraint"
* "Find the maximum sum subarray"
* "Find the minimum number of operations"

These problems often map to well-known patterns such as:

* Two Pointers
* Sliding Window
* Hashing
* Binary Search
* Prefix Sum
* Monotonic Stack
* Heap / Priority Queue
* Backtracking
* Dynamic Programming
* Graph Traversal
* Greedy Algorithms

Learning these patterns makes it easier to go from:

```text
Problem → Identify Pattern → Choose Technique → Implement → Optimize
```

instead of:

```text
Problem → Panic → Try Random Approaches → Get Stuck
```

---

## 🧠 The Core DSA Mindset

When solving a problem, don't immediately start coding.

Ask:

### 1. What is the input?

* Array?
* String?
* Linked List?
* Tree?
* Graph?
* Matrix?
* Number?

### 2. What is being asked?

* Search?
* Count?
* Optimize?
* Find all possibilities?
* Find maximum/minimum?
* Check existence?
* Construct an answer?

### 3. What constraints exist?

Constraints often tell you which algorithm is possible.

For example:

```text
n <= 10
```

Brute force may be acceptable.

```text
n <= 10^5
```

You probably need approximately:

```text
O(n)
O(n log n)
```

### 4. What pattern does the problem suggest?

Look for signals such as:

```text
sorted array
substring
subarray
contiguous
frequency
top K
minimum/maximum
next greater
all combinations
shortest path
dependencies
```

These keywords often point toward a specific pattern.

---

# 📚 DSA Pattern Roadmap

## 1. Hashing

### When to use

Use hashing when you need:

* Fast lookup
* Frequency counting
* Duplicate detection
* Pair matching
* Grouping
* Prefix-state tracking

### Common Data Structures

```text
HashMap
HashSet
Dictionary
Set
```

### Typical Complexity

```text
Time:  O(n)
Space: O(n)
```

### Common Problems

* Two Sum
* Contains Duplicate
* Group Anagrams
* Longest Consecutive Sequence
* Subarray Sum Equals K

---

# 2. Two Pointers

### When to use

Commonly used when:

* Working with arrays or strings
* The input is sorted
* Searching for pairs
* Processing from both ends
* Maintaining two positions

### Basic Template

```text
left  → 
        ← right
```

Example:

```java
while (left < right) {
    if (condition) {
        left++;
    } else {
        right--;
    }
}
```

### Typical Complexity

```text
Time:  O(n)
Space: O(1)
```

### Common Problems

* Two Sum II
* 3Sum
* Container With Most Water
* Valid Palindrome
* Remove Duplicates from Sorted Array

---

# 3. Sliding Window

One of the most important patterns for array and string problems.

### When to use

Look for:

* Subarray
* Substring
* Contiguous elements
* Longest
* Shortest
* At most K
* Exactly K
* Maximum/minimum within a range

### Basic Template

```text
left = 0

for right in range(n):

    add nums[right]

    while window_is_invalid:
        remove nums[left]
        left++

    update answer
```

### Complexity

```text
Time:  O(n)
Space: O(k)
```

### Common Problems

* Longest Substring Without Repeating Characters
* Maximum Length Substring With Two Occurrences
* Minimum Size Subarray Sum
* Longest Repeating Character Replacement
* Maximum Average Subarray

---

# 4. Prefix Sum

### When to use

Use prefix sums when you need:

* Range sums
* Repeated subarray-sum queries
* Subarray sum conditions
* Cumulative information

### Core Idea

Instead of repeatedly calculating:

```text
nums[l] + nums[l+1] + ... + nums[r]
```

precompute:

```text
prefix[i] = sum of elements before i
```

Then:

```text
sum(l, r) = prefix[r + 1] - prefix[l]
```

### Complexity

```text
Preprocessing: O(n)
Query:         O(1)
Space:         O(n)
```

---

# 5. Binary Search

### When to use

Use binary search when:

* The array is sorted
* The search space is monotonic
* You need first/last occurrence
* You can eliminate half of the search space

### Classic Template

```text
left = 0
right = n - 1

while left <= right:

    mid = left + (right - left) / 2

    if nums[mid] == target:
        return mid

    if nums[mid] < target:
        left = mid + 1
    else:
        right = mid - 1
```

### Complexity

```text
Time:  O(log n)
Space: O(1)
```

### Advanced Pattern

**Binary Search on Answer**

Instead of searching an array, search the possible answer space.

Examples:

* Capacity To Ship Packages Within D Days
* Koko Eating Bananas
* Split Array Largest Sum
* Minimum Time to Complete Trips

---

# 6. Fast & Slow Pointers

### When to use

Especially useful for linked lists.

Typical applications:

* Detect cycle
* Find middle node
* Find cycle entrance
* Compare positions moving at different speeds

### Template

```text
slow = head
fast = head

while fast != null && fast.next != null:

    slow = slow.next
    fast = fast.next.next
```

### Common Problems

* Linked List Cycle
* Linked List Cycle II
* Middle of the Linked List
* Happy Number

---

# 7. Stack

### When to use

Use stacks when the problem involves:

* Matching parentheses
* Nested structures
* Undo operations
* Previous/next relationships
* Expression evaluation

### Common Problems

* Valid Parentheses
* Min Stack
* Evaluate Reverse Polish Notation
* Daily Temperatures
* Remove All Adjacent Duplicates

---

# 8. Monotonic Stack

A specialized stack pattern.

### When to use

Look for:

```text
Next greater
Next smaller
Previous greater
Previous smaller
Nearest greater
Nearest smaller
```

### Core Idea

Maintain the stack in increasing or decreasing order.

Example:

```text
while stack is not empty
      and nums[stack.top] < nums[i]:

    process stack.top
    pop
```

### Common Problems

* Daily Temperatures
* Next Greater Element
* Largest Rectangle in Histogram
* Online Stock Span
* Trapping Rain Water

---

# 9. Queue / BFS

### When to use

Use BFS when processing things:

```text
level by level
```

Typical applications:

* Shortest path in an unweighted graph
* Tree level-order traversal
* Minimum number of moves
* Grid traversal

### Template

```text
queue.add(start)

while queue is not empty:

    node = queue.remove()

    for neighbor in neighbors(node):

        if not visited:

            visited.add(neighbor)
            queue.add(neighbor)
```

### Complexity

```text
Time:  O(V + E)
Space: O(V)
```

---

# 10. Heap / Priority Queue

### When to use

Look for:

* Top K
* Kth largest/smallest
* Minimum/maximum repeatedly
* Scheduling
* Merging sorted collections

### Common Problems

* Kth Largest Element
* Top K Frequent Elements
* Merge K Sorted Lists
* Find Median from Data Stream
* Task Scheduler

### Complexity

Usually:

```text
Insert: O(log n)
Remove: O(log n)
Peek:   O(1)
```

---

# 11. Intervals

### When to use

Look for:

* Intervals
* Meetings
* Start/end times
* Overlapping ranges
* Merging ranges

### Common Approach

Sort by start time:

```text
sort intervals by start

for each interval:

    if overlapping:
        merge
    else:
        create new interval
```

### Common Problems

* Merge Intervals
* Insert Interval
* Non-overlapping Intervals
* Meeting Rooms
* Meeting Rooms II

---

# 12. Greedy

### When to use

A greedy solution makes the best local decision while building toward a global solution.

Look for:

```text
maximum
minimum
earliest
latest
best immediate choice
```

### Important Question

Ask:

> "Can I make the locally optimal choice without hurting the final answer?"

### Common Problems

* Jump Game
* Gas Station
* Assign Cookies
* Activity Selection
* Partition Labels

---

# 13. Backtracking

### When to use

Use backtracking when you need to explore:

* All combinations
* All permutations
* All subsets
* Decision trees
* Constraint-based possibilities

### Basic Template

```text
backtrack(state):

    if solution:
        add result
        return

    for choice in choices:

        make choice

        backtrack(new state)

        undo choice
```

### Common Problems

* Subsets
* Permutations
* Combination Sum
* N-Queens
* Sudoku Solver
* Word Search

---

# 14. Recursion

### When to use

Recursion is useful when the problem naturally breaks into smaller versions of itself.

Common structures:

```text
Tree
Graph
Divide and conquer
Backtracking
Dynamic Programming
```

### Questions to Ask

1. What is the base case?
2. What is the smaller problem?
3. How do I combine the result?

---

# 15. Divide and Conquer

### Core Idea

Break a problem into smaller independent problems.

```text
Problem
   |
   +--- Left
   |
   +--- Right
          |
       Combine
```

### Examples

* Merge Sort
* Quick Sort
* Binary Search
* Maximum Subarray

### Typical Complexity

```text
O(n log n)
```

---

# 16. Dynamic Programming

Dynamic Programming is one of the most important advanced DSA patterns.

### When to use

Look for:

* Optimal answer
* Number of ways
* Minimum/maximum
* Repeated subproblems
* Choices at every step
* "Can we..." decisions

### Two Key Properties

A problem usually has:

### Overlapping Subproblems

The same subproblems appear multiple times.

### Optimal Substructure

The optimal solution can be constructed from optimal solutions to smaller subproblems.

---

## DP Approaches

### Top-Down

```text
Recursion
+
Memoization
```

### Bottom-Up

```text
Tabulation
```

---

## DP Framework

Ask:

```text
1. What is the state?

2. What are the choices?

3. What is the transition?

4. What is the base case?

5. What is the final answer?
```

### Common DP Categories

* 1D DP
* 2D DP
* Knapsack
* Subsequence DP
* String DP
* Interval DP
* Grid DP
* Partition DP
* Tree DP
* Bitmask DP

---

# 17. Graph Traversal

Graphs can represent:

```text
Cities
Networks
Dependencies
Relationships
Connections
Paths
```

Two fundamental traversal techniques:

```text
DFS
BFS
```

### DFS

Useful for:

* Connected components
* Cycle detection
* Backtracking
* Topological traversal
* Exploring paths

### BFS

Useful for:

* Shortest path in unweighted graphs
* Level-order exploration
* Minimum number of steps

---

# 18. Topological Sort

### When to use

Use topological sorting when the problem contains:

```text
dependencies
prerequisites
ordering
tasks
courses
build systems
```

The graph must be a **Directed Acyclic Graph (DAG)**.

### Common Algorithms

```text
Kahn's Algorithm
DFS
```

### Common Problems

* Course Schedule
* Course Schedule II
* Alien Dictionary
* Build System Dependencies

---

# 19. Union Find / Disjoint Set Union

### When to use

Useful for:

* Connected components
* Dynamic connectivity
* Grouping
* Detecting cycles in undirected graphs

### Operations

```text
find(x)
union(x, y)
```

With:

```text
Path Compression
+
Union by Rank/Size
```

the operations become extremely efficient.

---

# 20. Trie

### When to use

Use a Trie for:

* Prefix searches
* Dictionary problems
* Autocomplete
* Word matching
* String prefixes

### Common Problems

* Implement Trie
* Word Search II
* Design Add and Search Words
* Replace Words

---

# 21. Bit Manipulation

### Useful Operations

```text
AND  &
OR   |
XOR  ^
NOT  ~
LEFT SHIFT  <<
RIGHT SHIFT >>
```

### Useful Properties

```text
x ^ x = 0
x ^ 0 = x
```

### Common Problems

* Single Number
* Counting Bits
* Power of Two
* Missing Number
* Subsets using Bitmasking

---

# 22. Matrix / Grid Traversal

### When to use

Common in:

* Islands
* Mazes
* Grid paths
* Connected components
* Flood fill

Typical directions:

```text
up
down
left
right
```

Sometimes include diagonals:

```text
top-left
top-right
bottom-left
bottom-right
```

### Common Problems

* Number of Islands
* Flood Fill
* Rotting Oranges
* Pacific Atlantic Water Flow
* Word Search

---

# 🔍 Pattern Recognition Cheat Sheet

| Problem Signal               | Likely Pattern         |
| ---------------------------- | ---------------------- |
| Pair in sorted array         | Two Pointers           |
| Contiguous subarray          | Sliding Window         |
| Contiguous substring         | Sliding Window         |
| Frequency counting           | HashMap                |
| Fast lookup                  | HashSet / HashMap      |
| Sorted search                | Binary Search          |
| First/last position          | Binary Search          |
| Next greater element         | Monotonic Stack        |
| Top K                        | Heap                   |
| Kth largest                  | Heap / Quickselect     |
| Overlapping intervals        | Intervals              |
| All combinations             | Backtracking           |
| All permutations             | Backtracking           |
| All subsets                  | Backtracking / Bitmask |
| Minimum steps                | BFS                    |
| Shortest unweighted path     | BFS                    |
| Tree traversal               | DFS / BFS              |
| Dependencies                 | Topological Sort       |
| Connected components         | DFS / BFS / Union Find |
| Repeated subproblems         | Dynamic Programming    |
| Maximum/minimum with choices | DP / Greedy            |
| Prefix matching              | Trie                   |
| Connectivity                 | Union Find             |
| Range sum                    | Prefix Sum             |
| Next/previous greater        | Monotonic Stack        |
| Locally optimal choice       | Greedy                 |

---

# 🧩 How to Approach a New DSA Problem

Use this process every time.

## Step 1 — Understand the Problem

Explain the problem in your own words.

Don't code immediately.

---

## Step 2 — Identify the Data Structure

Ask:

```text
Array?
String?
Linked List?
Tree?
Graph?
Matrix?
Heap?
```

---

## Step 3 — Check Constraints

Estimate what complexity is required.

For example:

```text
n <= 20
```

Possible:

```text
O(2^n)
```

But:

```text
n <= 100000
```

Usually requires something closer to:

```text
O(n)
O(n log n)
```

---

## Step 4 — Identify the Pattern

Look for keywords.

```text
substring      → Sliding Window

sorted         → Binary Search / Two Pointers

top K          → Heap

next greater   → Monotonic Stack

dependencies   → Topological Sort

all possible   → Backtracking

optimal value  → DP / Greedy
```

---

## Step 5 — Start With Brute Force

Before optimizing, understand the straightforward solution.

Ask:

```text
What would the simplest solution be?

Why is it too slow?

What repeated work can I eliminate?
```

This often reveals the optimized pattern.

---

# ⚡ Complexity Cheat Sheet

| Complexity | Typical Use                             |
| ---------- | --------------------------------------- |
| O(1)       | Direct access / calculation             |
| O(log n)   | Binary Search                           |
| O(n)       | Hashing / Two Pointers / Sliding Window |
| O(n log n) | Sorting / Efficient divide & conquer    |
| O(n²)      | Nested loops / 2D problems              |
| O(2ⁿ)      | Subsets / Backtracking                  |
| O(n!)      | Permutations                            |
| O(V + E)   | Graph traversal                         |

---

# 🗂️ Recommended Repository Structure

```text
dsa-patterns/
│
├── README.md
│
├── 01-hashing/
│   ├── README.md
│   └── problems/
│
├── 02-two-pointers/
│   ├── README.md
│   └── problems/
│
├── 03-sliding-window/
│   ├── README.md
│   └── problems/
│
├── 04-prefix-sum/
│   ├── README.md
│   └── problems/
│
├── 05-binary-search/
│   ├── README.md
│   └── problems/
│
├── 06-fast-slow-pointers/
│
├── 07-stack/
│
├── 08-monotonic-stack/
│
├── 09-queue-bfs/
│
├── 10-heap/
│
├── 11-intervals/
│
├── 12-greedy/
│
├── 13-backtracking/
│
├── 14-recursion/
│
├── 15-divide-and-conquer/
│
├── 16-dynamic-programming/
│
├── 17-graphs/
│
├── 18-topological-sort/
│
├── 19-union-find/
│
├── 20-trie/
│
├── 21-bit-manipulation/
│
└── 22-matrix/
```

---

# 📈 Recommended Learning Order

Don't try to learn everything simultaneously.

### Beginner

```text
1. Arrays
2. Strings
3. Hashing
4. Two Pointers
5. Sliding Window
6. Stack
7. Binary Search
8. Prefix Sum
```

### Intermediate

```text
9. Linked Lists
10. Fast & Slow Pointers
11. Heap
12. Intervals
13. Recursion
14. Trees
15. BFS
16. DFS
17. Backtracking
```

### Advanced

```text
18. Greedy
19. Dynamic Programming
20. Graph Algorithms
21. Topological Sort
22. Union Find
23. Trie
24. Advanced DP
25. Bit Manipulation
```

---

# 🧪 Problem-Solving Template

For every problem, document your thinking using:

```text
Problem
   ↓
Understand
   ↓
Constraints
   ↓
Brute Force
   ↓
Find Bottleneck
   ↓
Recognize Pattern
   ↓
Optimize
   ↓
Implement
   ↓
Analyze Complexity
   ↓
Test Edge Cases
```

---

# 📝 Problem Documentation Template

For each solved problem, maintain:

```text
## Problem

What is being asked?

## Pattern

Which DSA pattern is being used?

## Intuition

Why does this pattern work?

## Approach

Step-by-step solution.

## Complexity

Time: O(?)
Space: O(?)

## Edge Cases

- Empty input
- Single element
- Duplicate values
- Maximum constraints
- Negative values
```

---

# 🎯 The Goal

The goal of this repository is **not to collect hundreds of solved problems**.

The goal is to build the ability to look at a new problem and think:

```text
"I have seen this structure before."

"This looks like Sliding Window."

"This is probably Binary Search on Answer."

"This is a Monotonic Stack problem."

"This is an optimization problem with overlapping subproblems."

"This looks like BFS because we need minimum steps."
```

That recognition is the real DSA skill.

---

# 🚀 Final Principle

> **Patterns are more valuable than solutions.**

A single pattern can help solve dozens of problems.

A memorized solution usually helps solve only one.

Keep practicing:

```text
Recognize → Reason → Implement → Optimize → Repeat
```

---

## 📌 Related Repositories

Part of the **CodeWithIshwar** learning ecosystem.

Recommended companion repositories:

* `leetcode-solutions`
* `dsa-thinking`
* `problem-solving-notes`
* `system-design-thinking`
* `engineering-notes`

---

## 👨‍💻 Author

**Ishwar**

Building in public as **CodeWithIshwar**.

> Learn deeply. Solve consistently. Build publicly.

---

⭐ If this repository helps you understand DSA patterns, consider starring the repository.
