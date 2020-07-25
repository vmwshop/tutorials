# Voyant Tutorial

## Objectives

By the end of this tutorial, you should be able to:
Create a default corpus using Voyant
Better understand the basic functions of Voyant



## What You Need
Computer with an internet browser and internet connection
- A dataset 
    - In a file as HTML, MS Word, MS Excel, ODT, Pages (Apple), PDF, plain text, RTF, XML, and others 
    - A zipped folder of multiple files
    - Copy/pasted text
    - A set of URLs, one per line


## About Voyant

Voyant Tools is an open-source, web-based text reading and analysis environment. When you upload or submit text into Voyant, it generates a corpus with a plethora of different tools built right into the program to help you quickly “see through your data,” as the Voyant catchphrase states. 

Voyant has their own very impressive help database that much of this tutorial is based on. Look for it in the references and resources section below. 

## What Can It Be Used For? 

- More thoroughly analyze large (or small) amounts of text or data 
- Add functionality to online collections, journals, blogs, or web sites by providing interactive analysis
- Develop your own tools using Voyant’s functionality and code

## Get Started

Getting started with Voyant is about as easy as it gets. Simply go to **[https://voyant-tools.org/](https://voyant-tools.org/), input your data using one of the available options, and click “Reveal”. 

[[SCREENSHOT]]
1. For this tutorial, copy/paste this URL into the text box: **[https://www.imsdb.com/scripts/Princess-Bride,-The.html](https://www.imsdb.com/scripts/Princess-Bride,-The.html)** then click “Reveal”.

[[SCREENSHOT]]


## Corpus

When Voyant generates a corpus for your data, it automatically shows it using their default skin. In this case, “skin” just refers to which of their tools are displayed. These are customizable based on your needs with a ton of different options, but for this tutorial, we are going to focus on their default skin.

[[SCREENSHOT]]

The tools you will see in the default skin include the following: 

- [Cirrus](linktosection)
- [Summary](linktosection)
- [Trends](linktosection)
- [Contexts](linktosection)
- [Reader](linktosection)

### Cirrus

The top left panel of your corpus shows you a cirrus. This is essentially just a word cloud that sizes a set number of terms from your data based on the frequency in which they appear, displaying the most frequently used words largest. 

[[SCREENSHOT]]

At first glance, you will notice some odd words appearing larger than you might expect from the script of the movie (if you are familiar with it already). For example, the word, “cut” appears larger than any other word in the cirrus. This seems odd given it most likely is not a word used that often in the actual dialog of the film. Upon another quick look at the original link to the script, you will notice that every camera cut is labeled in the script. For our purposes, we don’t need that word associated with our analysis, so let’s remove it. 

1. Hover your mouse over the header of the cirrus block on your screen. You will notice a few buttons appear. Click the icon that looks like a small switch. (it will say “Define options for this tool” when your mouse hovers over it)

[[SCREENSHOT]]

This will reveal the different options for filtering out what Voyant considers functional words like “I”, “the”, “a”, etc. Voyant calls these **“Stopwords”**.

2. To the right of the “Stopwords:” dropdown, click the “Edit List” button.

[[SCREENSHOT]]

3. Here you will see the full list of words that Voyant identified as Stopwords listed one word, number, or symbol per line. On the line directly underneath the last entry of this list, type the word “cut” and click “Save”. Click “Confirm”.

[[SCREENSHOT]]

“Cut” has not been removed from our cirrus.

### Summary

Let’s move down to the Summary tool right underneath the cirrus. This tool is just a simple, brief summary of some of the key elements of our text like the total word count, average words per sentence, and a list and count of the most frequent words in the corpus.

[[SCREENSHOT]]

By default, the summary lists the top 5 most frequent words in your corpus. If you would like to expand that list, click and drag the slider in the bottom left corner of the block labeled “Items:” to your desired number. This increases in increments of 5. 

1. Slide your items slide up to 30. Give Voyant about 30 seconds to catch up, and you will see your list of most frequent words increase.

[[SCREENSHOT]]

2. In your list of most frequent words, click the yellow highlighted word, “westley”. Now take a look at the rest of your corpus. 

[[SCREENSHOT]]

The most obvious change is in the “Trends” block of your corpus. Using the Summary tool, you can select individual words and that will trigger the rest of the tools within the corpus to adjust and show analysis on that specific word. 

### Trends




### Other Resources and References
 
[Voyant Help Database](https://voyant-tools.org/docs/#!/guide/about)
