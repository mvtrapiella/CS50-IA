**Minimax**: there are always two actors:
- MAX(O): wants to maximize the score
- MIN(O): wants to miniminze the score (worsen the position of MAX(0))

Given a [[state]] *s*:
- MAX picks action *a* in ACTIONS(*s*) that produces highest value of MIN-VALUE(RESULTS(*s*, *a*))
- MIN picks action *a* in ACTIONS(*s*) that produces smallest value of MAX-VALUE(RESULTS(*s*, *a*))

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

