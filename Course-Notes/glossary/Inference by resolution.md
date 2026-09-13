**Inference by resolution**:
Examples
- P v Q
- ¬P v R
Then (Q v R)

- P v Q v S
- ¬P v R v S
Then Q v R v S (we have refactor the S, we do not put 2 types the samel [[propositional symbols]], it is redundant)

- P
- ¬P
Then () -> the empty [[clause]]. The empty [[clause]] is always false, we cannot have at the same time something and not having it. It is a contradiction.

## Proof by contradiction
The algorithm goes as follows:
- To determine if [[Knowledge base|KB]]|=*a*: 
	- Check if ([[Knowledge base|KB]] ^ ¬*a*) is a contradiction? -> I want to check if it is a contradiction, so if it is false it means that is not a contradiction, so it is true.
		- If so (if true), then [[Knowledge base|KB]]|=*a*.
		- Otherwise, no [[entailment]].

- To determine if [[Knowledge base|KB]]|=*a*:
	- Convert ([[Knowledge base|KB]] ^ ¬*a*) to [[Conjuctive normal form]].
	- Keep checking to see if we can use resolution to produce a new [[clause]]. -> e.g. if we have a P and a ¬P so we can create a new clause
		- If ever we produce the empty [[clause]] (equivalent to False),  we have a contradiction, and [[Knowledge base|KB]]|=*a*.
		- Otherwise, if we can't add new [[Clause|clauses]], no [[entailment]].
Example:
![[Pasted image 20260914001704.png]]