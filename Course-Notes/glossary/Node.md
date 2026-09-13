**Node**: is a data structure that keeps track of:
- a [[state]] -> the one we are currently on
- a parent (a [[node]] that generates this [[node]]) -> used to know how we reached to the actual state (by backtraking the arent nodes until the [[initial state]])
- an [[actions|action]] ([[actions|action]] applied to parent to get [[node]])
- a [[path cost]] (from [[Initial state]] to [[goal state]])