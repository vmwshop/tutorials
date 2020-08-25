# Natural Language Processing with spaCy

## Objectives
By the end of this tutorial, you will be able to:

* Understand what spaCy is (and what it isn’t)
* ADD STUFF HERE

## What You Need
* Computer with a web browser and internet connection
* Experience working from the command line
* Experience with Python is not necessary for this tutorial, but basic working knowledge is recommended


## About spaCy
spaCy is a free, open-source library for advanced Natural Language Processing (NLP) in Python. If you’re working with a lot of text, you’ll eventually want to know more about it. For example, what’s it about? What do the words mean in context? Who is doing what to whom? What companies and products are mentioned? Which texts are similar to each other?

spaCy is designed specifically for production use and helps you build applications that process and “understand” large volumes of text. It can be used to build information extraction or natural language understanding systems, or to pre-process text for deep learning.

spaCy is not a platform or an API. Unlike a platform, spaCy does not provide a software as a service, or a web application. It’s an open-source library designed to help you build NLP applications, not a consumable service. Unlike [NLTK](https://github.com/nltk/nltk) or [Core NLP](https://stanfordnlp.github.io/CoreNLP/) which were designed for teaching and research, spaCy is not research software. This means that spaCy is integrated and opinionated. spaCy avoids asking the user to choose between multiple algorithms that deliver equivalent functionality. Instead, the menu is small and 

_Much of the following is adapted from the spaCy Usage documentation. See the references section of this tutorial for links to this and other resources._ 

### spaCy Features

Name | Description
------------ | -------------
Tokenization | Segmenting text into words, punctuations marks etc
Part-of-speech (POS) Tagging | Assigning word types to tokens, like verb or noun
Dependency Parsing | Assigning syntactic dependency labels, describing the relations between individual tokens, like subject or object
Lemmatization | Assigning the base forms of words. For example, the lemma of “was” is “be”, and the lemma of “rats” is “rat”
Sentence Boundary Detection (SBD) | Finding and segmenting individual sentences
Named Entity Recognition (NER) | Labelling named “real-world” objects, like persons, companies or locations
Entity Linking (EL) | Disambiguating textual entities to unique identifiers in a Knowledge Base
Similarity | Comparing words, text spans and documents and how similar they are to each other
Text Classification | Assigning categories or labels to a whole document, or parts of a document
Rule-based Matching | Finding sequences of tokens based on their texts and linguistic annotations, similar to regular expressions
Training | Updating and improving a statistical model’s predictions
Serialization | Saving objects to files or byte strings

### Feature Comparison
Natural Language Understanding is an active area of research and development, so there are many different tools or technologies catering to different use-cases. The table below summarizes a few libraries to help you get a feel of which to use for what.

 Use | spaCy | NLTK | AllenNLP | StanfordNLP | TensorFlow
 ------------ | ------------- | ------------- | ------------- | ------------- | -------------
 I’m a beginner and just getting started with NLP | :white_check_mark: | :white_check_mark: | :x: | :white_check_mark: | :x:
 I want to build an end-to-end production application | :white_check_mark: | :x: | :x: | :x: | :white_check_mark:
 I want to try out different neural network architectures for NLP | :x: | :x: | :white_check_mark: | :x: | :white_check_mark:
 I want to try the latest models with state-of-the-art accuracy | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark:
 I want to train models from my own data | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark:
 I want my application to be efficient on CPU | :white_check_mark: | :white_check_mark: | :x: | :x: | :x:

## Getting Started

### Python and pip
spaCy is compatible with 64-bit CPython 2.7 / 3.5+ and runs on Unix/Linux, macOS/OS X and Windows. The latest spaCy releases are available over pip and conda. The following installation instructions will use Python and pip. For information on installing and working with [Python](https://www.python.org/) and the [pip  package-management system](https://pypi.org/project/pip/), see these resources:
* [Python Setup and Usage](https://docs.python.org/3/using/index.html)
* [Do I Need to Install pip?](https://pip.pypa.io/en/stable/installing/)
* On a Mac, simply type `python3` in your terminal. If not already installed, you will be prompted to install "Command Line Tools" via XCode. Agree to installation and you should be all set. 

For more detailed information and varied options see the [spaCy Installation Guide](https://spacy.io/usage#installation)

### Installing spaCy and Downloading Statistical Model (English model)
1. Navigate to the terminal. 
> * To open the terminal in Linux, press Ctrl+Alt+T in Ubuntu, or press Alt+F2, type in gnome-terminal, and press enter. In Raspberry Pi, type in lxterminal
> * To open the terminal in MacOS, either open your Applications folder, then open Utilities and double-click on Terminal, or press Command - spacebar to launch Spotlight and type "Terminal," then double-click the search result.
> * To open the command prompt in Windows, press Windows+R to open “Run” box, then type “cmd” and then click “OK” to open a regular Command Prompt. Type “cmd” and then press Ctrl+Shift+Enter to open an administrator Command Prompt.
2. Install spaCy in a virtual environment by running the following commands.
> When using pip it is generally recommended to install packages in a virtual environment to avoid modifying system state. The first two commands here set up a virtual environment and the third installs spaCy in that environment.
> * Do not copy the `$`. This character signifies the beginning of a command line prompt. So, commit each separate `$` as a separate prompt (i.e. hit return/enter to run each line before moving to the next `$`).

**MacOS/Linux**
```
$ python -m venv .env
$ source .env/bin/activate
$ pip install -U spacy
```
**MacOS/Linux with Python3 and pip3** 
> If you try the previous commands and nothing returns, try these instead. They go straight to the latest version of python and pip. If these work, remember to add use `python3` and `pip3` for all future commands where you see `python` or `pip`, too!
```
$ python3 -m venv .env
$ source .env/bin/activate
$ pip3 install spacy
```
**Windows**
```
$ python -m venv .env
$ .env\Scripts\activate
$ pip install spacy
```
3. Download core statistical model by running the following command.
> While some of spaCy’s features work independently, others require statistical models to be loaded, which enable spaCy to predict linguistic annotations.spaCy core models are general-purpose pretrained models to predict named entities, part-of-speech tags and syntactic dependencies, which can be used out-of-the-box and fine-tuned on more specific data.

> As our input will be in English, this is the download for the core English model-- _other models available [here](https://spacy.io/usage/models)_

**MacOS/Linux** 
> Don't forget to use `python3` and `pip3` if that worked for you in Step 2. 
```
$ python -m spacy download en_core_web_sm
```
**Windows**
```
$ python -m spacy download en_core_web_sm
```
## Working with spaCy
### Pre-Processing Text String
The first step for working with spaCy is to pass it to an NLP object. This object is essentially a pipeline of several text pre-processing operations through which the input text string has to go through. The NLP pipeline has multiple components, such as tokenizer, tagger, parser, ner, etc. So, the input text string has to go through all these components before we can work on it.

1. Open a python interactive shell/interpreter by simply typing `python` or `python3` (depending on what worked for you earlier) in your terminal. You should now see `>>>` at the beginning of your prompts. This means you are now running your code in a python shell.
2. Import spaCy and load model installed earlier. This will return a language object, called an NLP, containing all components and data needed to process text.
```
>>> import spacy
>>> nlp = spacy.load("en_core_web_sm")
```
3. Process a string of text through the nlp to create a `doc` (an object split into individual words and annotated). This tutorial uses sample text, but feel free to use a text string of your choice between the double quotation marks.
```
>>> doc = nlp(“The work we do in the VMW is designed to be as self-reflexive as possible, using agile and iterative approaches to our humanities research in order to refine questions and respond productively to new findings and realizations”)
```



