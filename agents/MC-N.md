## MC-N

MC-N is implemented in class MCAgentN. We consider here only the case numberAgents==1 (numberAgents>1 was a majority-vote-test in 2048, was not better than simple MC-N). In case numberAgents==1, the relevant function is getNextAction_PAR.
Pseudocode for MC-N:
Given a state s with available actions A(s), player ps to move in s, and given MC-N parameters iterations ITER, rollout depth rDepth

```
for all actions a \in A(s)
	for i = 1,…,ITER
		scTuplei = rollout(s.advance(a), rDepth)
	avgTuple = < scTuplei>i  				// expectation value over i
	vTable[a] = avgTuple[ps]			
return action abest with highest average score vTable[a] 
```

>Description: Starting from state s advanced by a, a random rollout is performed where each player performs random actions until game is over or maximum rollout depth rDepth is reached. The score tuple of the rollout state newSob is returned and the average over all iterations is taken. 
 
