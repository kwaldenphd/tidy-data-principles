# Tidy Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Goals

This lab provides an overview of tidy data principles (Wickham et al). It covers how to recognize and address pattern errors in structured data using the data cleaning tool Open Refine and common spreadsheet programs like Microsoft Excel or Google Sheets. It also covers how to use survey design and data validation options to minimize user error in data entry.

By the end of this lab, students will be able to:
- Understand the core components and principles of tidy data
- Recognize pattern errors in structured datasets
- Understand how to approach data cleaning and wrangling using OpenRefine and spreadsheet programs
- Understand the affordances of survey design and data validation as part of data entry/wrangling workflows

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=988247ce-5e46-4369-ac15-ae3e018ab956">Lecture/live coding playlist</a></td>
  </tr>
  </table>

## Acknowledgements
The author consulted the following resources when building this tutorial:
- [Library Carpentry "Tidy Data for Librarians"](https://librarycarpentry.org/lc-spreadsheets/)
- [Library Carpentry "Database Design"](https://librarycarpentry.org/lc-sql/08-database-design/index.html)
- [Library Carpentry "Open Refine"](https://librarycarpentry.org/lc-open-refine/)

# Table of Contents

- [Lecture & Live Coding](#lecture--live-coding)
- [Lab Notebook Template](#lab-notebook-template)
- [Data](#data)
- [Tools](#tools)
- [Tidy Data Principles](#tidy-data-principles)
  * [What Are the Principles](#what-are-the-principles)
  * [Common Spreadsheet Errors](#common-spreadsheet-errors)
  * [Dealing With Messy Data](#dealing-with-messy-data)
    * [Identify Patterns and Brainstorm Solutions](#identify-patterns-and-brainstorm-solutions)
    * [Data Wrangling Using OpenRefine](#data-wrangling-using-openrefine)
    * [Data Wrangling Using a Spreadsheet Program](#data-wrangling-using-a-spreadsheet-program)
      * [Microsoft Excel](#microsoft-excel)
	  * [Google Sheets](#google-sheets)
- [Workflows for Data Entry](#workflows-for-data-entry)
  * [Survey Versus Spreadsheet](#survey-versus-spreadsheet)
  * [Data Validation](#data-validation)
- [Lab Notebook Questions](#lab-notebook-questions)

# Lecture & Live Coding

Throughout this lab, you will see a Panopto icon at the start of select sections.

This icon indicates there is lecture/live coding asynchronous content that accompanies this section of the lab. 

You can click the link in the figure caption to access these materials (ND users only).

Example:

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=988247ce-5e46-4369-ac15-ae3e018ab956">Lecture/live coding playlist</a></td>
  </tr>
  </table>

# Lab Notebook Template

[Link to lab notebook template (Google Doc)](https://docs.google.com/document/d/1ccLZghZq-CpNc-iGTHp2XnEAfSKkLKALLZTyCYIeoP8/copy)
- Screenshots (as needed) are HIGHLY RECOMMENDED.
  * Windows ([Snipping Tool](https://support.microsoft.com/en-us/windows/use-snipping-tool-to-capture-screenshots-00246869-1843-655f-f220-97299b865f6b) for folks running older versions of Windows; [Snip & Sketch](https://www.lifewire.com/snip-and-sketch-windows-10-4774799) for folks running updated versions)
  * [Mac](https://support.apple.com/en-us/HT201361)
  * [Google Chromebook](https://support.google.com/chromebook/answer/10474268?hl=en)
- [Tutorial for adding images/tables/drawings to a Google Doc](https://www.techrepublic.com/article/how-to-add-images-tables-and-drawings-to-a-google-doc-file/)

# Data

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=988247ce-5e46-4369-ac15-ae3e018ab956">Lecture/live coding playlist</a></td>
  </tr>
  </table>

The following data files are used in this tutorial, with Google Drive links (ND users only) provided below:
- Google Sheets project with all needed files:
  * [`Combined_Workbook.xlsx`](https://docs.google.com/spreadsheets/d/1kkvPaW1nzLVa4RzKlb71nqNqU4NE7lQyESipY_W9Gw8/copy)
- Individual CSV files:
  * [`Player_Birthplaces.csv`](https://drive.google.com/file/d/1Z2eCMvuMgbgZ1V1UGkRODYDkwBdtl564/view?usp=sharing)
  * [`Team_Locations.csv`](https://drive.google.com/file/d/1ORzrTd9Gz86scESFPb72rAdwagn9dxqr/view?usp=sharing)

You can also download the files in a compressed folder (`.zip`): [Google Drive link, ND users](https://drive.google.com/file/d/13VYKrh-ftTxRqB-zrHQM2okmV9nFhFq7/view?usp=sharing)

# Tools

We'll be opening some structured data files as part of our work in this lab. You can use a spreadsheet program or text editor to access these files.

  * Text editors:
    * [TextEdit (Mac)](https://support.apple.com/guide/textedit/welcome/mac)
    * [Notepad](https://www.microsoft.com/en-us/p/windows-notepad/9msmlrh6lzf3) or [Notepad++](https://notepad-plus-plus.org/) (Windows)
    * [Atom](https://atom.io/), [Brackets](https://brackets.io/) (free download options for Mac and Windows)
    * [Text (Chromebook)](https://chrome.google.com/webstore/detail/text/mmfbcljfglbokpmkimbfghdkjmjhdgbg?hl=en)  
  * Spreadsheet programs:
    * [Microsoft Excel (Windows or Mac)](https://nd.service-now.com/nd_portal?id=kb_article&sys_id=cf15b58edbaa3058310fa94ed3961935)
      * ND students have free access to the Microsoft Office suite through Office365
    * [Apple Numbers (Mac)](https://www.apple.com/numbers/)
    * [LibreCalc (open source Excel/Numbers alternative for Mac or Windows users)](https://www.libreoffice.org/download/download/)
    * [Google Sheets (web-based option available through Google Drive)](https://www.google.com/sheets/about/)

We'll also be working with a free software program called OpenRefine as part of our work in this lab.
  * Navigate to https://openrefine.org/download.html in a web browser and download the appropriate version for your operating system.
  * If you are getting memory-related error messages, visit https://docs.openrefine.org/manual/installing#increasing-memory-allocation to troubleshoot.

# Tidy Data Principles

Hadley Wickham's 2014 article in the *Journal of Statistical Software* outlines the foundations and principles of tidy data. These principles have become widely used in data science and other statistical software applications. 
* <em>"A huge amount of effort is spent cleaning data to get it ready for analysis, but there has been little research on how to make data cleaning as easy and effective as possible. This paper tackles a small, but important, component of data cleaning: data tidying. Tidy datasets are easy to manipulate, model and visualize, and have a specific structure: each variable is a column, each observation is a row, and each type of observational unit is a table. This framework makes it easy to tidy messy datasets because only a small set of tools are needed to deal with a wide range of un-tidy datasets. This structure also makes it easier to develop tidy tools for data analysis, tools that both input and output tidy datasets. The advantages of a consistent data structure and matching tools are demonstrated with a case study free from mundane data manipulation chores." (Hadley Wickham, Tidy Data, Vol. 59, Issue 10, Sep 2014, Journal of Statistical Software. http://www.jstatsoft.org/v59/i10.)</em>

To prepare for this lab, we read Karl W. Broman and Kara H. Woo's 2018 "Data Organization in Spreadsheets" from *The American Statistician*. 
* <em>"Spreadsheets are widely used software tools for data entry, storage, analysis, and visualization. Focusing on the data entry and storage aspects, this article offers practical recommendations for organizing spreadsheet data to reduce errors and ease later analyses. The basic principles are: be consistent, write dates like YYYY-MM-DD, do not leave any cells empty, put just one thing in a cell, organize the data as a single rectangle (with subjects as rows and variables as columns, and with a single header row), create a data dictionary, do not include calculations in the raw data files, do not use font color or highlighting as data, choose good names for things, make backups, use data validation to avoid data entry errors, and save the data in plain text files." (Karl W. Broman & Kara H. Woo (2018) Data Organization in Spreadsheets, The American Statistician, 72:1, 2-10, DOI: 10.1080/00031305.2017.1375989)</em>

## What Are the Principles

Designing spreadsheets that are “tidy, consistent, and as resistant to mistakes as possible” (2)

1. Be Consistent:
  * Use consistent codes for categorical variables
  * Use a consistent fixed code for any missing values
  * Use consistent variable names
  * Use consistent subject identifiers
  * Use a consistent data layout in multiple files
  * Use consistent file names
  * Use a consistent format for all dates
  * Use consistent phrases in your notes
  * Be careful about extra spaces within cells

2. Choose Good Names for Things:
  * Avoid spaces
  * Avoid special characters
  * Be short but meaningful

3. Write Dates as YYYY-MM-DD
  * Or have separate columns for YEAR, MONTH, DATE

4. No Empty Cells

5. Put Just One Thing in a Cell

6. Make it a Rectangle
  * Single first row with variable names

7.- Create a Data Dictionary
  * “This is part of the metadata that you will want to prepare: information about the data” (6)
  * You might also find this information in a codebook that goes with a dataset
  * Things to include:
    * The exact variable name as in the data file
    * A version of the variable name that might be used in data visualizations
    * A longer explanation of what the variable means
    * The measurement units
    * Expected minimum and maximum values

8. No Calculations in the Raw Data Files

9. Do Not Use Font Color or Highlighting as Data

10. Make Backups
  * Multiple locations (OneDrive, local computer, etc.)
  * Version control program (i.e. Git)
  * Write protect the file when not entering data

11. Use Data Validation to Avoid Errors

12. Save a Copy of the Data in Plain Text Files
  * File formats can include comma-separated values (CSV) or plain-text (TXT)
  
The principles are also available as a PDF:
  * [GitHub](https://github.com/kwaldenphd/tidy-data-principles/blob/main/QualData_TidyData_Principles.pdf)
  * [Google Drive](https://drive.google.com/file/d/1lUvFePf00JfU5jMLa9zuiCcadCiFKJcR/view?usp=sharing)

## Common Spreadsheet Errors

As described in Library Carpentry's ["Tidy data for librarians" tutorial](https://librarycarpentry.org/lc-spreadsheets/02-common-mistakes/index.html), common formatting problems for data in spreadsheets include:

- Multiple tables
- Multiple tabs
- Not filling in zeros
- Using bad null values
- Using formatting to convey information
- Using formatting to make the data sheet look pretty
- Placing comments or units in cells
- More than one piece of information in a cell
- Field name problems
- Special characters in data
- Inclusion of metadata in data table
- Date formatting

<blockquote>Q1: What questions do you have about these principles? Which ones are unclear or confusing?</blockquote>
 
# Dealing With Messy Data

Double check that you have the needed data files for this lab.

- Google Sheets project with all needed files:
  * [`Combined_Workbook.xlsx`](https://docs.google.com/spreadsheets/d/1kkvPaW1nzLVa4RzKlb71nqNqU4NE7lQyESipY_W9Gw8/copy)
- Individual CSV files:
  * [`Player_Birthplaces.csv`](https://drive.google.com/file/d/1Z2eCMvuMgbgZ1V1UGkRODYDkwBdtl564/view?usp=sharing)
  * [`Team_Locations.csv`](https://drive.google.com/file/d/1ORzrTd9Gz86scESFPb72rAdwagn9dxqr/view?usp=sharing)

Open the the `Combined_Workbook` file in a spreadsheet program (you can also open the two `.csv` files in a spreadsheet program or text editor).

  * Text editors:
    * [TextEdit (Mac)](https://support.apple.com/guide/textedit/welcome/mac)
    * [Notepad](https://www.microsoft.com/en-us/p/windows-notepad/9msmlrh6lzf3) or [Notepad++](https://notepad-plus-plus.org/) (Windows)
    * [Atom](https://atom.io/), [Brackets](https://brackets.io/) (free download options for Mac and Windows)
    * [Text (Chromebook)](https://chrome.google.com/webstore/detail/text/mmfbcljfglbokpmkimbfghdkjmjhdgbg?hl=en)  
* Spreadsheet programs:
    * [Microsoft Excel (Windows or Mac)](https://nd.service-now.com/nd_portal?id=kb_article&sys_id=cf15b58edbaa3058310fa94ed3961935)
      * ND students have free access to the Microsoft Office suite through Office365
    * [Apple Numbers (Mac)](https://www.apple.com/numbers/)
    * [LibreCalc (open source Excel/Numbers alternative for Mac or Windows users)](https://www.libreoffice.org/download/download/)
    * [Google Sheets (web-based option available through Google Drive)](https://www.google.com/sheets/about/)

Explore the tables tables (sheets/tabs in the combined workbook or separate `.csv` files), thinking about the types of information included or represented in different tables and fields

<blockquote>Q2: Explore both tables, thinking about what fields are represented in these datasets. Describe the data fields in your own words.</blockquote>

Type | Description | Example
--- | --- | ---
String | Used to store text or a string of non-integer characters | "This classroom is in Bond Hall" or "student"
Integer | Used to store positive or negative whole numbers | -25, 0, 25
Double | Used to store precise numerical values that include decimal points | 3.14159265359
 
## Identify Patterns and Brainstorm Solutions

Compare what you see in these tables to the tidy data principles outlined above. Start by looking for small-scale discrepencies and inconsistencies within the datasets.

<blockquote>Q3: Provide three (3) distinct examples from the sample datasets that do not conform to tidy data principles. Include the example as well as an explanation of how this example does not conform to tidy data principles.</blockquote>

<blockquote>Q4: Take a step back and consider the pattern errors you're seeing in these datasets. What trends do you notice? Any thoughts or ideas as to how or why these pattern errors might have occurred?</blockquote>

<blockquote>Q5: How would you address these pattern errors so the data conforms to tidy data principles? Explain what steps you would take to address at least 3 pattern errors. Each error explanation should include three parts:
<ol type="a">
<li>an example of the error</li>
<li>an explanation of your method to address the error</li>
<li>the same example as tidy data</li>
</ol>
</blockquote>

# Data Wrangling Using OpenRefine

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<blockquote><p>OpenRefine is described as 'a power tool for working with messy data' (<a href="http://web.archive.org/web/20141021040915/http://davidhuynh.net/spaces/nicar2011/tutorial.pdf">David Huynh</a>) - but what does this mean? It is probably easiest to describe the kinds of data OpenRefine is good at working with and the sorts of problems it can help you solve.</p>
<br>
<p>OpenRefine is most useful where you have data in a simple tabular format such as a spreadsheet, a comma separated values file (csv) or a tab delimited file (tsv) but with internal inconsistencies either in data formats, or where data appears, or in terminology used. OpenRefine can be used to standardize and clean data across your file.</p><br>
It can help you:
<ul>
<li>Get an overview of a data set</li>
<li>Resolve inconsistencies in a data set, for example standardizing date formatting</li>
<li>Help you split data up into more granular parts, for example splitting up cells with multiple authors into separate cells</li>
<li>Match local data up to other data sets, for example in matching local subjects against the Library of Congress Subject Headings</li>
<li>Enhance a data set with data from other sources</li>
</ul>
<br>
Some common scenarios where you might use OpenRefine include:
<ul><li>Where you want to know how many times a particular value (name, publisher, subject) appears in a column in your data</li>
<li>Where you want to know how values are distributed across your whole data set</li>
<li>Where you have a list of dates which are formatted in different ways, and want to change all the dates in the list to a single common date format."</li></ul>
</blockquote>

## Installing and Loading Data in OpenRefine

We'll also be working with a free software program called OpenRefine as part of our work in this lab. Navigate to https://openrefine.org/download.html in a web browser and download the appropriate version for your operating system.
- If you are getting memory-related error messages, visit https://docs.openrefine.org/manual/installing#increasing-memory-allocation to troubleshoot.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_1.png?raw=true" alt="Capture_2"  /></p>

Launch OpenRefine and click `Create Project` from the menu on the left-hand side. 

Select the option to `Get data from This Computer`, and select `Player_Birthplaces.csv` file. Click `Next.`

<img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_2.png?raw=true" alt="Capture_2"  /></p>

You now have a variety of configuration options before creating your project in OpenRefine. 
- Select an appropriate character encoding schema.
- Select the option to `Parse next 1 line(s) as column headers.` 
  * This option treats the first row of your file as a table header.
- Check to be sure the `Parse cell text into numbers, dates, ...` option is NOT selected. 
- In the `Project name` window, name your project. 

Click `Create Project >>` to begin to work with your data as an OpenRefine project. 

## OpenRefine's Layout

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_3.png?raw=true" alt="Capture_2"  /></p>

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<blockquote>
<p>"OpenRefine displays data in a tabular format. Each row will usually represent a ‘record’ in the data, while each column represents a type of information. This is very similar to how you might view data in a spreadsheet or database. As with a spreadsheet, the individual bits of data live in ‘cells’ at the intersection of a row and a column.</p>
<br>
<p>OpenRefine only displays a limited number of rows of data at one time. You can adjust the number choosing between 5, 10 (the default), 25 and 50 at the top left of the table of data. You can navigate through the records by using the previous/next/first/last navigation options at the top right of the table of data."</p></blockquote>

## Faceting and Filtering

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<blockquote><p>"Facets are one of the most useful features of OpenRefine and can help in both getting an overview of the data and to improve the consistency of the data.</p>
<br>
<p>A ‘Facet’ groups all the values that appear in a column, and then allows you to filter the data by these values and edit values across many records at the same time.</p>
<br>
<p>The simplest type of Facet is called a ‘Text facet’. This simply groups all the text values in a column and lists each value with the number of records it appears in. The facet information always appears in the left hand panel in the OpenRefine interface.</p>
<br>
<p>To create a Text Facet for a column, click on the drop down menu at the top of the publisher column and choose `Facet -> Text Facet`. The facet will then appear in the left hand panel.</p>
<br>
<p>The facet consists of a list of values used in the data. You can filter the data displayed by clicking on one of these headings.</p>
<br>
<p>You can include multiple values from the facet in a filter at one time by using the `Include` option which appears when you put your mouse over a value in the Facet.</p>
<br>
<p>You can also invert the filter to show all records which do not match your selected values. This option appears at the top of the Facet panel when you select a value from the facet to apply as a filter."</p></blockquote>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_4.png?raw=true" alt="Capture_2"  /></p>

Select the drop-down arrow for one of the columns that contains a pattern error. Select `Facet > Text Facet`. 

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_5.png?raw=true" alt="Capture_2"  /></p>

The facet will now appear on the left-hand side of the page. Click a line in the facet to select rows with that value.
- Use the `Include` option to select multiple values.
- Use the `Edit` option to address a pattern error.

Do this for other pattern errors. Consult the following resources as needed to understand this data:
- [ISO 3166 country code table (Wikipedia)](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Decoding_table)
- [United Nations geographic regions](https://unstats.un.org/unsd/methodology/m49/)
- [USPS list of state abbreviations](https://about.usps.com/who-we-are/postal-history/state-abbreviations.htm)
- [Wikipedia list of baseball team abbreviations](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Baseball/Team_abbreviations)
- [Wikipedia glossary of baseball jargon](https://en.wiktionary.org/wiki/Appendix:Glossary_of_baseball)

## Exporting from OpenRefine

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_6.png?raw=true" alt="Capture_2"  /></p>

Click on the `Export` button in the top right-hand corner and select the option to export your OpenRefine project as a CSV file. 

<blockquote>NOTE: OpenRefine will only export the rows of data selected in your current review. Be sure to remove all filters or facets before exporting.</blockquote>

Make sure this file has a unique name and is saved in a location where you can find it again. Open this new CSV file in a spreadsheet program. Check to see the pattern errors have been addressed.

Go through this same process for the `Team_Locations.csv` file.

<blockquote>Q6: Compare your experience working in OpenRefine to other experiences you have had in a text editor or spreadsheet program. In what ways do you understand, perceive, or relate to the data differently through working in OpenRefine? Describe your experience cleaning this data in OpenRefine.</blockquote>

We are barely scratching the surface of what is possible with data wrangling in OpenRefine. The progam can also standardize capitalization, remove leading and trailing spaces, and address other commonly-found data errors. [Library Carpentry's OpenRefine tutorial](https://librarycarpentry.org/lc-open-refine/) goes in to greater detail about many of these other functions.
 
# Data Wrangling Using A Spreadsheet Program

Spreadsheet software programs are another commonly-used tool for interacting with structured data. Some spreadsheet programs like Microsoft Office's Excel or Apple's Numbers are proprietary software installed on a local computer. Other proprietary spreadsheet programs like Google Sheets run online and are not installed locally. Open-source spreadsheet programs include OpenOffice's Calc and LibreOffice's Calc. 

<blockquote>Q7: Describe a past experience working with a spreadsheet program. What were you trying to do? How did it go? What was your overall feeling about working with data in a spreadsheet program?</blockquote>

There are two options for the next section of the lab- working in Google Sheets or Microsoft Excel. You are only expected to complete one of those options. For either option, the workflow covered in this section of the lab loads individual tables into a workbook and uses spreadsheet program tools to interact with and clean (or "tidy") the data.

  * [Microsoft Excel](#microsoft-excel)
    * Steps 76-95
  * [Google Sheets](#google-sheets)
    * Steps 96-134

## Microsoft Excel

### Loading Data

There are two options for loading data files in Excel.
  * Import CSV files
  * Open Excel workbook

#### Loading Data From CSV Files

Open a blank Microsoft Excel file. Save the blank file as an Excel workbook.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_7.png?raw=true" alt="Capture_2"  /></p>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figA.jpg?raw=true" alt="Capture_2"  /></p>

Click on `Data` in the top menu bar. Under `Get Data` select the `From Text/CSV` option. In `Sheet1`, select the `Player_Birthplaces.csv` file.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figB.jpg?raw=true" alt="Capture_2"  /></p>

In the pop-up window, make sure `Comma` is selected as the delimiter, and switch `File Origin` to `UTF-8`. Click `Load`

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_17.png?raw=true" alt="Capture_2"  /></p>

You should now see the CSV data in the Excel workbook. Go through the same process for the `team_locations.csv` file. Save the updated workbook.

#### Loading Data as an Excel Workbook

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figC.jpg?raw=true" alt="Capture_2"  /></p>

Alternatively, you can download the Google Sheets file as an Excel workbook (`.xlsx`). That workbook file includes both tables needed for this lab.

### Data Cleaning in Excel

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_18.png?raw=true" alt="Capture_2"  /></p>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_19.png?raw=true" alt="Capture_2"  /></p>
 
Click the drop-down arrow next to a column header to see additional options for that field. Use these sort, search, and filter options to address data pattern errors.

#### Find and Replace

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_20.png?raw=true" alt="Capture_2"  /></p>

Alternatively, use the `Replace` option under `Find & Select` (in the `Home` menu section) to address pattern errors.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figAA.jpg?raw=true" alt="Capture_2"  /></p>

Click the `Options` button to see additional options.
 
Consult the following resources as needed to understand this data:
- [ISO 3166 country code table (Wikipedia)](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Decoding_table)
- [United Nations geographic regions](https://unstats.un.org/unsd/methodology/m49/)
- [USPS list of state abbreviations](https://about.usps.com/who-we-are/postal-history/state-abbreviations.htm)
- [Wikipedia list of baseball team abbreviations](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Baseball/Team_abbreviations)
- [Wikipedia glossary of baseball jargon](https://en.wiktionary.org/wiki/Appendix:Glossary_of_baseball)

<blockquote>To change all cells in a column, click the cell in the first non-header row. Press <code>Control</code> or <code>Command</code> and the down arrow key to select all cells with data in that column. Press <code>Control/Command</code> and <code>D</code> to copy the first value into the other selected cells. Alternatively, move your cursor over the bottom right-hand corner of the cell in the first non-header row. Click and drag the plus icon that appears down through the column to copy the value in the first cell into the subsequent cells.</blockquote>

Go through this same process for the `team_locations` table.

### Saving and Exporting in Excel

The default file type in Microsoft Excel is an Excel workbook (`.xlsx`).

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_21.png?raw=true" alt="Capture_2"  /></p>

Click on the `File` menu section to show additional export options. Under `Export` you can see some of the other options for exporting the data in Excel.
  * While plain-text formats (tab separated values, `tsv`; comma separated values, `csv`, etc) are best for digital preservation and interoperability, they only accept a single table.

## Google Sheets

### Loading Data

There are two options for loading data files in Google Sheets.
  * Import CSV files
  * [Copy Google Sheets project](https://docs.google.com/spreadsheets/d/1kkvPaW1nzLVa4RzKlb71nqNqU4NE7lQyESipY_W9Gw8/edit?usp=sharing)

#### Loading Data From CSV Files

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figD.jpg?raw=true" alt="Capture_2"  /></p>

Open a blank Google Sheets project. Replace `Untitled spreadsheet` in the top-left hand corner with a meaningful file name.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figE.jpg?raw=true" alt="Capture_2"  /></p>

Select `Import` under `File` in the top-level menu.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figF.jpg?raw=true" alt="Capture_2"  /></p>

Select the option to `Upload` a file from your local computer, or drag and drop the `player_birthplaces.csv` file. Click `Select`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figG.jpg?raw=true" alt="Capture_2"  /></p>

A few settings to check before we import:
  * Change the `Import Location` to `Insert new sheet(s)`
  * Select `Comma` as the `Separator type`
  * Uncheck the `Convert text to numbers, dates, and formulas` box
  
Click `Import data`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figH.jpg?raw=true" alt="Capture_2"  /></p>

The `player_birthplaces` table is now loaded in Google Sheets. Go through the same workflow for the `team_locations.csv` file.

#### Copying the Google Sheets Project

Alternatively, you can [make a copy of the Google Sheets project](https://docs.google.com/spreadsheets/d/1kkvPaW1nzLVa4RzKlb71nqNqU4NE7lQyESipY_W9Gw8/copy) to your local Drive. The Google Sheets project includes both tables needed for this lab.

### Data Cleaning in Google Sheets

#### Freezing the Header Row

The first thing we want to do is freeze the first row in the table, which has our column headers. This way when we start sorting specific columns, the column labels will not be affected.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figI.jpg?raw=true" alt="Capture_2"  /></p>

Click `View` on the top-level menu, and select `Freeze`. Click `1 row` to freeze the first row in the table.

#### Sorting

Then, we can select a single column to sort by character or number values.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figJ.jpg?raw=true" alt="Capture_2"  /></p>

Right click on a column label and select one of the `Sort sheet` options.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figK.jpg?raw=true" alt="Capture_2"  /></p>

Or, click `Data` -> `Sort sheet` -> `Sort range` to sort by a particular column or selection. We can also sort by multiple columns.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figL.jpg?raw=true" alt="Capture_2"  /></p>

Click `Data` -> `Sort range` -> `Advanced range sorting options` to access these options.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figM.jpg?raw=true" alt="Capture_2"  /></p>

In the pop-up window, you can check the `Data has header row` box and then choose to sort by multiple columns. Click `Sort` to apply these settings.

#### Filters

We can also add filters to only see specific rows or values.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figN.jpg?raw=true" alt="Capture_2"  /></p>

Click `Create a filter` under `Data`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figO.jpg?raw=true" alt="Capture_2"  /></p>

Now we can set up filters for individual columns in the table.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figP.jpg?raw=true" alt="Capture_2"  /></p>

Click on the three horizontal lines next to a column label to open the filter menu.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figQ.jpg?raw=true" alt="Capture_2"  /></p>

One option is to filter by condition.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figR.jpg?raw=true" alt="Capture_2"  /></p>

Another option is to filter by values, which allows you to search for particular characters or select specific values. Click `OK` to apply the filter.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figS.jpg?raw=true" alt="Capture_2"  /></p>

Google Sheets allows you to save particular filter settings/configurating as a `Filter view`.
  * `Data` -> `Filter views` -> `Save as filter view`
  
<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figT.jpg?raw=true" alt="Capture_2"  /></p>

You can also remove any filters from the Google Sheets project.
  * `Data` -> `Remove filter`

#### Find and Replace in Google Sheets

Google Sheets also supports find and replace operations.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figX.jpg?raw=true" alt="Capture_2"  /></p>

Click `Find and replace` under the `Edit` menu tab.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figY.jpg?raw=true" alt="Capture_2"  /></p>

Google Sheets gives you options to match by case or for an entire cell's contents. You can also search using regular expressions.
- To learn more: ["Find and replace items using regular expressions,"](https://support.google.com/docs/answer/62754?p=spreadsheets_find_replace&visit_id=1644265064793-8550767213078292457&rd=1) Google Docs Support

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figZ.jpg?raw=true" alt="Capture_2"  /></p>

Click on the `Search` drop-down menu to see additional options for searching in Google Sheets.

### Saving and Exporting in Google Sheets

Google Sheets projects are cloud-based, which means they are stored online (in the cloud).

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figU.jpg?raw=true" alt="Capture_2"  /></p>

Click on the `File` - `Download` menu to show export options.

Under `Download` you can see some of the other options for exporting the data.
- An Excel workbook (`.xlsx`) supports multiple tables or sheets in a single workbook file.
- Plain-text formats (tab separated values, `tsv`; comma separated values, `csv`, etc) are best for digital preservation and interoperability, but they only accept a single table.

## Additional Resources and Next Steps

<blockquote>Q8: Compare your experience working in a spreadsheet program (Excel or Google Sheets) to your experience working in OpenRefine. In what ways do you understand, perceive, or relate to the data differently through working in a spreadsheet program? Describe your experience cleaning this data in a spreadsheet program.</blockquote>

We are barely scratching the surface of what is possible with data wrangling in Excel or Google Sheets. The progam can also standardize capitalization, remove leading and trailing spaces, and address other commonly-found data errors. 
- For more on Excel: [Library Carpentry's Tidy Data for Librarians tutorial](https://librarycarpentry.org/lc-spreadsheets/) goes in to greater detail about many of these other functions.
- For more on Google Sheets: [10 Google Workspace tips to clean up data](https://support.google.com/a/users/answer/9604139?hl=en)

# Workflows for Data Entry

<blockquote>Q9: For the baseball datasets we have been working with in this lab, what do you think may have contributed to or caused the pattern errors we needed to address? How could these pattern errors be addressed in the data entry process?</blockquote>

According to Library Carpentry's [Tidy Data for Librarians tutorial](https://librarycarpentry.org/lc-spreadsheets/04-quality-control/index.html), "Quality assurance stops bad data from ever being entered by checking to see if values are valid during data entry. For example, if research is being conducted at sites A, B, and C, then the value V (which is right next to B on the keyboard) should never be entered. Likewise if one of the kinds of data being collected is a count, only integers greater than or equal to zero should be allowed."

Building in quality assurance constraints into a data entry workflow can help minimize pattern errors that require later cleaning.

## Survey Versus Spreadsheet

One option is use a survey with some pre-defined choices or drop-down options. Log into your Notre Dame Google Drive account.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_22.png?raw=true" alt="Capture_2"  /></p>

Select the option to create a Google Form. Click on the `Blank Form` option.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_23.png?raw=true" alt="Capture_2"  /></p>

Explore the different question types. 

<blockquote>Q10: Describe how you would go about building a survey form or template for the <code>Tidy_Data_Lab_PlayerBirthplaces.csv</code> file. You DO NOT need to actually create or submit a survey form. Describe what types of questions and pre-defined question or field options could you use to more effectively generate the data in this file.</blockquote>

## Data Validation

You can also use some of the built-in data validation options in a spreadsheet program.
- [Microsoft Excel](#data-validation-in-excel)
- [Google Sheets](#data-validation-in-google-sheets)

### Data Validation in Excel

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_24.png?raw=true" alt="Capture_2"  /></p>

Under `Data`, select the `Data Validation` option.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_25.png?raw=true" alt="Capture_2"  /></p>

In the pop-up window, you can limit the  types of values that will be valid in a particular field. You can also define a list of options or values which will show up as drop-down options for cells in that field.

Visit Microsoft Office's ["Apply data validation to cells"](https://support.office.com/en-us/article/apply-data-validation-to-cells-29fecbcc-d1b9-42c1-9d76-eff3ce5f7249) article to learn more about data validation options.

### Data Validation in Google Sheets

Google Sheets also supports some data validation operations.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figV.jpg?raw=true" alt="Capture_2"  /></p>

Select `Data validation` under the `Data` menu tab.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figBB.jpg?raw=true" alt="Capture_2"  /></p>

You can customize the cell range for specific validation settings.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/figW.jpg?raw=true" alt="Capture_2"  /></p>

The `Criteria` drop-down list includes as range of options for data validation settings.

Visit Zapier's ["What is data validation in Google Sheets?"](https://zapier.com/blog/data-validation-google-sheets/) article to learn more about data validation options.

<blockquote>Q11: Describe how you would go about using data validation to build a template for the <code>player_birthplaces.csv</code> file. You DO NOT need to actually create or submit a template. Describe what data validation options and pre-defined field options could you use to more effectively generate the data in this file.</blockquote>

# Lab Notebook Questions

[Link to lab notebook template (Google Doc)](https://docs.google.com/document/d/1ccLZghZq-CpNc-iGTHp2XnEAfSKkLKALLZTyCYIeoP8/copy)
- Screenshots (as needed) are HIGHLY RECOMMENDED.
  * Windows ([Snipping Tool](https://support.microsoft.com/en-us/windows/use-snipping-tool-to-capture-screenshots-00246869-1843-655f-f220-97299b865f6b) for folks running older versions of Windows; [Snip & Sketch](https://www.lifewire.com/snip-and-sketch-windows-10-4774799) for folks running updated versions)
  * [Mac](https://support.apple.com/en-us/HT201361)
  * [Google Chromebook](https://support.google.com/chromebook/answer/10474268?hl=en)
- [Tutorial for adding images/tables/drawings to a Google Doc](https://www.techrepublic.com/article/how-to-add-images-tables-and-drawings-to-a-google-doc-file/)

Q1: What questions do you have about these principles? Which ones are unclear or confusing?

Q2: Explore both tables, thinking about what fields are represented in these datasets. Describe the data fields in your own words- what types of information do they contain, and what types of data are you seeing?

Q3: Provide 3 distinct examples from the sample datasets that do not conform to tidy data principles. Include the example as well as an explanation.

Q4: Take a step back and consider the pattern errors you're seeing in these datasets. What trends do you notice? Any thoughts or ideas as to how or why these pattern errors might have occurred?

Q5: How would you address these pattern errors so the data conforms to tidy data principles? Explain what steps you would take to address at least 3 pattern errors. Each error explanation should include three parts:
<ol type="a">
<li>an example of the error</li>
<li>an explanation of your method to address the error</li>
<li>the same example as tidy data</li>
</ol>

Q6: Compare your experience working in OpenRefine to other experiences you have had in a text editor or spreadsheet program. In what ways do you understand, perceive, or relate to the data differently through working in OpenRefine? Describe your experience cleaning this data in OpenRefine.

Q7: Describe a past experience working with a spreadsheet program. What were you trying to do? How did it go? What were some of your overall impressions about working with data in a spreadsheet program?

Q8: Compare your experience working in a spreadsheet program to your experience working in OpenRefine. In what ways do you understand, perceive, or relate to the data differently through working in Excel? Describe your experience cleaning this data in a spreadsheet program.

Q9: For the baseball datasets we have been working with in this lab, what do you think may have contributed to or caused the pattern errors we needed to address? How could these pattern errors be addressed in the data entry process?

Q10: Describe how you would go about building a survey form or template for the `player_birthplaces.csv` file. You DO NOT need to actually create or submit a survey form. Describe what types of questions and pre-defined question or field options could you use to more effectively generate the data in this file.

Q11: Describe how you would go about using data validation to build a template for the `player_birthplaces.csv` file. You DO NOT need to actually create or submit a template. Describe what data validation options and pre-defined field options could you use to more effectively generate the data in this file.
