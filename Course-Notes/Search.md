We want the [[agent]] to search for the solution of a problem.
Examples of search problems:
- Find the best move in a chess game.
- Find the exit in a maze.
- Find the shortest route.

A search problem will **always  be represented with a graph**.

## Components of a seach problem:
- [[Initial state]]
- [[Actions]]
- [[Transition model]]
- [[Goal test]]
- [[Path cost]] function


## **How do we work?**
### Aproach:
- Start with a [[frontier]] that contains the [[initial state]].
- Repeat:
	- If the [[frontier]] is empty, no [[solution]]
	- Remove a [[node]] from the [[frontier]] -> **very important part of the algorithm**
	- If [[node]] contains a [[goal state]], return the [[solution]]
	- Expand the [[node]], add resulting [[node|nodes]] to the [[frontier]]

### What could go wrong with that approach?
What happens if from an A [[node]] we go to a B [[node]] and then from that B [[node]] we can return to the A [[node]]? If we are not carefull we could enter in an infinite loop.

#### How do we fix this?
One way is keeping track of what we have aleady explored.

### Revised aproach
- Start with a [[frontier]] that contains the [[initial state]].
- Start with an empty explored set.
- Repeat:
	- If the [[frontier]] is empty, no [[solution]]
	- Remove a [[node]] from the [[frontier]] -> **very important part of the algorithm**
	- If [[node]] contains a [[goal state]], return the [[solution]]
	- **Add the [[node]] to the explored set**
	- Expand the [[node]], add resulting [[node|nodes]] to the [[frontier]] **if they are not already in the [[frontier]] or the explored set** -> this fix the problem of the loop

### How do we add and remove things from the [[frontier]]?
- We could use an stack (LIFO). -> [[Depth-first search]] (DFS)
- We could use a queue (FIFO) -> [[Breadth-first traversal]] (BFS)
In some cases [[Breadth-first traversal|BFS]] could lead to a [[optimal solution]] where [[Depth-first search|DFS]] could not but there are also case where [[Depth-first search|DFS]] could find a soultion with less memory usage than [[Breadth-first traversal|BFS]] -> trade-off
When we are working with unweighted graphs, [[Breadth-first traversal|BFS]] **will always find the [[optimal solution]]**. 

As we can see the [[Breadth-first traversal|BFS]] and [[Depth-first search|DFS]] have different trade offs but, even though [[Breadth-first traversal|BFS]] reaches the [[optimal solution]], we must have to find another more intelligent algorithm that do not explore so many unnecessary [[state|states]].

## Which type of algorithms could do that?
The answer is [[informed search]] algorithms. In this case we are going to use [[Greedy best-first search|GBFS]] algorithms, that uses a heuristic in order to give the algorithm a analitical decision making.
Not all the [[Greedy best-first search|GBFS]] are going to find the [[optimal solution]] even in cases where a [[Breadth-first traversal|BFS]] would have found it. It depends on the heuristic. 

## Which solution do we have?
In order to fix that, we usually use algorithms with that follows the Admissibility and Consistency / Monotonicity principles, like the [[A star search| A*]]. 

### **Important**
[[A star search| A*]] is optimal if:
	- *h(n)* is admissible (never overestimates the true cost), and
	- *h(n)* is consistent (for every [[node]] *n* and succesor *n'* with step cost *c*, *h(n)*, <= *h(n)* + *c*) -> it means that my cost at the actual [[state]] should not be more than the cost of my succesor being: the cost on my succesor + the cost to go from the previous [[state]] to it.

## [[Adversarial search]]
The most used algorithm for this type of cases (games like chess) is **[[minimax]]**.
First we must define what is a game when using a [[minimax]] algorithm.

### Game
- S0: [[initial state]]
- PLAYER(s): returns which player to move in [[state]] *s*
- [[ACTIONS]](s): returns legal moves in [[state]] *s*.
- RESULTS(*s*, *a*): returns [[state]] after action *a* taken in [[state]] *s*
- TERMINAL(*s*): checks if [[state]] *s* is a terminal [[state]]
- UTILITY(*s*): final numerical value for a terminal [[state]] *s*

### How would a minimax function be done?
function MAX-VALUE(state):
	if TERMINAL(state):
		return UTILITY(state)
	v = -infinity

	for action in ACTIONS(state):
		v = MAX(v, MIN-VALUE(RESULTS(state, action)))
	return v

function MIN-VALUE(state):
	if TERMINAL(state):
		return UTILITY(state)
	v = infinity

	for action in ACTIONS(state):
		v = MIN(v, MAX-VALUE(RESULTS(state, action)))
	return v

This functions will take longer and longer as the games grow and start to complicate. 

### What optimizations could we do?
The most typical optimization for [[minimax]] algorithms is **alpha-beta pruning**.
![[Pasted image 20260912162213.png]]

As we can see in the image in the second branch, beacuse the red arrow represents the player that is always trying to minimize the score has already obtained a 3, this means that at least that player is going to have a 3 or lower (if the remaining [[state]] gives an evaluation of 2, for example). Because in the previous branch, a value of 4 was obtained, we knows that if the actual branch gives a value of 3 or lower (supposing that the MIN player plays optimly), the MAX player is always going to choose the 4 beacuse it will be bigger than 3 or less. The same goes for the remaining branch where the first [[state]] is a 2. 

Even with **alpha-beta pruning**, there are games, like chess, where the number of possibilities is so big, that if we want to explore all of them we will never end.

### Solution to that?
The main solution is to use **alpha-beta pruning** with a limited depth, so we stop exploring when we reach a winning terminal, no more available moves or we reach a concrete depth: **Depth-Limited [[Minimax]]**.
For this, we must use an [[evaluation function]] in order to determine how good is the position at we stop in order to be able to choose the best path. 




