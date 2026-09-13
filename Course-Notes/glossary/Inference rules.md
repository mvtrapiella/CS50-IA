**Inference rules**:  some sort of rules we can apply to existing knowledge in order to create new knowledge.
- Modus Ponens:
	- *a* -> *b* (If it is raining, then Harry is inside)
	- *a* (It is raining)
	Then *b* is true (Harry is inside)
	
-  And Elimination
	- *a* ^ *b* (Harry is friends with Ron and Hermione)
	Then *a* is true and *b* is true (Harry is friend with Hermione)
	
- Double negation elimination
	- ¬(¬*a*) (It is not true that Harry did not pass his exam)
	Then *a* (Harry passed his exam)
	
- Implication elimination
	- *a* -> *b* (If it is raining, then Harry is inside)
	Then ¬*a* v *b* (It is not raining or Harry is inside)
	
- Biconditional Elimination
	- *a* <-> *b* (It is raining if and only if  Harry is inside)
	Then (*a* -> *b*) ^ (*b* -> *a*) (If it is raining Harry is inside and if Harry is inside then it is raining)
	
- De Morgan's Rule
	- ¬(*a* ^ *b*) (It is not true that Harry and Ron passed the test)
	Then ¬*a* v ¬*b*(Harry did not pass the test or Ron did not pass the test)
- De Morgan's Rule
	- ¬(*a* v *b*) (If is not true that Harry or Ron passed the test)
	Then ¬*a* ^ ¬*b*(Harry did not pass the text and Ron did not pass the text)
	
- Distributive Property
	- (*a* ^ (*b* v *y*))
	Then (*a* ^ *b*) v (*a* ^ *y*)
- Distributive Property
	- (*a* v (*b* v *y*))
	Then (*a* v *b*) ^ (*a* v *y*)

- Unit Resolution Rule
	- *a* v *b* ((Ron is in the Great Hall) v (Hermione is in the library))
	- ¬*a* (Ron is not in the Great Hall)
	Then *b* (Hermione is in the library)
- Unit Resolution Rule
	- *a* v *b* ((Ron is in the Great Hall) v (Hermione is in the library))
	- ¬*a* v *c* ((Ron is not in the Great Hall) v (Harry is sleeping)) 
	Then *b* v *c* (Hermione is in the library or Harry is sleeping)
