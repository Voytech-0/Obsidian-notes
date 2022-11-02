22101109:08
Status:  #LanguageAndSpeech
Tags: 

# Lexical semantics - word meaning
Lexical - regarding words
Semantics - meaning 
*sense* - a meaning of a word. A word can have multiple senses
*homonyms* - words with the same form, but unrelated *meaning*
	- *homophones* - same sounds, spelling may differ (male vs mail)
	- *homographs* - same spelling, sound may differ (desert 🏜 vs desert (verb, abandon))

Can *lexical semantic relations* help to identify word meaning?
	Yes, it can!

**Semantic relations**:
- *synonyms*: same / similar meaning
- *antonyms*: opposite in meaning 
- *hypernymy* (supertype) / *hyponymy* (subtype): cat → animal
- *meronymy* (part-of) /  *holonymy* (whole of): car → steering wheel, where car is the holonymy and the steering wheel is a meronymy
- *co-hyponyms* - coordinate terms - cat, dog

Word hierarchy and sense hierarchy can (should) differ

The goal of lexical semantics is to recreate human understanding and interferences

## WordNet
- Ontology of **synsets** - sets of synonyms
- Organised in hierarchical structure
	- ISA - is a - relation. Dog ISA animal. *hyponymy-hypernymy* relation
- 9 starting points:
	1. entity, something  
	2. psychological feature  
	3. abstraction  
	4. state  
	5. event  
	6. act, human action, human activity 
	7. group, grouping  
	8. possession  
	9. phenomenon
- Nouns, verbs, adjectives and adverbs are grouped into sets of **cognitive synonyms**
- WordNet 2.0 added *domains*
### Limitations of WordNet
- The are almost no proper nouns
- There are only a few idiomatic expressions
- Taxonomy planned during production but not thoroughly thought out.
- Depth of taxonomy and coverage uneven and inconsistent
- WordNet may be outdated as it is manually maintained. Words changing over time may be outdated but no longer maintained. 

## Sentiment analysis 
- Negation handling: I do not dislike cabin cruisers
- Adverbial modifies the sentiment: Sometime I really hate ... 
- Possible sarcasm: The weather is sooo goood!
- Dealing with brand names; identifying target of attitude is difficult
- Negative term used in a positive sense in certain domains: The movie is surprising with plenty of <mark style="background: #FFB8EBA6;">unsettling</mark> plot twists
- Qualified positive sentiment, difficult to categorise: I love my mobile but would not recommend it to any of my colleagues 

## SentiWordNet
Sentiment analysis can reach beyond positive and negative emotions: joy, anger, fear, etc.

- NLP task: opinion mining / sentiment classification
- Aims to identify the *opinions* expressed in a text, instead of the topic
	1. **SO-polarity** - subjective (opinion) or objective ()factual description
	2. **PN-polarity** - positive / negative
	3. strength of PN-polarity
	4. Extracting opinions of a text
	![[Pasted image 20221031141846.png|300]]

---

### Bayes Classifier
We need *training data* which is labelled
*Test data* to check how well the classifier works

### Similarity 
Words that share some element of meaning. Car and bicycle are not synonyms, but are similar.
Important component of natural language understanding (paraphrasing, etc.)

### Relatedness
Meaning of two words can be related in other ways than just similarity.
Coffee - tea are similar
Coffee - cup are not similar, but are *related*
Racket - ball are related but are different in many ways

### Antonymy
Senses that are opposite in one aspect of meaning
Different types: 
- Binary opposition
- Opposites ends of a scale
- Reverses

### Connotation
Affective meaning of words

### Computational approach
Defining association with words is difficult and requires manual labour


## Vector semantics
1. Defining meaning by linguistic distribution
2. Meaning as a point in multidimensional space
	- Words are represented by vectors of words (words are features)

### Term-document matrix
- A method of visualising document vectors ![[Pasted image 20221101095352.png|700]]
- Two words are similar in meaning if their context vectors are similar
	- It may indicate that words such as "cherry" and "dessert" are similar
- We can measure similarity by:
	- Euclidean distance: $d(a,b) = \sqrt{\sum_{i=1}^N (a_i - b_i)^2}$
	- By dot product: $a \cdot b = \sum_{i=1}^N a_i b_i$
		- Tends to be high when the two vectors have large values in the same directions 
		- But *dot product* favours long vectors 
	- Cosine similarity $\cos{\theta} = \frac{a \cdot b}{|a| |b|}$

Two common solutions to balancing conflicting constraints:
1. *tf-idf*: $tf_{t,d}$ is term frequency, $idf_t$ is inverse document frequency $$w_{t,d} = tf_{t,d} \times idf_t$$
1. *PMI*: Pointwise mutual information![[Pasted image 20221101100527.png]]

These vectors are *long* (20,000 to 50,000) and *sparse* (most elements are zero)


2 Word2Vec methods:
### SKIPGRAM
The distributed representation of the input word is used to **predict the context**

### CBOW
	Continuous bag of words
The distributed representations of context are combined **to predict the word in the middle**

Advantage:
- We can generalise to unseen words

#### Window size

-  Small windows (C= +/- 2) : nearest words are syntactically similar words in same taxonomy

	-  Hogwarts nearest neighbours are other fictional schools Sunnydale, Evernight, Blandings

-  Large windows (C= +/- 5) : nearest words are related words in same semantic field

	- Hogwarts nearest neighbours are Harry Potter world: Dumbledore, half-blood, Malfoy

# Vector semantics and embeddings 
[[Vector semantics and embeddings]]





---
# References