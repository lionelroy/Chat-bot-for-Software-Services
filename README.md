# Bilingual Chat-bot for Software Services(English/French)


## Technologies used in this built:
	- NLTK(Natural Language Toolkit)
	- Python
	- PyTorch

## Installation

### Create an environment
Whatever you prefer (e.g. `conda` or `venv`)
```console
mkdir myproject
$ cd myproject
$ python3 -m venv venv
```

### Activate it
Mac / Linux:
```console
. venv/bin/activate
```
Windows:
```console
venv\Scripts\activate
```
### Install PyTorch and dependencies

For Installation of PyTorch see [official website](https://pytorch.org/).

You also need `nltk`:
 ```console
pip install nltk
 ```

If you get an error during the first run, you also need to install `nltk.tokenize.punkt`:
Run this once in your terminal:
 ```console
$ python
>>> import nltk
>>> nltk.download('punkt')
```

### Usage
Run
```console
python train.py
```
This will dump `data.pth` file. And then run
```console
python chat.py
```


## 1) Theory + NLP concepts (Stemming, Tokenization, bag of words)

### Training Data(bag of words):

### All Words

["Hi", "How", "are", "you", "bye", "see", "later"]

"Hi" --> [1, 0, 0, 0, 0, 0, 0]                \
"how are you" --> [0, 1, 1, 1, 0, 0, 0]       /             0(greeting)

"Bye" --> [0, 0, 0, 0, 1, 0, 0]               \   
"See you later" --> [0, 0, 0, 1, 0, 1, 1]     /             1(goodbye)

                ^					                            ^
		    X data(model)				                    Y data(label)

---------------------------------------

### This will be implemented as a Feed Forward Neural Network:
X data("Sentence or bag of words", [0, 1, 1, 1, 0, 0, 0]) -----> number of patterns -----> hidden layer -----> hidden layer2 ------> number of classes -----> softmax -----> Y data(result of different probabilities)

---------------------------------------

## NLP basics

### 1st applied concept
Tokenization: splitting a string into meaningful units
(e.g. words, punctuation characters, numbers)
"What would you do with 1000000$?"
-----> ["What", "would", "you", "do", "with", "1000000", "$", "?"]
"Aren't you happy with so much money?"
-----> ["Are", "n't", "you", "happy", "with", "so", "much", "money", "?"]


### 2nd applied concept
Stemming: Generate the root form of the words.
Crude heuristic that chops off the ends off the ends of words
"organize", "organizes", "organizing"
-----> ["organ", "organ", "organ"]
"universe", "university"
-----> ["univers", "univers"]


### 3rd applied concept
NLP Preprocessing Pipeline
"Is anyone there?"

	| tokenize

["Is", "anyone", "there", "?"]

	| lower + stem

["is", "anyon", "there", "?"]

	| exclude punctuation characters

["is", "anyon", "there"]

	| bag of words

X vector data [0, 0, 0, 1, 0, 1, 0, 1]

---------------------------------------

## 2) Create training data
## 3) PyTorch model and training
## 4) Save/load model and implement the chat



# TODO - IMPLEMENT UI FOR CHAT-BOT







"# Chat-bot-for-Software-Services" 
