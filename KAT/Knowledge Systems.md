22092013:04
Status:  #KAT
Tags: 

# Knowledge Systems

Reasoning types:
- **Forward reasoning**, triggered by input, data driven
- **Backward reasoning**, triggered by goals, goal driven

Kinds of knowledge:
- **[[Descriptive knowledge]]** (knowing that)
- **[[Procedural knowledge]]** (knowing how)

Kinds of reasoning:
- **Theoretical reasoning**
	- Reasoning towards facts
	- uses [[Descriptive knowledge]]
	- **Knowledge system**
- **Practical reasoning**
	- Reasoning towards actions
	- uses [[Procedural knowledge]]
	- **Computational agent**

Defining actions using logic:
- *Precondition list*: facts must be true for the action to be executed
- *Delete list: facts* deleted after preforming the action
- *Add list*: Facts added after performing the action
![[defining_actions.png]]

## Ontologies **[[Ontologies]]** 
	a formal specification of a shared conceptualisation.
- Concrete: concepts and their relations
### Components of ontologies
- **Individuals**: instances, objects, things
- **Classes**: sets of instances, types of objects, kinds of objects
- **Relations**: connections between individuals and classes
- **Properties**: aspects of instances, characteristics of objects, properties of things

### Ontologies for agents:
- **Semantic interoperability** - ontologies provide a shared understanding of a domain
	- Overcome differences in terminology
	- Mappings between ontologies

### Types of ontology
- **Informal ontologies**
	- Glossary
	- Thesaurus
	- Informal is-a taxonomies
- **Formal ontologies**
	- formal is-a taxonomy (Turkish_pizza is-a pizza)
	- properties (edible(muffin))
	- subsumption + properties -> infer properties:
		(Turkish_pizza is-a pizza) and edible(pizza)therefore edible(Turkish_pizza)
### Ontologies on the web
- **Semantic Web**: objects (parts of webpages) have semantic tags and are linked by semantically meaningful links
	- Web of entities / things
	- Ontology underlying the web
	- The relations are linked as *is-about*, *is-a*, *has-a*

## ***[[OWL]]*** - Web Ontology Language



---
# References