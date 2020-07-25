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

<img src="https://user-images.githubusercontent.com/15221098/88464255-3a2a9f00-ce87-11ea-859f-ae463f1cd94a.png" class="responsive" alt="voyantgetstarted1" width="850">

1. For this tutorial, copy/paste this URL into the text box: **[https://www.imsdb.com/scripts/Princess-Bride,-The.html](https://www.imsdb.com/scripts/Princess-Bride,-The.html)** then click “Reveal”.


## Corpus

When Voyant generates a corpus for your data, it automatically shows it using their default skin. In this case, “skin” just refers to which of their tools are displayed. These are customizable based on your needs with a ton of different options, but for this tutorial, we are going to focus on their default skin.

<img src="https://user-images.githubusercontent.com/15221098/88464310-9b527280-ce87-11ea-8b3a-11d20f464607.png" class="responsive" alt="voyantcorpus" width="850">

The tools you will see in the default skin include the following: 

- [Cirrus](linktosection)
- [Summary](linktosection)
- [Trends](linktosection)
- [Contexts](linktosection)
- [Reader](linktosection)

### Cirrus

The top left panel of your corpus shows you a cirrus. This is essentially just a word cloud that sizes a set number of terms from your data based on the frequency in which they appear, displaying the most frequently used words largest. 

<img src="https://user-images.githubusercontent.com/15221098/88464334-c0df7c00-ce87-11ea-8e41-7b512d694617.png" class="responsive" alt="voyantcirrus1">

At first glance, you will notice some odd words appearing larger than you might expect from the script of the movie (if you are familiar with it already). For example, the word, “cut” appears larger than any other word in the cirrus. This seems odd given it most likely is not a word used that often in the actual dialog of the film. Upon another quick look at the original link to the script, you will notice that every camera cut is labeled in the script. For our purposes, we don’t need that word associated with our analysis, so let’s remove it. 

1. Hover your mouse over the header of the cirrus block on your screen. You will notice a few buttons appear. Click the icon that looks like a small switch. (it will say “Define options for this tool” when your mouse hovers over it)

<img src="https://user-images.githubusercontent.com/15221098/88464342-d2c11f00-ce87-11ea-8a57-732f7be3dfc0.png" class="responsive" alt="voyantcirrus2">

This will reveal the different options for filtering out what Voyant considers functional words like “I”, “the”, “a”, etc. Voyant calls these **“Stopwords”**.

2. To the right of the “Stopwords:” dropdown, click the “Edit List” button.

<img src="https://user-images.githubusercontent.com/15221098/88464350-f1bfb100-ce87-11ea-9529-321130b1dfc0.png" class="responsive" alt="voyantcirrus3">

3. Here you will see the full list of words that Voyant identified as Stopwords listed one word, number, or symbol per line. On the line directly underneath the last entry of this list, type the word “cut” and click “Save”. Click “Confirm”.

<img src="https://user-images.githubusercontent.com/15221098/88464355-ff753680-ce87-11ea-8a7f-6bc8331407ea.png" class="responsive" alt="voyantcirrus4">

“Cut” has now been removed from our cirrus.

### Summary

Let’s move down to the Summary tool right underneath the cirrus. This tool is just a simple, brief summary of some of the key elements of our text like the total word count, average words per sentence, and a list and count of the most frequent words in the corpus.

<img src="https://user-images.githubusercontent.com/15221098/88464380-34818900-ce88-11ea-8e2b-e43d5da0931f.png" class="responsive" alt="voyantsummary1">

By default, the summary lists the top 5 most frequent words in your corpus. If you would like to expand that list, click and drag the slider in the bottom left corner of the block labeled “Items:” to your desired number. This increases in increments of 5. 

1. Slide your items slide up to 30. Give Voyant about 30 seconds to catch up, and you will see your list of most frequent words increase.

<img src="https://user-images.githubusercontent.com/15221098/88464399-685cae80-ce88-11ea-8647-e17a5535b566.png" class="responsive" alt="voyantsummary2">

2. In your list of most frequent words, click the yellow highlighted word, “westley”. Now take a look at the rest of your corpus. 

<img src="https://user-images.githubusercontent.com/15221098/88464413-862a1380-ce88-11ea-9af6-58f026134191.png" class="responsive" alt="voyantsummary3">

The most obvious change is in the “Trends” block of your corpus. Using the Summary tool, you can select individual words and that will trigger the rest of the tools within the corpus to adjust and show analysis on that specific word. 

### Trends

The Trends tool shows you a line graph of the frequency of a selected word in your corpus. 

<img src="https://user-images.githubusercontent.com/15221098/88464427-a2c64b80-ce88-11ea-9d14-91eb6eed97f0.png" class="responsive" alt="voyanttrends1">

> (This is the default view from the beginning of this tutorial. Yours will look a little different right now if you’ve been following along.)

Since we selected “westley” from our Summary tool, you should just see one line on your Trends graph. If you’re familiar with the movie (spoiler ahead if you haven’t seen it), “The Princess Bride,” you will know that the character, Westley is actually The Man In Black at the beginning of the movie. With our Trends tool, we can visually show when that change occurs by using the search syntax to add a line for The Man In Black.

1. Click within the search bar at the bottom of the Trends block and select the term “westley” from the list that appears. Even though we have the term selected from our Summary tool already, we need to select it again here to make sure we get the results we’re looking for.

<img src="https://user-images.githubusercontent.com/15221098/88464442-bd98c000-ce88-11ea-8c32-f033af8f4992.png" class="responsive" alt="voyanttrends2">

2. In the search bar at the bottom of the Trends block, hover your mouse over the “?” symbol to reveal a cheat sheet of search syntaxes. 

<img src="https://user-images.githubusercontent.com/15221098/88464453-cdb09f80-ce88-11ea-9387-0cf357425802.png" class="responsive" alt="voyanttrends3">

> This little pop up only lasts for a few seconds. Click the “?” symbol to open a static lightbox version of the cheat sheet.

3. Based on this cheat sheet, if we want Voyant to search for “man in black” as a single term, all we need to do is surround those three words in quotation marks when we type them into the search bar. Do that and press your Enter key.

<img src="https://user-images.githubusercontent.com/15221098/88464459-de611580-ce88-11ea-8130-bc5a951f0421.png" class="responsive" alt="voyanttrends4">

> After you press the Enter key, you might see a random word pop into your search bar. Just click the little “x” next to that word to remove it. 

Now our line graph shows lines for each term and we can visually see the point in the story when The Man In Black is revealed to actually be Westley! (What a twist!)

4. In the bottom right corner of the Trends block, click on the “Display” dropdown. Here you can change the appearance of the graph. To really illustrate our point here, click the “Area” option from the list to change it to an area graph of solid colors. 

<img src="https://user-images.githubusercontent.com/15221098/88464468-f5a00300-ce88-11ea-8a15-fc4d1edde129.png" class="responsive" alt="voyanttrends5">
  

### Reader
The Reader tool displays the text from your corpus with some useful features for quickly finding information on a word while showing it in the context of the rest of the text. 

[[SCREENSHOT]]

1. Hover over a few words. This displays the total count of that word.

[[SCREENSHOT]]

2. The search bar also functions in the same way as the search bar in the Trends tool. However, in Reader, it highlights the searched word or term and displays a small, simple line graph to illustrate that word or term’s frequency throughout the text. Click within the search bar and select the word “humperdinck”. You will notice the line graph shift. You can also click on the line graph itself to jump to a part of the text that has a higher frequency of your searched word or term. 

[[SCREENSHOT]]

### Contexts

The Contexts tool is a great way to get a snapshot of exactly what it’s called, the context of a word in your text. It shows a list of each occurrence of the selected word and a few words that appear on either side of that occurrence. 

[[SCREENSHOT]]

1.  By default, Voyant selects the word with the highest frequency from your corpus in the Contexts block. For this example, let’s pick something else. Selecting a new word for the Contexts tool can be done a couple of ways: 

Click the word in the Reader block
Click a data point from the line graph in the Trends block
Using the search bar at the bottom of the Contexts block

However you want to get there, select the word “fezzik”.

[[SCREENSHOT]] 

2. Take a look down the list of the occurrences of “fezzick”. Each line of the table shows each individual occurrence of the word with one column showing the text on the left side of the word and another column showing the text that appears to the right of the word. Click the first line of the table and notice how the blocks for the Reader and Trends tools both change to help elaborate on the context of that occurrence of the word. 

[[SCREENSHOT]]

3. To add additional terms to your Contexts tool, use the search bar by either clicking and selecting a word or by typing in a word or phrase using Voyant’s search syntax. You can find a cheat sheet for the syntax again by clicking the little “?” symbol on the right end of the search bar. For this example, add “inigo” since he and Fezzik are together for most of the movie. 

[[SCREENSHOT]]

Adding multiple terms to your Contexts tool allows you to get a bird’s eye view of any consistencies in the contexts of different terms!

## Exporting and Embedding your Corpus

One of the beauties of Voyant is the ability to not only export your corpus but also embed it into an online collection, article, or webpage. This adds new depth to your data or research and allows readers to interact with it. 

1. Hover your mouse over the blue header at the top of your browser window to expose four icons. Click on the icon that is a rounded rectangle with an arrow sticking diagonally out of it.

[[SCREENSHOT]]

2. You are provided with a few different options here. The default is a URL that, when clicked, will populate your corpus in the exact condition that is at the time of click the “Export” button. If you select this option, Voyant will open that URL in a new tab and you can copy it from there. To find additional options, click the “Export View (Tools and Data)” dropdown to expose the following options:

[[SCREENSHOT]]


## Other Tips and Tricks

### Resize Your Tool Blocks

If you need to expand or contract the blocks of any of the tools displayed in your corpus, just hover your mouse over the border of the block until you see the resize icon then click and drag it to your desired size. 

[[SCREENSHOT]]

### Changing Your Blocks to Other Tools

We only showed you 5 of the tools available for your corpus. To change one of your blocks, hover over the gray header area of the block you want to change and click the icon with four small rectangles.

[[SCREENSHOT]]

Check out Voyant’s help database (linked below) to explore all of their available tools! 


## Other Resources and References
 
**[Voyant Help Database](https://voyant-tools.org/docs/#!/guide/about)**

