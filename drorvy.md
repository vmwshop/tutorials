# Faceting and Filtering Distant Reader Data with OpenRefine 

## Objectives
> This tutorial overviews how to use the Distant Reade and OpenRefine together. Please complete or review the [Distant Reader](distancereader.md) and [OpenRefine](openrefine.md) before proceeding.

By the end of this tutorial, you will be able to:
* Identify and locate tab-delimited files in a Distant Reader study carrel
* Facet, filter, and export, study carrel data using OpenRefine

_Much of the following is adapted from Eric Lease Morgan’s documentation and workshops about the Distant Reader tool. See the references section of this tutorial for links to these resources._ 

## What You Need
* Computer with an internet browser and internet connection
* Tab-delimited files from a [Distant Reader Carrel](https://carrels.distantreader.org/)

## Distant Reader + OpenRefine
Distant Reader is designed to be used in conjunction with other tools. One tool that we can use to “hack” the structured data from the Distant Reader is OpenRefine. When we open a tab-delimited file (structure data) in OpenRefine, it will parse the file(s) into fields. We can then use OpenRefine features (finding/replacing, faceting, filtering, sorting, clustering, counting & tabulating, and finally, exporting data) to work with our data.

### Distant Reader Tab-Delimited Files
The results of downloading and uncompressing the Distant Reader study carrel .zip file is a directory/folder containing a standard set of files and subdirectories. Most of the files in a Distant Reader study carrel are tab-delimited files, and they will import into OpenRefine with ease. While the file names end in .adr, .bib, .ent, etc., they are plain text files that can be imported into for favorite spreadsheet, database, or analysis application. 

* **adr**- Each tab-delimited file in this directory contains a set of email addresses extracted from the documents in your corpus. The files have two columns: 1) id, and 2) address. These files can humorously answer the question, “Who are you gonna call?”

* **bib**- Each tab-delimited file in this directory contains a set of rudimentary bibliographic information from a given document in your corpus. The files have thirteen columns: 1) id, 2) author, 3) title, 4) date, 5) page 6), extension, 7) mime, 8) words, 9) sentences, 10) flesch, 11) summary, 12) cache, and 13) txt. These files help answer the question, “What items are in my corpus, and how can they be described?”

* **ent**- Each tab-delimited file in this directory contains a set of named entities from a given document in your corpus. The files have five columns: 1) id, 2) sid, 3) eid, 4) entity, and 5) type. These files help answer questions regarding who, what, when, where, how, and how many.

* **pos**-  Each tab-delimited file in this directory contains a set of part-of-speech files from a given document in your corpus. The files have six columns: 1) id, 2) sid, 3) tid, 4) token, 5) lemma, and 6) pos. These files help answer questions regarding who, what, how, how many, and actions as well as grammar and style.

* **txt**- This subdirectory contains plain text versions of the files stored in the cache directory. A plain text version of each and every item in the cache directory should exist in this directory. The contents of this directory are what was used to do the Reader’s analysis. The contents of this directory are excellent candidates for further analysis with tools such as concordances, indexers, or topic modelers.

* **urls**- Each tab-delimited file in this directory contains a set of URLs from a given document in your corpus. The files have three columns: 1) id, 2) domain, and 3) url. These files help answer questions regarding document provenance and relationships as well as addressing the perenial issue of “finding more like this one.”

* **wrd**- Each tab-delimited file in this directory contains a set of computed keywords from a given document in your corpus. The files have two columns: 1) id, and 2) keyword. These files help answer questions such as “What is this document about?”

For more information on these and other files in Study Carrels, check out [Distant Reader “study carrels”: A manifest](https://sites.nd.edu/emorgan/2019/12/reader-manifest/).

### Faceting and Filtering Study Carrel Data Using OpenRefine
1. Download a sample [Study Carrel](https://carrels.distantreader.org/). These examples use the [“extraterrestrial-beings” Study Carrel](https://carrels.distantreader.org/library/extraterrestrial-beings/study-carrel.zip), but feel free to choose one that interests you. <img src="https://user-images.githubusercontent.com/15221098/88934333-82164100-d24e-11ea-832a-15808e58ec08.png" alt="drorvy1" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">
2. If you have not already done so, [Download](https://openrefine.org/download.html) and install the OpenRefine app. Launch the OpenRefine. Reminder: When you launch the OpenRefine app, your default internet browser will open.

### Recipe 1: Part of Speech Filtering
1. Create a new project in OpenRefine and choose any file from the study carrel's part-of-speech (pos) directory as your input. Accept defaults and “create project”. <img src="https://user-images.githubusercontent.com/15221098/88934336-82aed780-d24e-11ea-8bbb-9d6238d8ce2b.png" alt="drorvy2" class="responsive" width="400" style="vertical-align:middle;margin:40px 0px"> <img src="https://user-images.githubusercontent.com/15221098/88934337-82aed780-d24e-11ea-8abc-fb706e53f25b.png" alt="drorvy3" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px">
2. Click the arrow next to the POS column and select ```Facet > Text facet```. <img src="https://user-images.githubusercontent.com/15221098/88934339-83476e00-d24e-11ea-8fb0-c538e8e60eee.png" alt="drorvy4" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">
3. A column of words and a column of frequencies will appear to the left. In this case, the column of facets shows counts and tabulations of each type of part-of-speech in the file. Try faceting using the other available options including columns and facet types. <img src="https://user-images.githubusercontent.com/15221098/88934340-83476e00-d24e-11ea-82a4-7f93ba79f6c1.png" alt="drorvy5" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px">
4. Click the "Remove All" button to reset your view of the data. <img src="https://user-images.githubusercontent.com/15221098/88940912-6020bc80-d256-11ea-845d-46de3674b1bf.png" alt="drorvy6" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">
5. Click the arrow next to the "token" column and select ```Text filter```. <img src="https://user-images.githubusercontent.com/15221098/88940914-6020bc80-d256-11ea-9f1b-5771d27ef131.png" alt="drorvy7" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">
6. A box to input text will appear in the left sidebar. Think of a word of interest for your corpus and press “enter” to search. Try as many times as you like with other words.
7. “Remove All” again and let’s try filtering and faceting together. This can help with analyzing sentiment.
8. Text filter on the "token" column but search for ```^N``` and check the "regular expression" box.
> You can use the following to filter parts of speech, respectively:
> <p> ^N for nouns </p>
> <p> ^V for verbs </p>
> <p> ^J for adjectives </p>
9. Text facet on the "lemma" column. The result is a count and tabulation of all the nouns. <img src="https://user-images.githubusercontent.com/15221098/88941176-b4c43780-d256-11ea-832c-4fb1284ebcad.png" alt="drorvy8" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">

### Recipe 2: Who and How Often?
1. Create a new project in OpenRefine and select every file in the study carrel's named-entity (ent) directory as your input. <img src="https://user-images.githubusercontent.com/15221098/88975325-fe794600-d287-11ea-8a71-348b1405e0ed.png" alt="drorvy9" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px">
2. Select “configure parsing options.” A warning will probably pop up stating that attempts to parse this as an excel file have failed. Press “OK” and “Parse data as” as “CSV/TSV/separator-based” instead. If your data now appears, select “Create Project”. <img src="https://user-images.githubusercontent.com/15221098/88975327-fe794600-d287-11ea-9034-46736a5cd0bc.png" alt="drorvy10" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px">
3. Text facet on the "type” column.
4. Select "PERSON" from the list of named entities. The result is a count and tabulation of all the people in the corpus. <img src="https://user-images.githubusercontent.com/15221098/88975328-ff11dc80-d287-11ea-865f-a9fe5c1cc92f.png" alt="drorvy11" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px"> 

### Recipe 3: Just for Fun, Let’s Visualize It (Optional)
Word Clouds tend to be looked down upon for a number of reasons (one software architect referred to them as the [“mullets of the internet”](https://www.niemanlab.org/2011/10/word-clouds-considered-harmful/). However, as just one type of tool in our analysis toolkit, they can be helpful for identifying trends or anomalies for more thorough investigation. If anything, they can at least give some insight into how messy your data really is.  

1. Select “Remove All” 
2. Create any sort of meaningful set of faceted results. For this example, we have text faceted the “type” column, selected “PERSON”, then text faceted the “entity” column.  
3. “Cluster” the entities. 
4. Select the "choices" link. You will see a pop-up text area containing counts and tabulation. Copy and paste the whole area into your text editor. <img src="https://user-images.githubusercontent.com/15221098/88975328-ff11dc80-d287-11ea-865f-a9fe5c1cc92f.png" alt="drorvy12" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px"> <img src="https://user-images.githubusercontent.com/15221098/89049935-0258a700-d320-11ea-94c7-82e38ce83411.png" alt="drorvy13" class="responsive" width="500" style="vertical-align:middle;margin:40px 0px"> 
5. “Find” all tab characters and replace them with a colon. “Find” all spaces and replace with a tilde. This is a little different in every editor. The example shows how to find and replace using [Sublime Text](https://www.sublimetext.com/). <img src="https://user-images.githubusercontent.com/15221098/89049937-0258a700-d320-11ea-8389-fdb38f4d07bd.png" alt="drorvy14" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px"> 
6. You may need to do a little more clean up in here, too -- For example, one of the rows (row 21884 in OpenRefine) has a super long and invalid entity value for our purposes. For the sake of brevity, let’s fairly indiscriminately delete all of the rows that seem a little out of place (mostly those that start with numbers).
7. Download [Wordle](http://www.wordle.net/) (the web version no longer works)
8. Copy the whole of the resulting text and paste it into Wordle and select “Go”.
9. Take a look at your Word Cloud. What else do you need to clean up? What does tell you and what does it not tell you? <img src="https://user-images.githubusercontent.com/15221098/89049942-04bb0100-d320-11ea-95c9-f243d06413c6.png" alt="wordlecloud" class="responsive" width="850" style="vertical-align:middle;margin:40px 0px"> 





## References
* [Distant Reader “study carrels”: A manifest](https://sites.nd.edu/emorgan/2019/12/reader-manifest/)
* [Distant Reader Workshop by Eric Lease Morgan on GitHub](https://github.com/ericleasemorgan/reader-workshop)

This tutorial was adapted and written by Jane Thaler in 2020.  
