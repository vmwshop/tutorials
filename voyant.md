# Reading and Analyzing Text with Voyant

## Objectives
By the end of this tutorial, you will be able to:
* Understand the basic functions of Voyant
* Create a corpus using Voyant

## What You Need
* Computer with an internet browser and internet connection
* A text-based dataset, which can be:
    * A single file - HTML, MS Word, MS Excel, ODT, Pages, PDF, plain text, RTF, XML will work
    * A zipped folder of multiple files
    * Copy/pasted text
    * A set of URLs, one per line

## About Voyant
[Voyant Tools]((https://voyant-tools.org/)) is an open-source, web-based text reading and analysis environment. When you upload or submit text into Voyant, it generates a corpus with a plethora of different tools built right into the program to help you quickly “see through your data,” as the Voyant catchphrase states. 

_This tutorial is adapted from documentation found in the Voyant help database. See the references and resources section below for a link to the database._

## What We Can Do With Voyant
* More thoroughly analyze large (or small) amounts of text or data
* Create graphic visualizations of textual data
* Add functionality to online collections, journals, blogs, or web sites by providing interactive analysis
* Develop your own tools using Voyant’s functionality and code

## Getting Started
1. Using your web browser, navigate to [https://voyant-tools.org/](https://voyant-tools.org/).
2. Input your data using one of the available options (text or URLs). For this tutorial, copy/paste this URL into the text box: [https://www.imsdb.com/scripts/Princess-Bride,-The.html](https://www.imsdb.com/scripts/Princess-Bride,-The.html).
3. Select "reveal".
<img src="https://user-images.githubusercontent.com/15221098/88464255-3a2a9f00-ce87-11ea-859f-ae463f1cd94a.png" class="responsive" alt="voyantgetstarted1" width="850" style="vertical-align:middle;margin:20px 0px">

## Exploring Your Voyant Corpus
When Voyant generates a corpus for your data, it automatically shows it using their default skin. In this case, “skin” refers to which tools are displayed. These are customizable based on your needs. For this tutorial, we are going to use the default skin. Let's explore what we can do with these tools one-by-one.

<img src="https://user-images.githubusercontent.com/15221098/88464310-9b527280-ce87-11ea-8b3a-11d20f464607.png" class="responsive" alt="voyantcorpus" width="850" style="vertical-align:middle;margin:20px 0px">


### Cirrus
The top left panel of your corpus shows you a cirrus. This is essentially a word cloud that sizes a set number of terms from your data based on the frequency in which they appear, displaying the most frequently used words as the largest. 

<img src="https://user-images.githubusercontent.com/15221098/88464334-c0df7c00-ce87-11ea-8e41-7b512d694617.png" class="responsive" alt="voyantcirrus1" style="vertical-align:middle;margin:20px 0px">

At first glance, you may notice some odd words appearing larger than you might expect from the script of the movie (if you are familiar with it already). For example, the word, “cut” appears larger than any other word in the cirrus. This seems odd given it most likely is not a word used that often in the actual dialog of the film. Upon another quick look at the original link to the script, you will notice that every camera cut is labeled in the script. For our purposes, we don’t need that word associated with our analysis, so let’s remove it. 

1. Hover your mouse over the header of the cirrus block on your screen. You will notice a few buttons appear. Click the icon that looks like a small switch to “define options for this tool.” This will reveal the different options for filtering out function words and stopwords like “I”, “the”, “a”, etc. <img src="https://user-images.githubusercontent.com/15221098/88464342-d2c11f00-ce87-11ea-8a57-732f7be3dfc0.png" class="responsive" alt="voyantcirrus2" style="vertical-align:middle;margin:20px 0px">
2. To the right of the “Stopwords” dropdown, click the “Edit List” button. <img src="https://user-images.githubusercontent.com/15221098/88464350-f1bfb100-ce87-11ea-9529-321130b1dfc0.png" class="responsive" alt="voyantcirrus3" style="vertical-align:middle;margin:20px 0px">
3. Here you will see the full list of words that Voyant identified as stopwords listed one word, number, or symbol per line. On the line directly underneath the last entry of this list, type the word “cut” and click “Save”. Click “Confirm”. “Cut” has now been removed from our cirrus. <img src="https://user-images.githubusercontent.com/15221098/88464355-ff753680-ce87-11ea-8a7f-6bc8331407ea.png" class="responsive" alt="voyantcirrus4" style="vertical-align:middle;margin:20px 0px">


### Summary

Let’s move down to the Summary tool right underneath the cirrus. This tool is a brief summary of some of the key elements in our text like the total word count, average words per sentence, and a list and count of the most frequent words in the corpus.

<img src="https://user-images.githubusercontent.com/15221098/88464380-34818900-ce88-11ea-8e2b-e43d5da0931f.png" class="responsive" alt="voyantsummary1" style="vertical-align:middle;margin:20px 0px">

By default, the summary lists the top 5 most frequent words in your corpus. Let's exapnd that list. 

1. Click and drag the slider in the bottom left corner of the block labeled “Items” to your desired number. This increases in increments of 5. 
2. Slide your items slide up to 30. Give Voyant about 30 seconds to catch up, and you will see your list of most frequent words increase. <img src="https://user-images.githubusercontent.com/15221098/88464399-685cae80-ce88-11ea-8647-e17a5535b566.png" class="responsive" alt="voyantsummary2" style="vertical-align:middle;margin:20px 0px">
3. In your list of most frequent words, take turns selecting the yellow highlighted words. Now take a look what this selection does to the rest of your corpus. Using the Summary tool, you can select individual words and that will trigger the rest of the tools within the corpus to adjust and show analysis on that specific word. The most obvious change in this case is the “Trends” block of your corpus. 
<img src="https://user-images.githubusercontent.com/15221098/88464413-862a1380-ce88-11ea-9af6-58f026134191.png" class="responsive" alt="voyantsummary3" style="vertical-align:middle;margin:20px 0px">


### Trends

The Trends tool shows you a line graph of the frequency of a selected word in your corpus. 

<img src="https://user-images.githubusercontent.com/15221098/88464427-a2c64b80-ce88-11ea-9d14-91eb6eed97f0.png" class="responsive" alt="voyanttrends1" style="vertical-align:middle;margin:20px 0px">

> (This is the default view from the beginning of this tutorial. Yours will look a little different right now if you have been following along.)

1. Select “westley” in the Summary tool. You should now just see one line on your Trends graph. If you’re familiar with the movie (**spoiler alert**), you will know that Westley is actually also the Man in Black mentioned frequently in the first third of the movie. With our Trends tool, we can visually show when Westley leaves the picture, becomes the Man in Black, and is then eventually realized to be Westley by using the search syntax to add a line for the Man in Black.
2. Click within the search bar at the bottom of the Trends block and select the term “westley” from the list that appears. Even though we have the term selected from our Summary tool already, we need to select it again here to make sure we get the results we are looking for. <img src="https://user-images.githubusercontent.com/15221098/88464442-bd98c000-ce88-11ea-8c32-f033af8f4992.png" class="responsive" alt="voyanttrends2" style="vertical-align:middle;margin:20px 0px">
3. In the search bar at the bottom of the Trends block, hover your mouse over the “?” symbol to reveal a cheat sheet of search syntaxes. <img src="https://user-images.githubusercontent.com/15221098/88464453-cdb09f80-ce88-11ea-9387-0cf357425802.png" class="responsive" alt="voyanttrends3" style="vertical-align:middle;margin:20px 0px">
> This little pop up only lasts for a few seconds. Click the “?” symbol to open a static lightbox version of the cheat sheet.
4. Based on this cheat sheet, if we want Voyant to search for “man in black” as a single term, all we need to do is surround those three words in quotation marks when we type them into the search bar. Now our line graph shows lines for each term and we can visually see the point in the story when The Man In Black is revealed to actually be Westley! (What a twist!) <img src="https://user-images.githubusercontent.com/15221098/88464459-de611580-ce88-11ea-8130-bc5a951f0421.png" class="responsive" alt="voyanttrends4" style="vertical-align:middle;margin:20px 0px">
> After you press the Enter key, you might see a random word pop into your search bar. Just click the little “x” next to that word to remove it. 
5. In the bottom right corner of the Trends block, click on the “Display” dropdown. Here you can change the appearance of the graph. 
<img src="https://user-images.githubusercontent.com/15221098/88464468-f5a00300-ce88-11ea-8a15-fc4d1edde129.png" class="responsive" alt="voyanttrends5" style="vertical-align:middle;margin:20px 0px">
  

### Reader
The Reader tool displays the text from your corpus with some useful features for quickly finding information on a word while showing it in the context of the rest of the text. 

<img src="https://user-images.githubusercontent.com/15221098/88464560-c5a52f80-ce89-11ea-9421-6a7e85f2f21e.png" class="responsive" alt="voyantreader1" style="vertical-align:middle;margin:20px 0px">

1. Hover over a few words. The hover text displays the total count of that word. <img src="https://user-images.githubusercontent.com/15221098/88464569-e077a400-ce89-11ea-8516-bd9a0b09acc5.png" class="responsive" alt="voyantreader2" style="vertical-align:middle;margin:20px 0px">

2. The search bar also functions in the same way as the search bar in the Trends tool. However, in Reader, it highlights the searched word or term and displays a small, simple line graph to illustrate that word or term’s frequency throughout the text. Click within the search bar and select the word “humperdinck”. You will notice the line graph shift. You can also click on the line graph itself to jump to a part of the text that has a higher frequency of your searched word or term. 
<img src="https://user-images.githubusercontent.com/15221098/88464574-ec636600-ce89-11ea-9d0f-3c9992da119b.png" class="responsive" alt="voyantreader3" style="vertical-align:middle;margin:20px 0px">

### Contexts

The Contexts tool shows each occurrence of a keyword with a bit of surrounding text (the context). It can be useful for studying more closely how terms are used in different contexts. 

<img src="https://user-images.githubusercontent.com/15221098/88464607-33e9f200-ce8a-11ea-84dc-df7e3b839917.png" class="responsive" alt="voyantcontexts1" style="vertical-align:middle;margin:20px 0px">

1. By default, Voyant selects the word with the highest frequency from your corpus in the Contexts block. <img src="https://user-images.githubusercontent.com/15221098/88464617-51b75700-ce8a-11ea-99d6-df358cefe24a.png" class="responsive" alt="voyantcontexts2" style="vertical-align:middle;margin:20px 0px">
>Selecting a new word for the Contexts tool can be done a couple of ways: 
> - Click the word in the Reader block
> - Click a data point from the line graph in the Trends block
> - Using the search bar at the bottom of the Contexts block
2. However you want to get there, select the word “fezzik”. Take a look down the list of the occurrences of “fezzick”. Each line of the table shows each individual occurrence of the word with one column showing the text on the left side of the word and another column showing the text that appears to the right of the word. Click the first line of the table and notice how the blocks for the Reader and Trends tools both change to help elaborate on the context of that occurrence of the word. <img src="https://user-images.githubusercontent.com/15221098/88464626-60057300-ce8a-11ea-93ae-5d966b7b975e.png" class="responsive" alt="voyantcontexts3" style="vertical-align:middle;margin:20px 0px">
3. To add additional terms to your Contexts tool, use the search bar by either clicking and selecting a word or by typing in a word or phrase using Voyant’s search syntax. You can find a cheat sheet for the syntax again by clicking the little “?” symbol on the right end of the search bar. For this example, add “inigo” since he and Fezzik are together for most of the movie. 
<img src="https://user-images.githubusercontent.com/15221098/88464636-73184300-ce8a-11ea-8858-2c61a3540a9d.png" class="responsive" alt="voyantcontexts4" style="vertical-align:middle;margin:20px 0px">

Adding multiple terms to your Contexts tool allows you to get a bird’s eye view of any consistencies in the contexts of different terms!

## Exporting and Embedding your Corpus

One of the nice features of Voyant is the ability to not only export your corpus but also embed it into an online collection, article, or webpage. This allows readers to interact with your data or research. 

1. Hover your mouse over the blue header at the top of your browser window to expose four icons. Click on the icon that is a rounded rectangle with an arrow sticking diagonally out of it. <img src="https://user-images.githubusercontent.com/15221098/88464643-84614f80-ce8a-11ea-952a-08af38daacb0.png" class="responsive" alt="voyantexport1" style="vertical-align:middle;margin:20px 0px">
2. You are provided with a few different options here. The default is a URL that, when clicked, will populate your corpus in the exact condition that is at the time of click the “Export” button. If you select this option, Voyant will open that URL in a new tab and you can copy it from there. To find additional options, click the “Export View (Tools and Data)” dropdown to expose your options:
<img src="https://user-images.githubusercontent.com/15221098/88464649-95aa5c00-ce8a-11ea-99a8-811ff6f707e6.png" class="responsive" alt="voyantexport2" style="vertical-align:middle;margin:20px 0px">


## Other Tips and Tricks

### Resize Your Tool Blocks

If you need to expand or contract the blocks of any of the tools displayed in your corpus, just hover your mouse over the border of the block until you see the resize icon then click and drag it to your desired size. 

<img width="850" alt="Voyant_resize" src="https://user-images.githubusercontent.com/15221098/88464675-b70b4800-ce8a-11ea-96e1-2d9e40853b48.png">

### Changing Your Blocks to Other Tools

We only showed you 5 of the tools available for your corpus. To change one of your blocks, hover over the gray header area of the block you want to change and click the icon with four small rectangles. Check out Voyant’s help database (linked below) to explore all of their available tools! 

<img src="https://user-images.githubusercontent.com/15221098/88464690-d013f900-ce8a-11ea-9a08-fe7c4b44a829.png" class="responsive" alt="voyanttools">


## Other Resources and References
 
* [Voyant Help Database](https://voyant-tools.org/docs/#!/guide/about)

