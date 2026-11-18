## Theta*

**theta\*** is an any-angle pathfinding algorithm built on [A\* search](https://wikipedia.org*) that finds short & direct routes across grids without restricting movement to grid edges or 45/90-degree increments

### how it works
* **line-of-sight checks:** unlike standard A\*, which connects a node only to adjacent grid neighbors, Theta\* checks whether a node has an unobstructed line of sight to its current parent's parent (an ancestor node)
* **sny-Angle shortcuts:** if the line of sight is clear and the direct distance is shorter, Theta\* connects the node directly to that ancestor, skipping intermediate grid cells
* **heuristic search:** like A\*, it prioritizes candidate nodes using the accumulated path cost ($g$) plus a heuristic estimate to the goal ($h$) to guide the search efficiently

### key characteristics
* **smoother, shorter paths:** removes artificial zig-zagging along grid edges, producing natural, near-Euclidean paths without requiring a separate post-processing smoothing pass
* **fast & near-Optimal:** maintains runtimes close to standard A\* while yielding significantly shorter paths, though it does not strictly guarantee the mathematically optimal shortest path in every edge case
* **common variants:** related extensions include **Lazy Theta\*** (which delays line-of-sight checks to improve speed) and **Phi\*** (designed for dynamic environments with changing obstacles)
