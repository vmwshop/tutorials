# Cleaning Data with OpenRefine 

## Objectives

By the end of this tutorial, you will be able to:
* Facet (count & tabulate) messy data
* Filter and export a specific portion of your dataset

## What You Need
* Computer with a web browser and internet connection
* A dataset - ideally something on the larger size (i.e. tens or hundreds of thousands of data points)
    * We altered a dataset from the [Western Pennsylvania Regional Data Center](http://www.wprdc.org/) for this tutorial. Access our **["messy" dataset](https://raw.githubusercontent.com/janethaler/dsamtools/master/Allegheny%20County%20Dog%20Licenses.csv)** here. 
        > * Right click the "messy" dataset link above and select "Open in New Tab" 
        > * On the webpage that opens, right click and select "Save As"
        > * Save the .csv file somewhere you can easily access it again when it's time to upload it
    * Your own data can be uploaded as a file in many different formats (csv, json, wiki, xls, etc.), pulled from a webpage, or even copy/pasted as text

## About OpenRefine

OpenRefine (previously Google Refine) is a powerful, opensource tool for working with messy data. Key features include cleaning up small to large mistakes en masse, converting data from one format to another, and adding to a dataset by pulling data from an online source into your dataset. OpenRefine is an app that is downloaded to your personal computer that then uses your internet browser to interact with it. While it might look as though you are uploading your data to the internet through your browser, the data is in fact still being locally hosted on your hard drive. 

### What Can We Do With OpenRefine?
* Clean up messy data
* Combine data from a website with an outside dataset
* Convert a dataset from one format to another

## Getting Started

To get started, there is no account sign up. All you need to do is visit [the OpenRefine Downloads Page](https://openrefine.org/download.html) and pick the download kit that is applicable to your operating system. 

> _NOTE_: If using a Mac, you may get a security warning that your computer doesn’t recognize the developer and won’t let you open the application. If that is the case, then go to your System Settings > Security & Privacy > Click the lock icon in the bottom left corner of the window > Click the _“Open Anyway”_ button in the _“Allow apps downloaded from”_ section of your General
Settings. Open it again and you should be good to go!

Once you have the app downloaded and installed, launch the app, upload your data, and start working. As a reminder, when you launch the OpenRefine app, your default internet browser will open. This is how you interact with the application even though your data is still being hosted locally on your personal drive. So, no need to worry about the security of your data! 

## Uploading Your Data

1. Click the “Choose Files” button, select your dataset, and click “Next”. For this workshop, we altered a dataset from the WRPDC: **["messy" Allegheny County Dog Licenses.csv](https://raw.githubusercontent.com/janethaler/dsamtools/master/Allegheny%20County%20Dog%20Licenses.csv)**. If you already have some data that you know is messy, feel free to use that and follow along with the same steps! Just be prepared for us to use different values and have different “mistakes” within our provided data than what you might have. <img src="https://user-images.githubusercontent.com/15221098/87857135-50b68080-c8f2-11ea-8f74-80d2897f285d.png" class="responsive" alt="ORgetstarted1" width="850" style="vertical-align:middle;margin:20px 0px">
2. Once uploaded, your data will appear in a "Configure Parsing Options" page. There are several options available at this point, but we can stick to the default settings for our purposes. So, just click the “Create Project” button in the top right corner to continue. <img src="https://user-images.githubusercontent.com/15221098/87857139-5ad87f00-c8f2-11ea-8aa9-683c15222099.png" class="responsive" alt="ORgettingstarted2" width="850" style="vertical-align:middle;margin:20px 0px">
3. Once your project is created, you will see the first ten rows of your data as a new OpenRefine project. <img src="https://user-images.githubusercontent.com/15221098/87824197-d24ed580-c842-11ea-95ad-5a330fe90798.png" class="responsive" alt="ORgettingstarted3" width="850" style="vertical-align:middle;margin:20px 0px">

## Faceting  

Facets are the bread and butter of OpenRefine when it comes to cleaning up messy data as well as sorting and filtering it. Essentially, they are a collection of each value in each cell of your data, grouped together with a total count for each unique datapoint. When you create a “text facet” or you "facet text" OpenRefine automatically separates and groups them based on text and characters. You will also notice that the fine folks at OpenRefine have [provided a link to some great screencasts](https://github.com/OpenRefine/OpenRefine/wiki/Screencasts) on using filters and facets. Much of this tutorial is based on these videos, so please feel free to reference those as well.

1. In the Breed column of our data, click the dropdown arrow in the column header and select ```Facet > Text facet```. <img src="https://user-images.githubusercontent.com/15221098/87824323-0de99f80-c843-11ea-912c-e1b001de2aff.png" class="responsive" alt="ORfacets1" width="850" style="vertical-align:middle;margin:20px 0px">
2. In the left sidebar, you will see a list of all of the different breeds in your dataset grouped together with a total count for each. Take a look through these carefully and you will notice that there are some that appear to be duplicates. <img src="https://user-images.githubusercontent.com/15221098/87824431-3d98a780-c843-11ea-8f46-a70573c98b2f.png" class="responsive" alt="ORfacets2" width="850" style="vertical-align:middle;margin:20px 0px">
3. You will see some minor typos, find trailing spaces, etc. OpenRefine has built-in features to help rid your data of these quickly. The first of which lives in your facet widget in the left sidebar. Click the “Cluster” button in the top right corner of the widget. Here you will see a list of any data points that OpenRefine thinks are supposed to be the same. The “Values in Cluster” column shows you what values are up for being combined and the “New Cell Value” column shows you what OpenRefine wants to change them to. For our dataset, OpenRefine got them all right, so click the checkbox in each row in the “Merge” column (or click the “Select All” button under the table) then click “Merge Selected & Close”. <img src="https://user-images.githubusercontent.com/15221098/87824474-56a15880-c843-11ea-9388-31d851c126c5.png" class="responsive" alt="ORfacets3" width="850" style="vertical-align:middle;margin:20px 0px">
4. Take another look at your Breed facets. Scroll down until you find the “AM PIT BUL TERRIER” and “AM PIT BULL MIX” values. You will notice that they each only have one entry and right under them there are “AM PIT BULL TERRIER” AND “AM PITT BULL MIX” values with hundreds of entries each. This inconsistency might be important for analysis, but it also might just be something that needs to be cleaned. Let's assume that latter. Hover over each value and click the “Edit” button that appears to the right of them. This will bring up a text box where you can manually edit the typo from “PIT BUL” to “PIT BULL”, etc. <img src="https://user-images.githubusercontent.com/15221098/87824514-69b42880-c843-11ea-9f3d-a5cbaebb5aa8.png" class="responsive" alt="ORfacets4" width="850" style="vertical-align:middle;margin:20px 0px">
5. Once you click “Apply” you will see your typo’ed value disappear and the count of the correctly spelled value increase by one. <img src="https://user-images.githubusercontent.com/15221098/87826045-37f09100-c846-11ea-9dd0-8d4ff9be6790.png" class="responsive" alt="ORfacets5" width="850" style="vertical-align:middle;margin:20px 0px"> <img src="https://user-images.githubusercontent.com/15221098/87826118-4dfe5180-c846-11ea-93d8-04015ff32c18.png" class="responsive" alt="ORfacets6" width="850" style="vertical-align:middle;margin:20px 0px">

6. Listed here are some other minor errors in the provided dataset that you can use the above steps to locate and correct. Scrolling through your list of facets sorted by name is a quick way to identify these by noticing lower than usual counts and duplicates for values. 

- Edit the “BAGLE” value to “BEAGLE”
- Edit the “BOXTER” value to “BOXER”
- Edit the “MATLEESE” value to “MALTESE”
- Edit the “MIX” value to “MIXED”

### Other Quick Edits

#### Eliminate Extra Spaces

A common issue with large datasets is trailing or leading spaces. Meaning there is a space either right before or right after the value in the cell. OpenRefine makes trimming these off of your data super easy! 

Again in the “Breed” column of your dataset, click the dropdown arrow by the column header and hover over ```Edit Cells > Common Transformations > Trim leading and trailing whitespace```. You can repeat this for each column just to be sure that you've cleared up any trailing spaces throughout your data. <img src="https://user-images.githubusercontent.com/15221098/87826248-8bfb7580-c846-11ea-8686-da19dc895e2d.png" class="responsive" alt="ORotheredits1" width="850" style="vertical-align:middle;margin:20px 0px">

#### Split Columns with Multiple Values

1. Look at the “ValidDate” column of our data. You will see that the values have both a date and a time in the same cell. We want a separate column for “ValidTime”. In the header of the “ValidDate” column, click the dropdown arrow and hover over ```Edit column > Split into several columns```. Notice how the dates and times in the “ValidDate” cells are separated by a “T”. Enter “T” in the “Separator” box in the Split column window and click “OK”. <img src="https://user-images.githubusercontent.com/15221098/87826318-af262500-c846-11ea-95ad-cc79d5e5820b.png" class="responsive" alt="ORotheredits2" width="850" style="vertical-align:middle;margin:20px 0px">

2. Now you have your dates and times in separate columns! Notice how OpenRefine automatically names the headers of these columns based on the original column’s name. Simply edit these by clicking the dropdown next to the header name and select ```Edit column > Rename this column```. <img src="https://user-images.githubusercontent.com/15221098/87826393-cfee7a80-c846-11ea-8b1d-d2dd346563f2.png" class="responsive" alt="ORotheredits3" width="850" style="vertical-align:middle;margin:20px 0px"> 

#### Add Text To Existing Values

Just for clarity’s sake, we want all of our pups that are designated as “MIXED” to read as “MIXED BREED”. So let’s add the word “BREED” to any occurrence of the word “MIXED” in the “Breeds” column. 

1. Back in your Facets widget, scroll down to the “MIXED” value and select it. The facet will be bolded and change to orange to signify that it’s selected. <img src="https://user-images.githubusercontent.com/15221098/87826584-2b206d00-c847-11ea-9e86-5eb4da23adba.png" class="responsive" alt="ORotheredits4" width="850" style="vertical-align:middle;margin:20px 0px"> 
2. With the facet selected, click the dropdown arrow in the “Breed” column header and select ```Edit cells > Transform…``` <img src="https://user-images.githubusercontent.com/15221098/87826637-3d9aa680-c847-11ea-9d57-eca51ecff7e1.png" class="responsive" alt="ORotheredits5" width="850" style="vertical-align:middle;margin:20px 0px"> 
3. Here you will use what OpenRefine calls _General Refine Expression Language or GREL_ to tell OpenRefine how you want to transform your cells. For this example, in the “Expression” box, use the following command to add your text to the existing values:

```
value+” BREED”
```
Luckily, the Google Refine Expression Language is pretty simple and there tons of [resources available](https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language) on using it if you run into a more complicated need for it, so it's not really necessary to learn it.

You will see a preview of your handy work in the table under the “Expression” box. Click “OK” when it looks the way you want it to. 

<img src="https://user-images.githubusercontent.com/15221098/87826691-55722a80-c847-11ea-9aaa-9a1c9e6b0e08.png" class="responsive" alt="ORotheredits6" width="850" style="vertical-align:middle;margin:20px 0px"> 

### Filtering and Exporting Data

Now that your data is all cleaned up and ready for use, you can use facets to filter out what you don’t need, sort everything by a specific value, or a combination of both! Filtering is about as easy as it gets. 

1. Click the dropdown of the “LicenceType” column header. Select ```Facet > Text Facet```. Let’s say we want to find out how many of our registered pups are seniors. From your facet widget in the left sidebar, hover over each of the values that include “Senior”. As you hover over each, you will see the option to either “edit” or “include”. Click “include” for each value. As you do this for each facet, they will all become bold and turn orange, signifying that they are selected. You will also notice the number of matching rows at the top of the page adjusts to show you how many rows contain our senior pups. <img src="https://user-images.githubusercontent.com/15221098/87826731-6884fa80-c847-11ea-8520-43e614a7d76e.png" class="responsive" alt="ORsortandfilter1" width="850" style="vertical-align:middle;margin:20px 0px"> 
2. From here, you can Export your filtered data by clicking the “Export” dropdown in the top right corner of the screen and selecting your desired format. For this example, we will choose “Comma-separated value”. <img src="https://user-images.githubusercontent.com/15221098/87826773-7c306100-c847-11ea-8e0b-de8f1458323b.png" class="responsive" alt="ORsortandfilter2" width="850" style="vertical-align:middle;margin:20px 0px"> 

You have now exported a filtered portion of your dataset to manipulate further or send away, but your OpenRefine project remains right where you left off! Now you can jump back into OpenRefine and remove your filters and export your data again however else you might need to.  


#### Other Resources and References

- [OpenRefine Video Tutorials](https://github.com/OpenRefine/OpenRefine/wiki/Screencasts)
- [Miriam Posner’s “Get started with OpenRefine”](http://miriamposner.com/classes/dh101f17/tutorials-guides/data-manipulation/get-started-with-openrefine/)
- [General Refine Expression Language Guide](https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language)
- [OpenRefine on Github](https://github.com/OpenRefine/OpenRefine/wiki/Documentation-For-Users) 
