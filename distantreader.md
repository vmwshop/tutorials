# Using the Distant Reader

## Objectives
By the end of this tutorial, you will be able to:
* Identify problems the Distant Reader addresses
* Submit content to the Distant Reader and download results
* Compare some methods for interpreting your downloaded results

## What You Need
* Computer with a web browser and internet connection
* Text editor - Any will do, but here are some good options:
  * Windows - [Notepad++](https://notepad-plus-plus.org/downloads/), [Sublime Text](https://www.sublimetext.com/3)
  * Mac - [BBedit](https://www.barebones.com/products/bbedit/download.html), [Sublime Text](https://www.sublimetext.com/3), [Atom](https://atom.io/)
* Spreadsheet application (Microsoft Excel or Macintosh Numbers work just fine)
* A dataset (We will be using datasets from the [Western Pennsylvania Regional Data Center](http://www.wprdc.org/))

## About the Distant Reader

_Distant reading_ generally refers to the use of computational methods to analyze literary texts. Created by Eric Lease Morgan at the University of Notre Dame, the [Distant Reader](https://distantreader.org/) is a web-based text analysis toolset for “reading” and analyzing texts. It takes unstructured data (text) as input, and it outputs sets of structured data for analysis. The Distant Reader is intended to supplement the traditional reading process by simplifying the process of identifying trends and anomalies in large volumes of text. It is also a method for pre-processing data to be used in natural language processing. 

Much of the following is adapted from Eric Lease Morgan’s documentation on the Distant Reader tool. See the references section of this tutorial for links to these resources. 

## What We Can Do With the Distant Reader

Designed to “read” everything from a single item to a large corpus, the Distant Reader can help answer questions like: 
* How big is the corpus, and how does its size compare to other corpora?
* How difficult (scholarly) is the corpus?
* What words or phrases are used frequently and infrequently?
* What statistically significant words characterize the corpus?
* Are there latent themes in the corpus, and if so, then what are they and how do they change over both time and place?
* How do any latent themes compare to basic characteristics of each item in the corpus (author, genre, date, type, location, etc.)?
* What is discussed in the corpus (nouns)?
* What actions take place in the corpus (verbs)?
* How are those things and actions described (adjectives and adverbs)?
* What is the tone or “sentiment” of the corpus?
* How are the things represented by nouns, verbs, and adjective related?
* Who is mentioned in the corpus, how frequently, and where?
* What places are mentioned in the corpus, how frequently, and where?

### How the Distant Reader Works

The Distant Reader is a system which locally harvests/caches content you specify. It then transforms the content into plain text, performs sets of natural language processing & text mining against the text, saves the results in a number of formats, reduces the whole to a cross-platform database file, queries the database thus summarizing the collection, zips the results of the entire process into a single file, and makes the file available to you for further investigation.

