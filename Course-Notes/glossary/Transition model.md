**Transition model**: a description of what [[state]] results from performing any applicable [[actions|action]] in any [[state]]. It is more precisely defined as a function:
- Results(s, a) returns the [[state]] resulting from performing [[actions|action]] *a* in [[state]] *s*.
Example:
![[Pasted image 20260911120559.png]]

We pass to the Results() function a [[state]] (the actual [[state]] of the board), an [[actions|action]] (move the tile to  the right) and the function returns a new [[state]] (the previous [[state]] but with the tile 15 moved one square to the right).