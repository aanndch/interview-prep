# Pre-Solve Checklist

## 1. Read & Rewrite
- [ ] Paraphrase the problem in your own words
- [ ] Write down the **input type** and **output type**
- [ ] Underline the **key verb** (find, count, return, modify, check)

## 2. Constraints Scan

| Clue | Likely Complexity |
|------|-------------------|
| n ≤ 20 | O(2ⁿ), O(n!) — backtracking |
| n ≤ 500 | O(n³) — Floyd, DP |
| n ≤ 10³ | O(n²) — nested loops |
| n ≤ 10⁵ | O(n log n) — sorting, heap |
| n ≤ 10⁶ | O(n) — two pointers, sliding window, DP |
| n ≤ 10⁹ | O(log n) — binary search |

- [ ] What is the **size range** of the input?
- [ ] Are there **duplicates**?
- [ ] Are values **positive only**, or can they be negative/zero?
- [ ] Is the array **sorted** or can it be sorted?
- [ ] Are characters **lowercase only** or full ASCII/Unicode?

## 3. Edge Case Inventory
- [ ] Empty input (`[]`, `""`)
- [ ] Single element
- [ ] All elements the same
- [ ] Already sorted / reverse sorted
- [ ] Target not present
- [ ] Minimum/maximum values (overflow risk)
- [ ] Null / None input
- [ ] k larger than input length

## 4. Brute Force First
- [ ] Verbalize the naive O(n²) or O(n³) approach
- [ ] Say: *"This works but we can do better"*
- [ ] Then pivot to the optimized approach

## 5. Pattern Recognition

Ask yourself these questions to narrow the pattern:

| Question | Pattern to Try |
|----------|----------------|
| "Sorted or can sort?" | Two Pointers, Binary Search |
| "Contiguous subarray/substring?" | Sliding Window |
| "Need frequency counts?" | Hash Map / Frequency Array |
| "Subset / combination / permutation?" | Backtracking |
| "Shortest/longest path?" | BFS / DFS / DP |
| "Optimal choice at each step?" | Greedy |
| "Overlapping subproblems?" | Dynamic Programming |
| "In-place modification?" | Two Pointers (fast & slow) |
| "Need max/min in sliding window?" | Monotonic Stack / Deque |
| "Next greater/smaller element?" | Monotonic Stack |

## 6. Example Walkthrough
- [ ] Trace through the given examples **manually** on paper/whiteboard
- [ ] Create a **custom example** that covers edge cases
- [ ] Confirm your approach works on your custom example

## 7. Complexity Target
Before writing code, set your goal:
```
Time:  O(___)    (e.g., O(n), O(n log n))
Space: O(___)    (e.g., O(1), O(n))
```

## 8. Test Strategy
After coding, run:
- [ ] The given example(s)
- [ ] Empty input
- [ ] Single element
- [ ] Minimum/maximum values
- [ ] Large input (mental check for O(n) viability)

---

## During Coding — Common Traps

```
 Off-by-one:  for i in range(n)      vs  for i in range(1, n)
              while l < r            vs  while l <= r
              arr[i]                 vs  arr[i-1]

 Pointer drift:  always move at least one pointer per iteration

 Mutation:  did we modify the input? caller may not expect it

 Integer overflow:  use long or 64-bit when sums can exceed 2³¹-1

 Empty collections:  arr[0] on [] will crash
```

## Quick Reference: Complexity Classes

| Class | Typical Use | Example |
|-------|-------------|---------|
| O(1) | Hash lookup, deque front/back | Two Sum (with hash map) |
| O(log n) | Binary search, balanced tree | Binary Search, Koko Bananas |
| O(n) | Single pass, two pointers | Valid Palindrome, Move Zeroes |
| O(n log n) | Sorting, divide & conquer | 3Sum, Merge Intervals |
| O(n²) | Nested loops over all pairs | Brute-force 3Sum |
| O(2ⁿ) | Subset enumeration | Backtracking (Subsets) |
