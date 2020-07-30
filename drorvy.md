# Faceting, Filtering, and Visualizing Distant Reader Data with OpenRefine and Voyant

## Objectives
> This tutorial overviews how to use the Distant Reader, OpenRefine, and Voyant together. Please complete or review the [Distant Reader](distancereader.md), [OpenRefine](openrefine.md), and [Voyant](voyant.md) tutorials before proceeding.

By the end of this tutorial, you will be able to:
* Identify and locate tab-delimited files in a Distant Reader study carrel
* Facet, filter, and export, study carrel data using OpenRefine
* Visualize frequencies with Voyant

_Much of the following is adapted from Eric Lease Morgan’s documentation and workshops about the Distant Reader tool. See the references section of this tutorial for links to these resources._ 

## What You Need
* Computer with an internet browser and internet connection
* Tab-delimited file from a [Distant Reader Carrel](https://carrels.distantreader.org/)

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

### Faceting study carrel data using OpenRefine
1. Download a sample [Study Carrel](https://carrels.distantreader.org/). These examples use the [“extraterrestrial-beings” Study Carrel](https://carrels.distantreader.org/library/extraterrestrial-beings/study-carrel.zip), but feel free to choose one that interests you. 

<img src="https://user-images.githubusercontent.com/15221098/88934333-82164100-d24e-11ea-832a-15808e58ec08.png" alt="drorvy1" class="responsive" width="500">

2. If you have not already done so, [Download](https://openrefine.org/download.html) and install the OpenRefine app. Launch the OpenRefine. Reminder: When you launch the OpenRefine app, your default internet browser will open.

3. Create a new project in OpenRefine and choose any file from the study carrel's part-of-speech (pos) directory as your input. Accept defaults and “create project”.

<img src="https://user-images.githubusercontent.com/15221098/88934336-82aed780-d24e-11ea-8bbb-9d6238d8ce2b.png" alt="drorvy2" class="responsive" width="400">
<img src="https://user-images.githubusercontent.com/15221098/88934337-82aed780-d24e-11ea-8abc-fb706e53f25b.png" alt="drorvy3" class="responsive" width="850">

4. Click the arrow next to the POS column and select Facet > Text facet.

<img src="https://user-images.githubusercontent.com/15221098/88934339-83476e00-d24e-11ea-8fb0-c538e8e60eee.png" alt="drorvy4" class="responsive" width="500">

5. A column of words and a column of frequencies will appear to the left. In this case, the column of facets shows counts and tabulations of each type of part-of-speech in the file. Try faceting using the other available options including columns and facet types. 

<img src="https://user-images.githubusercontent.com/15221098/88934340-83476e00-d24e-11ea-82a4-7f93ba79f6c1.png" alt="drorvy5" class="responsive" width="300">



## References
* [Distant Reader “study carrels”: A manifest](https://sites.nd.edu/emorgan/2019/12/reader-manifest/)
* [Distant Reader Workshop by Eric Lease Morgan on GitHub](https://github.com/ericleasemorgan/reader-workshop)
