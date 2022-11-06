22092713:01
Status:  #KAT
Tags: 

# Norms
### The need for norms in AI
**General Data Protection Regulation (GDPR)**
- Includes a *right to explanation* for automated decisions 
	- The data subject should have the right not to be subject to a decision (...) which is based solely on automated processing
	- (...) such processing should be subject to suitable safeguards, which should include (...) the right to (...) to obtain an explanation of the decision reached

**Automated Lane Keeping Systems (ALKS)**
- Autonomous driving in traffic jams, without a human driver paying attention, up to 60 km/h
- Conditions:
	- The driver is in a normal position, and is available upon being alerted
	- The car is in a highway
	- The systems work properly
	- The weather is ok
## Coordination
- The activities of agents can interact, both positively and negatively
- Successful cooperation is an example of positive interaction
- Traffic jams are an example of negative interaction
- Coordination is the managing of agent interactions in order to support positive and prevent negative effects. 


---
### Partial global planning
	A coordination mechanism proposed by Durfee and Lesser
- There is a **global goal**
- **Local conflicts** between the partial plans are determined
- **Coordination** is achieved by resolving local conflicts, so the global goal can be reached

---
### Norms as system constraints
- Norms have been proposed as a coordination mechanism for AI systems
- Norms can vary in *explicitness* and *bindingness*.
	- Social conventions: e.g. type of clothes in a community
	- Social norms: priority of seats in public transport
	- Legal norms: bike lights
- **system constraints**.
	- A car with built-in speed limitation
	- A can that automatically keeps a distance to other cars
- **Emergent norms**
	- High level pattern arising from low level properties.
	- Example: Agents in a grid environment are blue or red. At each step, they determine their colour at the next step by considering the agents they have met, switching colour depending on the majority.
		Loosely inspired by Shoham and Tennenholz (1992)
 

---
### The nature and roles of norms
#### The nature of norms
- Norms are considered from a descriptive side and from a normative side
- Descriptively, a norm refers to an actual pattern of behaviour 
- Normatively, a norm refers to *a pattern of behaviour* aimed for    
- The *aim* of a norm can be *personal* (vegetarian eating), *social* (being kind) or *institutional* (following the law)

#### Roles of norms.
- Norms guide behaviour (coordination)
- Norms determine meaning (winning a game)
- The meaning-determining role of norms leads to a hierarchy of facts, from physical via conventional to institutional. e.g. signing a contract

---
### Determining norms
- What should the norms be?
- Ethical dilemmas as thought experiment:
	- Do something or do nothing? Doing something and killing one vs doing nothing and killing two.
- **The moral machine experiment (Nature 2018)**
	- Online experimental platform
	- 40 million decisions from millions of people
	- showed *cross-cultural ethical variation*
- Human-in-the-loop: A human controller oversights the actions of AI
- Society-in-the-loop: Societal norms oversight the human in the loop
- *Veil of ignorance*: We should determine societal norms without knowing where we end up in society 

---
### The law as a system of norms
	- The law is a human made system of norms aimed at coordinating society


- The law as a knowledge system (BNA – British Nationality Act)
- The law as a data system (HYPO – HYPOthetical)

- **Problems for machine learning in law**:
	- Machine learning is retrospective
	- Success in law is not statistical
	- Machine learning often does not provide explanations
	- In machine learning we typically need a large datasize
	- Past data may not be homogeneous
	- Past decisions may be simply wrong
	- A legal dispute is often about what rule should be applied

**Rissland 1988 on Gardner 1987**
1. Legal reasoning is rule-guided, rather than rule-governed.
2. Legal terms are open textured.
3. Legal questions can have more than one answer, but a reasonable and timely answer must be given.
4. The answers to legal questions can change over time.

---
# References