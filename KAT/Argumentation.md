22100413:01
Status:  #KAT
Tags: 

# Argumentation

## Argumentation
- positions
- pros and cons
- dialogue
- Conflict resolution

A bike of Mary is stolen and John buys the bike from the theft. Who’s bike is it?
	It depends on whether John knew it was stolen.

Use of argumentation:
- For internal reasoning:
	- Reasoning about beliefs, goals, intentions, actions
- For their interactions with other agents
	- Information exchange, deliberation, negotiation, collaboration

## History of argumentation in AI

- The early days of AI focused on classical logic, which is *monotonic*: a conclusion that logically follows from a set of premises also follows logically from any larger set of premises
- -   Since reasoning often uses incomplete, uncertain and inconsistent information, the focus shifted to **nonmonotonic logic**: a conclusion may no longer follow from a larger set of premises
	- Nonmonotonic logic coincides with the philosophical notion of **defeasible reasoning**

**Reiter's logic for default reasoning** (1980)
	Birds fly
	BIRD(x) : M FLY(x). FLY(x) A penguin does not fly
	PENGUIN(x) → FLY(x). FLY(t) follows from BIRD(t)
	FLY(t) does not follow from BIRD(t)
	PENGUIN(t)

**Pollock's defeasible reasoning:**
	- red light example – **undercutting defeat**. 
	- If an object looks red, is it red or is it illuminated by a red light

**Toulmin's "The uses of argument"**:
	- Uses argumentation in reasoning
	- Toulmin proposed to analyze reasoning in a way different from classical logic and probabilistic reasoning: as argumentation

**Phan Minh Dung's abstract argumentation** (1995):
	- Dung proposed to focus on the argument attack relation as a mathematical directed graph
## Dung's abstract argumentation
Dung's basic principle of **argument acceptability**. 
- An argument $\alpha$ is **acceptable** with respect to a set of argument A if for each argument $\beta$ that attacks $\alpha$, there is an argument $\gamma$ in A that attacks $\beta$

**Admissible sets**
- They are *conflict free*
- Each argument in A is *acceptable* with respect to A.

**Preferred extension**:
- an *admissible set* that is maximal with respect to set inclusion
- It can be an empty set
- It is a *complete extension*

**Stable extension**:
- The set is *Admissible*
- all arguments that are not in the set are attacked by an argument in the set
- A *stable extension* is a *preferred extension*, but not always the other way around.
- It is a *complete extension*

**Complete extension**
- *Admissible set*
- Each argument outside A is *not* acceptable with respect to A
	- - If $\alpha$ is acceptable with respect to A, $\alpha$ is in A.
- Can be an empty set

**Grounded extension**
1. Label all nodes without attackers or with all attackers labeled out as in.
2. Label all nodes with an in attacker as out.
3. Go to 1 if changes were made; else stop.
- It is the smallest *complete extension*

**attack relation**
- 

**Basic properties**:
- An *attack relation* always has a *preferred extension*. Not all *attack relations* have a *stable extension*.
- An *attack relation* can have more than one preferred/stable extension.

## Argumentation schemes
- **Douglas Walton** proposed to collect argumentation schemes. 
- *Argumentation schemes* are a generalisation from the inference rules in logic

**Inference rules in logic**
1. P. If P then Q
		Therefore Q
2. All Ps are Qs. Some R is not a Q. 
		Therefore some R is not a P.

**Critical Questions**
Argumentation scheme for witness testimony: 
- Witness A has testified that P. Therefore: P
Critical questions: 
- Wasn’t A mistaken?
- Wasn’t A lying?

- Argumentation schemes have:
	- *Premises*,
	- *Conclusions*,
	- *Critical questions*

## Argumentation in AI today

In AI, **Argumentation schemes** are modelled using *knowledge representation approaches*

**Argumentation systems**
Argumentation systems are systems that can *conduct a critical discussion* in which hypotheses can be constructed, tested and evaluated on the basis of reasonable arguments.


---
# References