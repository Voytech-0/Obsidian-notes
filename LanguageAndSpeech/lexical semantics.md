22101109:08
Status:  #LanguageAndSpeech
Tags: 

# Lexical semantics - word meaning
Lexical - regarding words
Semantics - meaning 
*sense* - a meaning of a word. A word can have multiple senses
*homonyms* - words with the same form, but unrelated *meaning*
	- *homophones* - same sounds, spelling may differ(male vs mail)
	- *homographs* - same spelling, sound may differ (desert 🏜 vs desert (abandon))

Can *lexical semantic relations* help to identify word meaning?
	Yes, it can!

**Semantic relations**:
- *synonyms*
- *antonyms*
- hypernymy (supertype) / hyponymy (subtype)*: cat → animal*
- meronymy / holonymy* part-of, whole of: car → steering wheel
- *co-hyponyms* - coordinate terms - cat, dog

Word hierarchy and sense hierarchy can (should) differ



## WordNet
- Ontology of **synsets** - sets of synonyms
- Organised in hierarchical structure
	- ISA - is a - relation. Dog ISA animal
- 9 starting points:
- Nouns, verbs, adjectives and adverbs are grouped into sets of ***sth*
- WordNet 2.0 added domains
- The are almost no proper nouns
- There are only a few idiomatic expressions
- Taxonomy planned during production but not thoroughly thought out.
- WordNet may be outdated as it is manually maintained. Words changing over time may be outdated but no longer maintained. 

## SentiWordNet
Sentiment analysis
- negation handling - I do not dislike sth
- Possible sarcasm
- negative term used in a positive sense in certain domains

- NLP task: opinion mining / sentiment classification
- Aims to identify the *opinions* expressed in a text, instead of the topic
	1. SO-polarity - subjective (opinion) or objective ()factual description
	2. PN-polarity
	3. strength of PN-polarity
	4. Extracting opinions of a text

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

Term-document matrix

Two common solutions:
1. tf-idf
2. PMI: Pointwise mutual information

These vectors are long (20,000 to 50,000) and sparse (most elements are zero)

### SKIPGRAM
The distributed representation of the input word is used to **predict the context**

### CBOW
	Continuous bag of words
The distributed representations of context are combined **to predict the word in the middle**

Advantage:
- We can generalise to unseen words





---
# References