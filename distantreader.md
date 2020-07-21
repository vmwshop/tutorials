# Distant Reading with the Distant Reader

## Objectives
By the end of this tutorial, you will be able to:
* Identify the types of problems the Distant Reader addresses
* Submit content to the Distant Reader and download results
* Compare some methods for interpreting your downloaded results

## What You Need
* Computer with a web browser and internet connection
* A corpus (we will be using a dataset from the [Western Pennsylvania Regional Data Center](http://www.wprdc.org/) and a Wikipedia URL)

## About the Distant Reader

_Distant reading_ generally refers to the use of computational methods to analyze literary texts. Created by Eric Lease Morgan at the University of Notre Dame, the [Distant Reader](https://distantreader.org/) is a web-based text analysis toolset for “reading” and analyzing texts. It takes unstructured data (text) as input, and it outputs sets of structured data for analysis. The Distant Reader is intended to supplement the traditional reading process by simplifying the process of identifying trends and anomalies in large volumes of text. It is also a method for pre-processing data to be used in natural language processing. 

_Much of the following is adapted from Eric Lease Morgan’s documentation and workshops about the Distant Reader tool. See the references section of this tutorial for links to these resources._ 

### How the Distant Reader Works

The Distant Reader is a system which locally harvests/caches content you specify. It then transforms the content into plain text, performs sets of natural language processing & text mining against the text, saves the results in a number of formats, reduces the whole to a cross-platform database file, queries the database thus summarizing the collection, zips the results of the entire process into a single file, and makes the file available to you for further investigation.

### What We Can Do With the Distant Reader

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
* How are the things represented by nouns, verbs, and adjectives related?
* Who is mentioned in the corpus, how frequently, and where?
* What places are mentioned in the corpus, how frequently, and where?


## Getting Started
1. Using your web browser, navigate to https://distantreader.org/.
2. Select “Create Account” on the top right. <img src="https://user-images.githubusercontent.com/15221098/87683727-6b9cbf80-c74f-11ea-8f9f-684248ce3927.png" alt="DRCreateAccount1" class="responsive" width="600">
3. Fill in your account information, confirm your account, and log in.
4. You should now see your Distant Reader Portal Dashboard where you can submit yout input and download the results (referred to as “study carrels”). <img src="https://user-images.githubusercontent.com/15221098/87683736-6d668300-c74f-11ea-8e69-6e84d81cd7e7.png" alt="DRHome" class="responsive" width="600">

## Submitting Content ("Experiments") to the Distant Reader

### Types of Input
The Distant Reader can currently accept these five types of input:

* **Single file -**
A single file can be just about any file available to you, but it needs to contain textual data. Word documents, spreadsheets, HTML, and plain text will work. Image files like PNG and JPEG will not. PDFs will also work so long as they were created digitally with text content or [converted into text using OCR](https://acrobat.adobe.com/us/en/acrobat/how-to/ocr-software-convert-pdf-to-text.html#:~:text=Easily%20edit%20your%20scanned%20PDF,editable%2C%20searchable%20PDF%20files%20instantly.).

* **Single URL -**
Given a URL, the Reader will cache the URL’s content, crawl the URL one level deep, cache the result, and stop caching to create a corpus. This works well with URLs pointing to things like Wikipedia articles, open access journal articles, the home page of some sort of institution or organization, and blogs.

> Caveats: 
> * The Reader can only cache 100% freely accessible content, which means the content cannot be behind paywalls or firewalls. 
> * Many URLs do not point to the content itself, but instead, they point to ill-structured pages describing the content (think “splash” and “landing” pages). These things are not presented in a consistent nor computer-readable fashion, so make try to avoid these types of content-less pages. 
> * Many Web pages include links for navigating around the site. They also include links to things like “contact us” and “about this site”. If found, the Reader will crawl such links and include their content in the resulting corpus. This may not be an undesirable thing given your research questions, but be aware of this in your analysis. 

* **List of URLs -**
The Reader will take lists of URLs as a plain text file (.txt.). Like the single URL approach, the list of URLs must point to freely available content, and pointing to landing pages or splash pages is probably to be avoided. Unlike the single URL approach, the URLs in the list will not be used as starting points for Web crawling. Thus, if the list contains ten items, then ten items will be cached for analysis. 

> Tip: Pulling URLs from link can be incredibly tedious. Try using a URL extraction tool to speed up the process. Eric Lease Morgan suggest the Google Chrome extension called [Link Grabber](https://chrome.google.com/webstore/detail/link-grabber/caodelkhipncidmoebgbbeemedohcdma?hl=en-US).

* **Zip file -**
If you want to submit multiple files to the Reader, pull them altogether Create a folder/directory on your computer, copy just about any file into the folder/directory (see caveats for single files above), then compress the file into a .zip file. Submit the result to the Reader. This method is helpful for circumventing URL authorization restrictions because you can put licensed content into your zip files and it will be analyzed just like any other content. Converting files into plain text in bulk can also allow pre-processing to take place (e.g., you can find/replace to clean up header and footer information)

> Caveats: 
> * The .zip files must be smaller than 64 megabytes. 
> * Keep your file names simple, less than 64 characters, and avoid extraneous characters.

* **Zip file with companion CSV file -**
As the size of your corpus increases, so does the need for context. This context can often be manifested as metadata (authors, titles, dates, subject, genre, formats, etc.). For example, you might want to compare and contrast who wrote what. You will probably want to observe themes over space and time. You might want to see how things differ between different types of documents. To do this sort of analysis you will need to know metadata regarding your corpus. This is where the CSV file comes in; by including a CSV file named “metadata.csv” in the .zip file, the Distant Reader will be able to provide meaningful context.

> How to create this CSV File:
> * Assemble a set of files for analysis
> * Use your favorite spreadsheet or database application to create a list of the file names
assign a header to the list (column) and call it “file”
> * Create one or more columns whose headers are “author” and/or “title” and/or “date”
to the best of your ability, update the list with author, title, or date values for each file
> * Save the result as a CSV file named “metadata.csv” and put it in the folder/directory to be zipped
> * Compress the folder/directory to create the zip file

### Creating a New "Experiment"
1. Determine your type of input and select the corresponding experiment application in your Distant Reader dashboard. For this tutorial, let’s try using a single .csv file. The file used here is the [Bike PGH Bicycle Pavement Markings June 2016](https://data.wprdc.org/dataset/on-road-bicycle-pavement-markings/resource/90fb26be-e754-4f45-b695-d17f0645dd2b) downloaded from the WPRDC site.
2. Enter the name of your experiment, add your input (you can ignore pretty much everything else on the page), then submit your experiment by selecting “Save and Launch.” <img src="https://user-images.githubusercontent.com/15221098/87858423-c4a95680-c8fb-11ea-92e8-d86f03a7c8ef.png" alt="DRInput1" class="responsive" width="600">
3. Your experiment is now sent to the queue. If there are fewer than ten jobs currently running, the submitted job will be run immediately. It takes almost two minutes for the Reader to instantiate a new virtual machine, and then, depending on the number and sizes of items to read, processing can take as short as four minutes or as long as twelve hours. Generally, this process takes less than ten minutes. It is not necessary to keep your Web browser open to the Reader's interface; the Distant Reader will do its work and wait for you to return. <img src="https://user-images.githubusercontent.com/15221098/87858425-c4a95680-c8fb-11ea-8468-019c47f73466.png" alt="DRInput2" class="responsive" width="600">
4. When the Reader has finished, your dashboard will have been updated and you can navigate to the “Experiment Summary” page. From here you can: 
 * Read the standard error report; send this to the author if something goes amiss. 
 * Read the standard output report, which is a simple summary of what the Reader found; look at this report first. 
 * Download the study carrel.
<img src="https://user-images.githubusercontent.com/15221098/87858426-c4a95680-c8fb-11ea-9215-fd9955e6117f.png" alt="DRInput3" class="responsive" width="400"><img src="https://user-images.githubusercontent.com/15221098/87858427-c4a95680-c8fb-11ea-8ca2-190d24d1822c.png" alt="DRInput4" class="responsive" width="400">

## Working with the Distant Reader Results ("Study Carrels")

### Study Carrels
The results of the Distant Reader process is a "study carrel" -- a .zip file containing a set of structured data that includes your original content, various transformations of it, and various sets of analysis. Uncompressing the Distant Reader study carrel results in a directory/folder containing a standard set of [files and subdirectories](https://github.com/ericleasemorgan/reader-workshop#the-structured-data-of-study-carrels-taking-inventory-through-the-manifest). The following sections detail how to download your study carrel and some basic ways of interacting with the results.

### Downloading Your Study Carrel
1. Download the results of your experiment found under “ZipFile” in your experiment summary. <p><img src="https://user-images.githubusercontent.com/15221098/87859042-587d2180-c900-11ea-93c2-43d664fbb0e7.png" alt="DRstudycarrel1" class="responsive" width="400"></p>
2. Find your locally downloaded .zip file. The zipped filed should have downloaded with “study-carrel” somewhere in the file name.
3. Unzip the file by double-clicking it. 
4. The resulting unzipped file will have a long, seemingly unrelated string of characters as the filename. Rename the file to something simpler and more relevant to you. Consider moving the file to your desktop while you work with it. 

### Working with Your Study Carrel - Narrative Reports
1. Open the .zip file and navigate to the HTML text file called “index.htm.” This is the root of the narrative interface and will open in your web browser. <img src="https://user-images.githubusercontent.com/15221098/87859041-57e48b00-c900-11ea-9b50-ad8abbdddb26.png" alt="DRnarrative1" class="responsive" width="400">
2. The body of the study carrel's narrative interface provides a very broad overview of your study carrel. Narrative reports including frequencies, keywords, and topic modeling can be accessed on the left-hand side of the page. <img src="https://user-images.githubusercontent.com/15221098/87860394-33da7700-c90b-11ea-939a-5620c9cacf99.png" alt="DRnarrative2" class="responsive" width="600">
3. Take some time now to explore the narrative reports. Eric Lease Morgan provides some detail as to what these reports can help tell you about your data. Also, see the standard-output.txt file in the unzipped study carrel, as it will both summarize and elaborate upon this narrative report.<img src="https://user-images.githubusercontent.com/15221098/87860396-34730d80-c90b-11ea-9d60-d0a8f0f03e70.png" alt="DRnarrative3" class="responsive" width="600">
> As you can see, this single .csv does not have a ton of variation or narrative data to analyze. While not the most exciting dataset, this does at least point to the idea that this dataset is used for bureaucratic purposes and is fairly consistent. Think about what you see in these reports and how using Distant Reader for this type of dataset might not be the best option. 
> Let’s try running an experiment with more narrative content to see how this works more clearly. To keep with the theme, let’s find the URL for the Wikipedia page for [Bike Lanes](https://en.wikipedia.org/wiki/Bike_lane) and follow the same steps as the [Creating a New Experiment](https://github.com/janethaler/dsamtools/blob/master/distantreader.md#creating-a-new-experiment) section above. What differences do you see?

### Working with Your Study Carrel - Interactive Reports
1. The links at the top of the page point to interactive HTML pages. Each page is really a table listing bi-grams, noun-verb combinations, adjective-noun combinations, questions, etc. Let’s look at how to browse, sort, and search the content of the menu items named Ngrams, POS, Grammars, and Others. You can use these reports to look for patterns or anomalies, ask themselves questions, and then enter text into any of the available text areas in order to answer (or at least address) their question: For example, enter the words "who", "what", "when", "where", "why", "how", or "how many" into the text area of the question page. The interactive HTML pages are akin to a back-of-the-book index.
> As mentioned above, our data output regarding bike lanes does not have a lot of fodder for questions like these. Let’s continue using our [Bike Lanes Wikipedia Study Carrel](https://en.wikipedia.org/wiki/Bike_lane) for the rest of this section.
2. Now navigate to the “Named Entities” table in the “Other” Dropdown. <img src="https://user-images.githubusercontent.com/15221098/87861091-f37df780-c910-11ea-86e6-3d311a0f97ab.png" alt="DRinterp1" class="responsive" width="400">
3. The named entity pages list names of people (PERSON), organizations (ORG), places (GRE), and locations (LOC). To learn who is mentioned in your study carrel, enter "PERSON" into the text area. To learn what organizations, places, or locations are mentioned in your study carrel, enter the labels "ORG", "GRE", or "LOC" into the text area. <img src="https://user-images.githubusercontent.com/15221098/87861092-f4168e00-c910-11ea-8aed-9b1146b27836.png" alt="DRinterp2" class="responsive" width="400">
4. All of the other pages linked from the top of the index.htm page operate very similarly. Explore those now. 
5. And there you have it! You now know the basics of working with the Distant Reader. As with everything, using the tool requires practice and refining. Remeber that it's almost impossible to break anyhting using the Distant Reader, so you can rest assured when trying all sorts of experiments.

## Cleaning and Analyzing Your Study Carrel

Notice how the content we used cannot simply be taken at face value. For example, Wikipedia and it’s related privacy policy information tends to take over frequency assessments if not cleaned.
<img src="https://user-images.githubusercontent.com/15221098/87861701-c46a8480-c916-11ea-8a85-95729610d7ed.png" alt="keywords" class="responsive" width="400">
<img src="https://user-images.githubusercontent.com/15221098/87861700-c16f9400-c916-11ea-9bfe-8ef107ddf850.png" alt="DRIssues1" class="responsive" width="400">
The Distance Reader can help with pre-processing, but there is always work to do in terms of cleaning your data and conducting analysis. There are three essential types of desktop tools you will need/want in order to use the content of a study carrel. These types include: text editors, spreadsheet/database applications, and analysis programs. Please

### Text Editors
Text editors read and write plain text files -- files with no formatting and no binary characters. Plain text files usually have a .txt extension. Every single file in a Distant Reader study carrel (except one) is a plain text file, and therefore, every single file (except one) is openable by any text editor. You can use a text editor to find/replace to find any character and change it to something else, which is useful for stopwords, carriage returns, newline characters, etc. Another very useful function of a text editor, especially used for the purposes of text mining and natural language processing, is the ability to change the case of all letters to either their upper or lower-case forms. Such is the most basic of text normalization/cleaning processes.

* Here are some good options:
  * Windows - [Notepad++](https://notepad-plus-plus.org/downloads/), [Sublime Text](https://www.sublimetext.com/3)
  * Mac - [BBedit](https://www.barebones.com/products/bbedit/download.html), [Sublime Text](https://www.sublimetext.com/3), [Atom](https://atom.io/)

### Spreadsheet/Database Applications
Spreadsheet/database applications are designed to read "delimited" files, plain text files where each line is a row in a matrix, and each item is punctuated by some special character such as a tab character or a comma. These items are the columns in the matrix. The whole file is a kin to a spreadsheet or a database. Like a text editor, you will want to use the spreadsheet/database application to support sort.

The majority of the files in a study carrel are delimited files, and these delimited files are really annotated lists. Examples include lists of word and their parts-of-speech, lists of documents and the URLs they contain, or lists of sentences and the named-entities they include. Given these files the student, researcher, or scholar can compare & contrast the ratio of named entities across a corpus, or they could plot the ebb & flow of an idea over time.

* Some common spreadsheet applications: 
  * [Microsoft Excel](https://www.microsoft.com/en-us/microsoft-365/excel)
  * [Apple Numbers](https://www.apple.com/numbers/)

### Analysis Programs

Analysis programs cover a wide spectrum of tools and these tools fall into a number of categories including counting & tabulating, concordancing, topic modeling, and visualizing. It is not within the scope of this tutorial to cover all of these programs, but here are a few that can be useful when working with Distant Reader study carrels:

* [OpenRefine](https://openrefine.org/download.html#) - OpenRefine (previously Google Refine) is a powerful, opensource tool for working with messy data. Key features include cleaning up small to large mistakes en masse, converting data from one format to another, and adding to a dataset by pulling data from an online source into your dataset. 

* [AntConc](https://www.laurenceanthony.net/software/antconc/) - AntConc contains seven tools. 
  * Concordance Tool: This tool shows search results in a 'KWIC' (KeyWord In Context) format. This allows you to see how words and phrases are commonly used in a corpus of texts.
  * Concordance Plot Tool: This tool shows search results plotted as a 'barcode' format. This allows you to see the position where search results appear in target texts.
  * File View Tool: This tool shows the text of individual files. This allows you to investigate in more detail the results generated in other tools of AntConc.
  * Clusters/N-Grams: The Clusters Tool shows clusters based on the search condition. In effect it summarizes the results generated in the Concordance Tool or Concordance Plot Tool. The N-Grams Tool, on the other hand, scans the entire corpus for 'N' (e.g. 1 word, 2 words, …) length clusters. This allows you to find common expressions in a corpus.
  * Collocates: This tool shows the collocates of a search term. This allows you to investigate non-sequential patterns in language.
  * Word List: This tool counts all the words in the corpus and presents them in an ordered list. This allows you to quickly find which words are the most frequent in a corpus.
  * Keyword List: This tool shows the which words are unusually frequent (or infrequent) in the corpus in comparison with the words in a reference corpus. This allows you to identify characteristic words in the corpus, for example, as part of a genre or ESP study.
  
* [MALLET Topic Modeling Tool](http://mallet.cs.umass.edu/topics.php) - Topic Modeling Tool is a GUI/desktop topic modeler based on the venerable MALLET suite of software. Technically speaking, topic modeling is an unsupervised machine learning process used to extract latent themes from a text. Given a text and an integer, a topic modeler will count & tabulate the frequency of words and compare those frequencies with the distances between the words. The words form "clusters" when they are both frequent and near each other, and these clusters can sometimes represent themes, topics, or subjects. Topic modeling is often used to denote the "aboutness" of a text or compare themes between authors, dates, genres, demographics, other topics, or other metadata items.

* [Wordle](http://www.wordle.net/) -  Visualized word frequencies, while often considered sophomoric, can be quite useful when it comes to understanding a text, especially when the frequencies are focused on things like parts-of-speech, named entities, or co-occurrences. Wordle visualizes such frequencies.

## Conclusions
>"The Distant Reader is a tool for reading. It takes an almost arbitrary amount of unstructured data (text) as input, and it outputs sets of structured data for analysis -- reading. As such, the Distant Reader is akin to books' page numbers, tables-of-contents, back-of-the-book indexes, and other apparatuses used to make them easier to use and understand. The difference is the Distant Reader does these things at scale. The Distant Reader is not a replacement for the traditional reading process, but instead it supplements the process. If you were asked to articulate a few main themes or just about anything else about any given corpus, then you would probably be able do so, but with the Distant Reader you would be able to so more thoroughly. Moreover, you would be able to literally point where those themes were manifested themselves. The Distant Reader does not output truth nor meaning. It merely outputs observations. Just like the traditional reading processes, it is up to the student, researcher, or scholar to interpret the observations and discuss the possible truth or meaning. It his way, the Distant Reader is simply a tool in the ongoing dialog on what it means to be human. Given the amount of narrative data/information at our finger tips, discovery is not the problem to solve. I don't know about you, but I can find plenty. No, the problem goes beyond that; the problem is about getting the data/information, and reading it. The Distant Reader is a tool intended to address just these sorts of issues." _From Eric Lease Morgan's Distant Reader Workshop_ 


## Distant Reader Resources
* [Distant Reader Home](https://distantreader.org/)
* [Distant Reader Workshop by Eric Lease Morgan on GitHub](https://github.com/ericleasemorgan/reader-workshop)
* [Distant Reader Blog by Eric Lease Morgan](http://sites.nd.edu/emorgan/category/distant-reader/)



