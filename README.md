# BFS-DFS

# Breadth-First Search (BFS):
BFS explores the search space level by level. It explores all states at the current level before moving to the next level. This ensures that the shortest path to the solution is found. Intuition: BFS is generally faster when the optimal solution is at a shallow depth in the searchtree. If the solution can be reached with a small number of moves, BFS will find it quickly. BFS works better when a user searches for the vertices that stay closer to any given source. BFS is complete (finds a solution if one exists) and optimal (finds the shortest solution) for problems with a finite branching factor. BFS can have high memory requirements, especially for problems with a large state space, as it stores all explored states in memory.

# Algorithm:
1. Initialize an empty queue.
2. Enqueue the initial state along with an empty path into the queue.
3. Initialize an empty set called visited to keep track of visited states.
4. While the queue is not empty:
● Dequeue a state and its path from the front of the queue.
● If the dequeued state is the goal state, return the path.
● Otherwise:
○ Add the dequeued state to the visited set.
○ Find the coordinates of the blank tile ('B') in the dequeued state.
○ For each possible move (up, down, left, right) from the current blank tile
position:
■ Calculate the new position after the move.
■ If the new position is valid and has not been visited:
● Create a new state by applying the move to the dequeued
state.
● Enqueue the new state along with the updated path into
the queue.
5. If the queue becomes empty and no solution is found, return None or indicate that no
solution exists.

# Depth First Search(DFS):
The idea behind DFS is to go as deep into the graph as possible and backtrack once you are at a vertex without any unvisited adjacent vertices. It is very easy to describe/implement the algorithm recursively: We start the search at one vertex. After visiting a vertex, we further perform a DFS for each adjacent vertex that we haven't visited before. This way we visit all vertices that are reachable from the starting vertex. DFS is often chosen when memory constraints are a concern, as it uses less memory compared to Breadth-First Search (BFS). DFS is mostly used in Graph traversal, Maze solving, Backtracking, and Decision Trees. It's important to note that DFS may not guarantee to find the optimal solution, especially in scenarios where the solution is far from the initial state. It can get stuck in deep branches before exploring other potentially better solutions. Additionally, in cases of deep or infinite paths, DFS might not terminate without proper precautions.

# Algorithm:
1. Define the goal_state as the solved configuration of the 8-puzzle and the possible
movements (up, down, left, right) along with their names.
2. Implement utility functions:
● is_goal(state): Checks if the given state matches the goal state.
● get_blank_tile_index(state): Finds the index of the blank tile ('B') in the state.
● perform_move(state, move): Given a state and a move, calculate the new state
after applying the move.
3. Implement the main dfs function:
● Takes state, visited list, and depth as input.
● Limits the depth of exploration to prevent excessive recursion.
● Appends the current state to the visited list.
● If the current state is the goal state, returns the state.
● Loops through possible moves:
○ Applies the move to the current state.
○ If the new state is valid and not visited, recursively calls ‘dfs’ with the new
state and increments the depth.
○ If a solution is found in the recursion, returns the solution.
4. Implement the main function:
● Takes user input for the initial state (list of 9 elements).
● Validates the input length.
● Calls the dfs function with the initial state and prints the steps and solution if
found.
5. The program executes the main function if it's run directly.
