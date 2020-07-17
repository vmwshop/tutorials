# OpenRefine Tutorial

## Objectives

By the end of this tutorial, you should be able to use Facets to clean up messy data and filter and export exactly what you need.

## What You Need
- Computer with an internet browser and internet connection
- A dataset - ideally something on the larger size (i.e. tens or hundreds of thousands of data points)
    - This can be uploaded as a file in many different formats (csv, json, wiki, xls, etc.), from a webpage, or even via copy/paste as text

## About OpenRefine

OpenRefine (previously Google Refine) is a powerful, opensource tool for working with messy data. Clean up small to large mistakes en masse, convert data from one format to another, and add to a dataset by pulling data from an online source into your dataset. OpenRefine is an app that is downloaded to your personal computer that then uses your internet browser to interact with it. While it might look as though you are uploading your data to the internet through your browser, the data is in fact still being locally hosted on your hard drive. 

### What Can It Be Used For?
- Clean up messy data
- Combine data from a website with an outside dataset
- Convert a dataset from one format to another

## Get Started

To get started, there is no account sign up! All you need to do is visit **[the OpenRefine Downloads Page](https://openrefine.org/download.html)** and pick the download kit that is applicable to your operating system. 

> _NOTE_: If using a Mac, you may get a security warning that your computer doesn’t recognize the developer and won’t let you open the application. If that is the case, then go to your System Settings > Security & Privacy > Click the lock icon in the bottom left corner of the window > Click the _“Open Anyway”_ button in the _“Allow apps downloaded from”_ section of your General
Settings. Open it again and you should be good to go!

Once you have the app downloaded and installed, simply launch the app, upload your data, and start working! As a reminder, when you launch the OpenRefine app, your default internet browser will open. This is how you interact with the application even though your data is still being hosted locally on your personal drive. So no need to worry about the security of your data! 

**1.** Click the “Choose Files” button, select your dataset, and click “Next”. For this workshop, we have pre-messed up some data for you to use HERE called Allegheny County Dog Licenses.csv. If you already have some data that you know is messy, feel free to use that and follow along with the same steps! Just be prepared for us to use different values and have different “mistakes” within our provided data than what you might have. 

<img scr="https://user-images.githubusercontent.com/15221098/87825832-d4fefa00-c845-11ea-9251-113dbb17fa6d.png" class="responsive" alt="ORgettingstarted1" width="850">

**2.** What you will see when your file is finished uploading is a preview of what your data will look like in your new project within OpenRefine. There are some other options you have here, but for this basic understanding of the tool, just click the “Create Project” button in the top right corner to continue. 

<img scr="https://user-images.githubusercontent.com/15221098/87825880-eba55100-c845-11ea-9d96-c9e4a708226a.png" class="responsive" alt="ORgettingstarted2" width="850">

**3.** Enjoy the progress bar as your project is created, then you will see the first ten rows of your data as a new OpenRefine project! You will also notice that the fine folks at OpenRefine have [provided a link to some great screencasts](https://github.com/OpenRefine/OpenRefine/wiki/Screencasts) on using filters and facets. Much of this tutorial is based on these videos, so please feel free to reference those as well. 

<img src="https://user-images.githubusercontent.com/15221098/87824197-d24ed580-c842-11ea-95ad-5a330fe90798.png" class="responsive" alt="ORgettingstarted3" width="850">

## Facets 

Facets are the bread and butter of OpenRefine when it comes to cleaning up messy data as well as sorting and filtering it. Essentially what they are is a collection of each value in each cell of your data, grouped together with a total count for each unique datapoint. When you create a “text facet,” OpenRefine automatically separates and groups them based on text and characters. 

**1.** In the Breed column of our data, click the dropdown arrow in the column header and select _Facet_ > _Text Facet_

<img src="https://user-images.githubusercontent.com/15221098/87824323-0de99f80-c843-11ea-912c-e1b001de2aff.png" class="responsive" alt="ORfacets1" width="850">

In the left sidebar, you will see a list of all of the different breeds in your dataset grouped together with a total count for each. Take a look through these carefully and you will notice that there are some that appear to be duplicates of each other. Here’s where your clean up begins. 

<img src="https://user-images.githubusercontent.com/15221098/87824431-3d98a780-c843-11ea-8f46-a70573c98b2f.png" class="responsive" alt="ORfacets2" width="850">

You will see some minor typos, find trailing spaces, etc. OpenRefine has some great built-in features to help rid your data of these quickly. The first of which lives in your facet widget in the left sidebar. Click the “Cluster” button in the top right corner of the widget. Here you will see a list of any data points that OpenRefine thinks are supposed to be the same. The “Values in Cluster” column shows you what values are up for being combined and the “New Cell Value” column shows you what OpenRefine wants to change them to. For our dataset, OpenRefine got them all right, so click the checkbox in each row in the “Merge” column (or click the “Select All” button under the table) then click “Merge Selected & Close”. 

<img src="https://user-images.githubusercontent.com/15221098/87824474-56a15880-c843-11ea-9388-31d851c126c5.png" class="responsive" alt="ORfacets3" width="850">

Take another look at your Breed facets. Scroll down until you find the “AM PIT BULL TERRIER” and “AM PIT BULL MIX” values. You will notice that they each only have one entry and right under them there are “AM PIT BULL TERRIER” AND “AM PITT BULL MIX” values with hundreds of entries each. We’ve found another typo! These are quick fixes. Simply hover over each value and click the “Edit” button that appears to the right of them. This will bring up a text box where you can manually edit the typo from “PIT BUL” to “PIT BULL”, etc. 

<img src="https://user-images.githubusercontent.com/15221098/87824514-69b42880-c843-11ea-9f3d-a5cbaebb5aa8.png" class="responsive" alt="ORfacets4" width="850">

Once you click “Apply” you will see your typo’ed value disappear and the count of the correctly spelled value increase by one. 

[[SCREENSHOT]]

Listed here are some other minor errors in the provided dataset that you can use this method to locate and correct. Scrolling through your list of facets sorted by name is a quick way to identify these by noticing lower than usual counts for values. 

- Edit the “BAGLE” value to “BEAGLE”
- Edit the “BOXTER” value to “BOXER”
- Edit the “MATLEESE” value to “MALTESE”
- Edit the “MIX” VALUE to “MIXED”

### Other Quick Edits

#### Eliminate Extra Spaces

A common issue with large datasets is trailing or leading spaces. Meaning there is a space either right before or right after the value in the cell. OpenRefine makes trimming these off of your data super easy! 

Again in the “Breed” column of your dataset, click the dropdown arrow by the column header and hover over “Edit Cells” > “ Common Transformations” > Click “Trim leading and trailing whitespace”.

[[SCREENSHOT]]

#### Split Columns with Multiple Values

Look at the “ValidDate” column of our data. You will see that the values have both a date and a time. We want a separate column for “ValidTime”. In the header of the “ValidDate” column, click the dropdown arrow and hover over “Edit column” > Click “Split into several columns”. Notice how the dates and times in the “ValidDate” cells are separated by a “T”. Enter “T” in the “Separator” box in the Split column window and click “OK”. 

[[SCREENSHOT]]

Now you have your dates and times in separate columns! Notice how OpenRefine automatically names the headers of these columns based on the original column’s name. Simply edit these by clicking the dropdown next to the header name > Hover over “Edit column” > Click “Rename this column”. 

[[SCREENSHOT]]

#### Add Text To Existing Values

Just for clarity’s sake, we want all of our pups that are designated as “MIXED” to read as “MIXED BREED”. So let’s add the word “BREED” to any occurrence of the word “MIXED” in the “Breeds” column. 

Back in your “Facets” widget, scroll down to the “MIXED” value and select it. The facet will be bolded and change to orange to signify that it’s selected. 

[[SCREENSHOT]]

With the facet selected, click the dropdown arrow in the “Breed” column header > Hover over “Edit cells” > Click “Transform…”

[[SCREENSHOT]]

Here you will use what OpenRefine calls “Google Refine Expression Language” to tell OpenRefine how you want to transform your cells. For this example, in the “Expression” box, use the following command to add your text to the existing values:

```
value+” BREED”
```

You will see a preview of your handy work in the table under the “Expression” box. Click “OK” when it looks the way you want it to. 

[[SCREENSHOT]]

### Sorting and Filtering Data

Now that your data is all cleaned up and ready for use, you can use facets to filter out what you don’t need, sort everything by a specific value, or a combination of both! 

Filtering is about as easy as it gets. Click the dropdown of the “LicenceType” column header > Hover over “Facet” > Click “Text Facet”. Let’s say we want to find out how many of our registered pups are seniors. From your facet widget in the left sidebar, hover over each of the values that include “Senior”. As you hover over each, you will see the option to either “edit” or “include”. Click “include” for each value. As you do this for each facet, they will all become bold and turn orange, signifying that they are selected. You will also notice the number of matching rows at the top of the page adjusts to show you how many rows contain our senior pups. 

[[SCREENSHOT]]

From here, you can Export your filtered data by clicking the “Export” dropdown in the top right corner of the screen and selecting your desired format. For this example, we will choose “Comma-separated value”. 

[[SCREENSHOT]]

This is one of the beauties of OpenRefine. You have now exported a filtered portion of your dataset to maybe send off to your boss or manipulate further within a different spreadsheet program, but your OpenRefine project remains right where you left off! Now you can jump back into OpenRefine and filter and export your data however else you might need to.  




##### Other Resources and References

Miriam Posner’s [“Get started with OpenRefine”](http://miriamposner.com/classes/dh101f17/tutorials-guides/data-manipulation/get-started-with-openrefine/)

