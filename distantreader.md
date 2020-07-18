# Using the Distant Reader

## Objectives
By the end of this tutorial, you will be able to:
* Identify the types of problems the Distant Reader addresses
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
1. Using your web browser, navigate to https://distantreader.org/
2. Select “Create Account” on the top right <p><img src="https://user-images.githubusercontent.com/15221098/87683727-6b9cbf80-c74f-11ea-8f9f-684248ce3927.png" alt="DRCreateAccount1" class="responsive" width="600"></p>
3. Fill in your account information, confirm your account, and log in.
4. You should now see your Distant Reader Portal Dashboard where you can submit yout input and download the results (referred to as “study carrels”). <p><img src="https://user-images.githubusercontent.com/15221098/87683736-6d668300-c74f-11ea-8e69-6e84d81cd7e7.png" alt="DRHome" class="responsive" width="600"></p>

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
2. Enter the name of your experiment, add your input (you can ignore pretty much everything else on the page), then submit your experiment by selecting “Save and Launch.” <p><img src="https://user-images.githubusercontent.com/15221098/87858423-c4a95680-c8fb-11ea-92e8-d86f03a7c8ef.png" alt="DRInput1" class="responsive" width="600"></p>
3. Your experiment is now sent to the queue. If there are fewer than ten jobs currently running, the submitted job will be run immediately. It takes almost two minutes for the Reader to instantiate a new virtual machine, and then, depending on the number and sizes of items to read, processing can take as short as four minutes or as long as twelve hours. Generally, this process takes less than ten minutes. It is not necessary to keep your Web browser open to the Reader's interface; the Distant Reader will do its work and wait for you to return. <p><img src="https://user-images.githubusercontent.com/15221098/87858425-c4a95680-c8fb-11ea-8468-019c47f73466.png" alt="DRInput2" class="responsive" width="600"></p>
4. When the Reader has finished, your dashboard will have been updated and you can navigate to the “Experiment Summary” page. From here you can: 
 * Read the standard error report; send this to the author if something goes amiss. 
 * Read the standard output report, which is a simple summary of what the Reader found; look at this report first. 
 * Download the study carrel.
<p><img src="https://user-images.githubusercontent.com/15221098/87858426-c4a95680-c8fb-11ea-9215-fd9955e6117f.png" alt="DRInput3" class="responsive" width="400"><img src="https://user-images.githubusercontent.com/15221098/87858427-c4a95680-c8fb-11ea-8ca2-190d24d1822c.png" alt="DRInput4" class="responsive" width="400"></p>

## Working with the Distant Reader Results ("Study Carrels")

### Study Carrels
The results of the Distant Reader process is a "study carrel" -- a .zip file containing a set of structured data that includes your original content, various transformations of it, and various sets of analysis. The following sections detail how to download your study carrel and some basic ways of interacting with the results.

### Downloading Your Study Carrel
1. Download the results of your experiment found under “ZipFile” in your experiment summary. <p><img src="https://user-images.githubusercontent.com/15221098/87859042-587d2180-c900-11ea-93c2-43d664fbb0e7.png" alt="DRstudycarrel1" class="responsive" width="400"></p>
2. Find your locally downloaded .zip file. The zipped filed should have downloaded with “study-carrel” somewhere in the file name.
3. Unzip the file by double-clicking it. 
4. The resulting unzipped file will have a long, seemingly unrelated string of characters as the filename. Rename the file to something simpler and more relevant to you. Consider moving the file to your desktop while you work with it. 

### Working with Your Study Carrel through the Narrative Interface
1. Open the .zip file and navigate to the HTML text file called “index.htm.” This file will open in your web browser. <p><img src="https://user-images.githubusercontent.com/15221098/87859041-57e48b00-c900-11ea-9b50-ad8abbdddb26.png" alt="DRnarrative1" class="responsive" width="400"></p>

