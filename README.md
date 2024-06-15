# LEETCODE-Array-502
Let's dry run the provided `Solution` class method `findMaximizedCapital` using a sample input to understand its behavior step by step. Here's a breakdown of the code:

1. **Initialization**:
   - Two priority queues (`minHeap` and `maxHeap`) are initialized.
   - `minHeap` is used to store projects sorted by their capital requirement (ascending order).
   - `maxHeap` is used to store projects sorted by their profits (descending order).

2. **Filling the minHeap**:
   - All projects (represented by instances of the class `T`) are added to `minHeap`.

3. **Main loop**:
   - The loop runs `k` times, representing the maximum number of projects that can be selected.
   - Projects that can be afforded with the current capital (`W`) are moved from `minHeap` to `maxHeap`.
   - If `maxHeap` is empty, the loop breaks early because no further projects can be funded.
   - The most profitable project from `maxHeap` is selected, and its profit is added to the current capital (`W`).

Let's use the following input for a dry run:

- `k = 2` (maximum number of projects that can be selected)
- `W = 0` (initial capital)
- `Profits = [1, 2, 3]` (profits of the projects)
- `Capital = [0, 1, 1]` (capital required for the projects)

**Dry Run**:

1. **Initialization**:
   - `minHeap` and `maxHeap` are initialized.
   - `minHeap` is filled with projects:
     - Project 1: Profit = 1, Capital = 0
     - Project 2: Profit = 2, Capital = 1
     - Project 3: Profit = 3, Capital = 1

2. **First Iteration (k = 2)**:
   - `minHeap`: [(1, 0), (2, 1), (3, 1)] (sorted by capital)
   - `maxHeap`: []
   - Current capital `W` = 0
   - Move projects affordable with `W` from `minHeap` to `maxHeap`:
     - Project 1 (Profit = 1, Capital = 0) is moved to `maxHeap`.
   - `minHeap`: [(2, 1), (3, 1)]
   - `maxHeap`: [(1, 0)] (sorted by profit descending)
   - Select the most profitable project from `maxHeap`:
     - Project 1 is selected, and `W` is increased by its profit (1).
   - Updated capital `W` = 1

3. **Second Iteration (k = 1)**:
   - `minHeap`: [(2, 1), (3, 1)]
   - `maxHeap`: []
   - Current capital `W` = 1
   - Move projects affordable with `W` from `minHeap` to `maxHeap`:
     - Project 2 (Profit = 2, Capital = 1) is moved to `maxHeap`.
     - Project 3 (Profit = 3, Capital = 1) is moved to `maxHeap`.
   - `minHeap`: []
   - `maxHeap`: [(3, 1), (2, 1)] (sorted by profit descending)
   - Select the most profitable project from `maxHeap`:
     - Project 3 is selected, and `W` is increased by its profit (3).
   - Updated capital `W` = 4

4. **End of loop** (k = 0):
   - Final capital `W` = 4

Thus, the final maximized capital after selecting up to 2 projects is 4.

The solution correctly prioritizes selecting the most profitable projects that can be afforded with the current available capital.
