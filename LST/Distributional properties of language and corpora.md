22100409:03
Status:  #LanguageAndSpeech
Tags: 

# Corpus
A collection of texts with some **unifying characteristics** (functional for language analysis)

Corpora uses:
- *Applicative*: develop NLP tools
- *Analytic*: Empirical basis on the distribution of constrictions and language phenomena 

Classifying corpora:
- *Mode*: written vs spoken vs multimedia vs mixed
- *Representative*: balanced / reference vs specialised / opportunistic 
- Time: *diachronic* vs *synchronic*
	- Diachronic: Sorted by time of creation ex. written in the 50s
	- Synchronic more consistent. Ex. collected within 10 years
- Language: *monolingual* vs multilingual vs parallel vs comparable 
- *Sampling*: full documents / transcriptions vs sample of documents / transcriptions
- *Mark-up*: 'raw' vs annotated

**Balanced corpus**:
- Collection of texts / documents / speeches:
	- Big in size
	- mixed: (should) contain written and spoke language
	- full texts / documents
	- include different domains and genres
	- cover a range of text categories
	- well documented

- ***Brown corpus***:
	- First big corpus ever created (around million words)
	- Balanced: different types and different styles
		- Consulted publication catalogues
		- Consulted library statistics about what was loaned
		- Only original English texts
	- Copyright has to be obtained for redistribution
		- It influences the use of the corpus
	- Limitation: Only published texts

Other corpora:
- SUC - Stockholm-Umea Corpus of Swedish
- BNC – British National Corpus

**Parallel corpora**:
- Original text and a translation, linked with another
	- Sentence level or word level
- EUROPARL is the most famous of parallel corpora

**Dynamic corpora**:
- New texts added continuously
- Useful for *diachronic studies*
- Example:
- COCA - Corpus of Contemporary American English
	- 560 million words
- Twitter corpora: TwiSty
- Wikipedia 
- Messaging and group chats

**Treebank**:
- Corpus with linguistic annotation beyond word level
- Manually checked syntactic annotation
- They are supposed to be the gold standards for other applications 
- *Penn Treebank* is a collection of four corpora: BrownCorpus, WallStreetJournalCorpus, SwitchboardCorpus, ASTISCorpus

**Text archives**:
- Databases of texts:
	- May not have been produced in a natural setting
	- Often have not been compiled for the purposes of linguistic analysis
	- Often have not been intended to be representative with a particular linguistic variety or speech community
	- Large quantities of data


# Distributional properties of language 
## Regular expressions
RegEx can be used to search for patterns. 

**Tokens**: statistical units (basic units) of study
	Each token is a distinct word

**Lexicon:**;
- The set of all the possible words of a target language
- The set of all the words known by a speaker
**Vocabulary:**
- Number of *types* (distinct word units) in the corpus
**Dictionary**
- the repository of lemmas and inflected forms (tokens) of a specific language which has been selected for a specific goal/purpose

**Frequency**

**Frequency class**: Class of frequency of words
- The set of type which have frequency i
- $V_1$ = the set of all types with frequency 1
- **Hapax Legomena** is a set of $V_1$. It makes 45% of tokens
- 70% of types occurs less than four times.
- Types occurring less than four times make up only 11% of all tokens.
- **cumulative frequencies**

**Type-Token Ratio** – **TTR** 
	The type-token ratio (TTR) is a measure of vocabulary variation within a written text or a person’s speech. The type-token ratios of two real world examples are calculated and interpreted. The type-token ratio is shown to be a helpful measure of lexical variety within a text. It can be used to monitor changes in children and adults with vocabulary difficulties.

**Zipf distribution**  
	Progressive reduction of a word, proportional to the increase of its rank (lower in rank ~ less frequent)
- Word of rank 3 should occur 1/3 of the time of word of rank 1 and so on


---
# References