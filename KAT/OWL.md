22092013:44
Status:  #KAT
Tags: 

---
**Web Ontology Language** - OWL
	
Owl has two types of properties:
- *Object Properties*: Relate object to other objects.
- *Data type properties*: Relate objects to datatype values.

**owl:Thing** includes everything
**owl:Nothing** is an empty class
## Class restriction
- Class (Plant partial owl:Thing)
- SubClassOf(Tree Plant)
- DisjointClasses(Plant Animal)

## Properties of OWL
### Object properties
	Relate objects to other objects
- **ObjectProperty**
```
	<owl:ObjectProperty rdf:ID="husband">
	  <rdf:type    rdf:resource="&owl;FunctionalProperty" />
	  <rdfs:domain rdf:resource="#Woman" />
	  <rdfs:range  rdf:resource="#Man" />
	</owl:ObjectProperty>
```
- **Data type properties**, which relate objects to datatype values
	- DataProperty(age range(nonNegativeInteger))

### Individuals
- Individual("Oak" type(Tree))
- Individual(“Butcher’s Crossing” type(Novel) value(author “John Williams”))
- SameIndividual("A" "B")
- DifferentIndividual("A" "B")

---
It consists of three sublanguages:
## OWL Full
› It uses all the OWL language primitives
› It allows the combination of these primitives in arbitrary ways with RDF and RDF Schema
› OWL Full is fully upward-compatible with RDF, both syntactically and semantically
› OWL Full is so powerful that it is undecidable 
	▪ No complete reasoning support

## OWL DL (Descriptive Logic)
› OWL DL (Description Logic) is a sublanguage of OWL Full that restricts application of the constructors from OWL and RDF
-   ▪  Application of OWL’s constructors’ to each other is disallowed
-   ▪  Therefore it corresponds to a well studied description logic
› OWL DL permits efficient reasoning support
› But we lose full compatibility with RDF: 
	- Not every RDF document is a legal OWL DL document. 
	- Every legal OWL DL document is a legal RDF document.

## OWL Lite
An even further restriction limits OWL DL to a subset of the language constructors
E.g., OWL Lite excludes enumerated classes, disjointness statements, and arbitrary cardinality.
The advantage of this is a language that is easier to
- grasp, for users
- implement, for tool builders
The disadvantage is restricted expressivity


---
# References