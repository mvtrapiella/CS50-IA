Knowledge is very important for taking decisions. Humans usually use our knowledge about something in order to be able to find the solution to a problem. The [[agents]] that use knowlege are named as [[knowledge-based agents]]

### How do we represent knowledge on an [[agent]]?
## Propositional logic
Based on a logic of proposition (statements of the world). In order to represent things on this logic we use **propositional symbols** (P, Q, R), used to represent some fact of the world.

Now we have individual facts of the world, but we want a way to connect this prepositional symbols: **[[logical connectives]]**.

In order to evaluate those **propositional symbols** we use a [[model]]. In order to do that, [[knowledge-based agents]] has what is call a [[knowledge base]] in order to perform that task.

We would basically tell our AI information about a situation or problem that it is trying to solve. The AI will store that information in its [[knowledge base]] and will use that information in order to be able to drawn conclusion about the rest of the world.

A very important idea in order to achieve the computer to drawn new conlusions from past ones is [[inference]] in which [[entailment]] will take a very important role so it allows as to derive true conclusions from previous true conlusion.

Example:
P: If it is Tuesday.
Q: It is raining.
R: Harry will go for a run.

[[Knowledge base|KB]]: (P ^ ¬Q) -> R => If it is Tuesday and it is not raining, Harry will go for a run
We know that P -> true, that Q -> false so ¬Q -> true and that (P ^ ¬Q) -> R -> true

[[Inference]]: so if P ^ ¬Q -> true (true ^ true -> true) and the whole sentence is true, we know that in order to true -> x to be true x must be true. So we have infered that R is true

This that we have done is an [[inference]] algorithm and is what we want to implement in a computer. Finally, what we want to answer is the following:
- **[[Knowledge base|KB]]|=*a* ??** -> with the knowledge that we have in our [[Knowledge base|KB]] can we conlude that a sentence *a* is true? 

### How can we do that?
There a couple of different algorithms in order to do that. The most simpe one is [[model checking]]. However, [[model checking]] is not a particularly efficient algorithm, so we need to find other ways to do this. 
In order to do this we use [[inference rules]].

## [[Search]] problems as a [[knowledge]] problem
A [[search]] problem can be seen as a [[knowledge]] problem in which we want to prove that one [[solution]] is true and the others false. This is named [[Theorem Proving]]. 
### Conversion to [[Conjuctive normal form|CNF]]
- Eliminate biconditionals
	- turn (*a* <-> *b*) into (*a* -> *b*) ^ (*b* -> *a*)
- Eliminate implications
	- turn (*a* -> *b*) into ¬*a* v *b*
- Move ¬ inwards using th De Morgan's law
	- e.g. turn ¬(*a* ^ *b*) into ¬*a* v ¬*b*
- Use distributive law to distribute v wherever possible 

### Why is this helpful?
By doing this we can apply the Resolution rule ([[Inference rules]]) and eliminates some of the [[Clause|clauses]] in order to drawn a new conlusion. This in named [[Inference by resolution]].

All this are algorithms for propositional logic. However, there exists other types of logic and, in fact, proposiotional logic has a serie of limitations (its poor degree of expresivity).
One of this types of different logics is First-Order Logic.

## First-Order Logic
It is more expressive than propositional logic.
In this type of logic we are going to have:
- Contant symbol -> represnt object like people or houses (Minerva, Horace...)
- Predicate symbol -> property of the constant symbol that might hold true or false (Person, House, BelongsTo...)
Example:
- Person(Minerva) => Minerva is a Person
- House(Griffindor) => Griffindor is a House
- ¬House(Minerva) => Minerva is not a House
- BelongsTo(Minerva, Griffindor) => Minerva belongs to Griffindor -> There are predicates that hold a binary relationship

Also we can use quantifiers:
- [[Universal Quantification]]
- [[Existential Quantification]]
Example:
![[Pasted image 20260914004936.png]]
