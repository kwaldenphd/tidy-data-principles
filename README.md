# Tidy Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Goals


## Acknowledgements
The author consulted the following resources when building this tutorial:
- [Library Carpentry "Tidy Data for Librarians"](https://librarycarpentry.org/lc-spreadsheets/)
- [Library Carpentry "Database Design"](https://librarycarpentry.org/lc-sql/08-database-design/index.html)
- [Library Carpentry "Open Refine"](https://librarycarpentry.org/lc-open-refine/)

# Table of Contents

- [Tidy Data Principles](#tidy-data-principles)
  * [What Are the Principles](#what-are-the-principles)
  * [Common Spreadsheet Errors](#common-spreadsheet-errors)
  * [Dealing With Messy Data](#dealing-with-messy-data)
    * [Identify Patterns and Brainstorm Solutions](#identify-patterns-and-brainstorm-solutions)
    * [Data Wrangling Using OpenRefine](#data-wrangling-using-openrefine)
    * [Data Wrangling Using a Spreadsheet Program](#data-wrangling-using-a-spreadsheet-program)
- [Workflows for Data Entry](#workflows-for-data-entry)
  * [Survey Versus Spreadsheet](#survey-versus-spreadsheet)
  * [Data Validation](#data-validation)
- [Additional Resources](#additional-resources)
- [Lab Notebook Questions](#lab-notebook-questions)

# Data

# Data

The following data files are used in this tutorial:
- `Tidy_Data_Lab_Combined_Workbook.xlsx`
- `Tidy_Data_Lab_Player_Birthplaces.csv`
- `Tidy_Data_Lab_Team_Locations.csv`
- `Tidy_Data_Lab_Combined_Transactions.csv`

They can be downloaded as a `zip` folder in this GitHub repo.

[Link to access via Google Drive (ND users only)](https://drive.google.com/drive/folders/1pmK-MqJT7aEzOBAVNNtoV5VidCCc99T8?usp=sharing)

# Tidy Data Principles

Hadley Wickham's 2014 article in the *Journal of Statistical Software* outlines the foundations and principles of tidy data. 

Article abstract: "A huge amount of effort is spent cleaning data to get it ready for analysis, but there has been little research on how to make data cleaning as easy and effective as possible. This paper tackles a small, but important, component of data cleaning: data tidying. Tidy datasets are easy to manipulate, model and visualize, and have a specific structure: each variable is a column, each observation is a row, and each type of observational unit is a table. This framework makes it easy to tidy messy datasets because only a small set of tools are needed to deal with a wide range of un-tidy datasets. This structure also makes it easier to develop tidy tools for data analysis, tools that both input and output tidy datasets. The advantages of a consistent data structure and matching tools are demonstrated with a case study free from mundane data manipulation chores." (Hadley Wickham, Tidy Data, Vol. 59, Issue 10, Sep 2014, Journal of Statistical Software. http://www.jstatsoft.org/v59/i10.)

Wickham's tidy data principles have become widely used in data science and other statistical software applications. 

To prepare for this lab, we read Karl W. Broman and Kara H. Woo's 2018 "Data Organization in Spreadsheets" from *The American Statistician*. 

Article abstract: "Spreadsheets are widely used software tools for data entry, storage, analysis, and visualization. Focusing on the data entry and storage aspects, this article offers practical recommendations for organizing spreadsheet data to reduce errors and ease later analyses. The basic principles are: be consistent, write dates like YYYY-MM-DD, do not leave any cells empty, put just one thing in a cell, organize the data as a single rectangle (with subjects as rows and variables as columns, and with a single header row), create a data dictionary, do not include calculations in the raw data files, do not use font color or highlighting as data, choose good names for things, make backups, use data validation to avoid data entry errors, and save the data in plain text files." ( Karl W. Broman & Kara H. Woo (2018) Data Organization in Spreadsheets, The American Statistician, 72:1, 2-10, DOI: 10.1080/00031305.2017.1375989)

## What Are the Principles

Designing spreadsheets that are “tidy, consistent, and as resistant to mistakes as possible” (2)

1- Be Consistent:
  * Use consistent codes for categorical variables
  * Use a consistent fixed code for any missing values
  * Use consistent variable names
  * Use consistent subject identifiers
  * Use a consistent data layout in multiple files
  * Use consistent file names
  * Use a consistent format for all dates
  * Use consistent phrases in your notes
  * Be careful about extra spaces within cells

2- Choose Good Names for Things:
  * Avoid spaces
  * Avoid special characters
  * Be short but meaningful

3- Write Dates as YYYY-MM-DD
  * Or have separate columns for YEAR, MONTH, DATE

4- No Empty Cells

5- Put Just One Thing in a Cell

6- Make it a Rectangle
  * Single first row with variable names

7- Create a Data Dictionary
  * “This is part of the metadata that you will want to prepare: information about the data” (6)
  * You might also find this information in a codebook that goes with a dataset
  * Things to include:
    * The exact variable name as in the data file
    * A version of the variable name that might be used in data visualizations
    * A longer explanation of what the variable means
    * The measurement units
    * Expected minimum and maximum values

8- No Calculations in the Raw Data Files

9- Do Not Use Font Color or Highlighting as Data

10- Make Backups
  * Multiple locations (OneDrive, local computer, etc.)
  * Version control program (i.e. Git)
  * Write protect the file when not entering data

11- Use Data Validation to Avoid Errors

12- Save a Copy of the Data in Plain Text Files
  * File formats can include comma-separated values (CSV) or plain-text (TXT)
  
The principles are also available as a PDF in this repo.

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


<blockquote>Q1: What questions do you have about these principles? Which ones are unclear are confusing?</blockquote>
 
## Dealing With Messy Data

1- Extract the contents of the `tidy_data_lab_data.zip` folder. 

2- Open the `Tidy_Data_Lab_Player_Birthplaces.csv` and `Tidy_Data_Lab_Team_Locations.csv` files in a spreadsheet program.

3- Explore both files.

<blockquote>Q2: What fields are represented in these datasets? Describe the data fields in your own words. Use the language of string, double, and integer to describe the data fields.</blockquote>

Type | Description | Example
--- | --- | ---
String | Used to store text or a string of non-integer characters | "This classroom is in Bond Hall" or "student"
Integer | Used to store positive or negative whole numbers | -25, 0, 25
Double | Used to store precise numerical values that include decimal points | 3.14159265359
 
### Identify Patterns and Brainstorm Solutions

4- Compare what you see in the `Tidy_Data_Lab_Player_Birthplaces.csv` and `Tidy_Data_Lab_Team_Locations.csv` files to the tidy data principles outlined above.

5- Start by looking for small-scale discrepencies and inconsistencies within the datasets.

<blockquote>Q3: Provide 3 distinct examples from the sample datasets that do not conform to tidy data principles. Include the example as well as an explanation.</blockquote>

<blockquote>Q4: Discuss with a colleague what issues you are seeing in these datasetes. What commonalities or patterns are you seeing?</blockquote>

<blockquote>Q5: How would you address these pattern errors so the data conforms to tidy data principles? Describe what steps you would take to address at least 3 pattern errors. For each error, include the following elements: an example of the error, an explanation of your method to address the error, and the same example as tidy data.</blockquote>

### Data Wrangling Using OpenRefine

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<em>OpenRefine is described as 'a power tool for working with messy data' ([David Huynh](http://web.archive.org/web/20141021040915/http://davidhuynh.net/spaces/nicar2011/tutorial.pdf)) - but what does this mean? It is probably easiest to describe the kinds of data OpenRefine is good at working with and the sorts of problems it can help you solve.

OpenRefine is most useful where you have data in a simple tabular format such as a spreadsheet, a comma separated values file (csv) or a tab delimited file (tsv) but with internal inconsistencies either in data formats, or where data appears, or in terminology used. OpenRefine can be used to standardize and clean data across your file. 

It can help you:
- Get an overview of a data set
- Resolve inconsistencies in a data set, for example standardizing date formatting
- Help you split data up into more granular parts, for example splitting up cells with multiple authors into separate cells
- Match local data up to other data sets, for example in matching local subjects against the Library of Congress Subject Headings
- Enhance a data set with data from other sources

Some common scenarios where you might use OpenRefine include:
- Where you want to know how many times a particular value (name, publisher, subject) appears in a column in your data
- Where you want to know how values are distributed across your whole data set
- Where you have a list of dates which are formatted in different ways, and want to change all the dates in the list to a single common date format."</em>

#### Installing and Loading Data in OpenRefine

6- Navigate to https://openrefine.org/download.html in a web browser and download the appropriate version for your OS.
- [Windows](https://github.com/OpenRefine/OpenRefine/releases/download/3.4.1/openrefine-win-with-java-3.4.1.zip)
- [Mac](https://github.com/OpenRefine/OpenRefine/releases/download/3.4.1/openrefine-mac-3.4.1.dmg)
- [Google Chromebook](https://github.com/OpenRefine/OpenRefine/releases/download/3.4.1/openrefine-linux-3.4.1.tar.gz)
  * If you are getting memory-related error messages, visit https://github.com/OpenRefine/OpenRefine/wiki/FAQ%3A-Allocate-More-Memory#linux-or-mac to troubleshoot.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_1.png?raw=true" alt="Capture_2"  /></p>

7- Launch OpenRefine.

8- Click `Create Project` from the menu on the left-hand side. 

9- Select the option to `Get data from This Computer.`

10- Select `Player_Birthplaces.csv` file.

11- Click `Next.`

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_2.png?raw=true" alt="Capture_2"  /></p>

12- You now have a variety of configuration options before creating your project in OpenRefine.

13- Select an appropriate character encoding schema.

14- Select the option to `Parse next 1 line(s) as column headers.` This option treats the first row of your file as a table header.

15- Check to be sure the `Parse cell text into numbers, dates, ...` option is NOT selected. 

16- In the `Project name` window, name your project. 

17- Click `Create Project >>` to begin to work with your data as an OpenRefine project. 

#### OpenRefine's Layout

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_3.png?raw=true" alt="Capture_2"  /></p>

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<em>"OpenRefine displays data in a tabular format. Each row will usually represent a ‘record’ in the data, while each column represents a type of information. This is very similar to how you might view data in a spreadsheet or database. As with a spreadsheet, the individual bits of data live in ‘cells’ at the intersection of a row and a column.

OpenRefine only displays a limited number of rows of data at one time. You can adjust the number choosing between 5, 10 (the default), 25 and 50 at the top left of the table of data. You can navigate through the records by using the previous/next/first/last navigation options at the top right of the table of data."</em>

#### Faceting and Filtering

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<em>Facets are one of the most useful features of OpenRefine and can help in both getting an overview of the data and to improve the consistency of the data.

A ‘Facet’ groups all the values that appear in a column, and then allows you to filter the data by these values and edit values across many records at the same time.

The simplest type of Facet is called a ‘Text facet’. This simply groups all the text values in a column and lists each value with the number of records it appears in. The facet information always appears in the left hand panel in the OpenRefine interface.

To create a Text Facet for a column, click on the drop down menu at the top of the publisher column and choose `Facet -> Text Facet`. The facet will then appear in the left hand panel.

The facet consists of a list of values used in the data. You can filter the data displayed by clicking on one of these headings.

You can include multiple values from the facet in a filter at one time by using the `Include` option which appears when you put your mouse over a value in the Facet.

You can also invert the filter to show all records which do not match your selected values. This option appears at the top of the Facet panel when you select a value from the facet to apply as a filter."</em>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_4.png?raw=true" alt="Capture_2"  /></p>

18- Select the drop-down arrow for one of the columns that contains a pattern error.

19- Select `Facet > Text Facet`. 

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_5.png?raw=true" alt="Capture_2"  /></p>

20- The facet will now appear on the left-hand side of the page.

21- Click a line in the facet to select rows with that value.

22- Use the `Include` option to select multiple values.

23- Use the `Edit` option to address a pattern error.

24- Do this for other pattern errors. 

Consult the following resources as needed to understand this data:
- [ISO 3166 country code table (Wikipedia)](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Decoding_table)
- [United Nations geographic regions](https://unstats.un.org/unsd/methodology/m49/)
- [USPS list of state abbreviations](https://about.usps.com/who-we-are/postal-history/state-abbreviations.htm)
- [Wikipedia list of baseball team abbreviations](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Baseball/Team_abbreviations)
- [Wikipedia glossary of baseball jargon](https://en.wiktionary.org/wiki/Appendix:Glossary_of_baseball)

#### Exporting from OpenRefine

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_6.png?raw=true" alt="Capture_2"  /></p>

25- Click on the `Export` button in the top right-hand corner and select the option to export your OpenRefine project as a CSV file. 

<blockquote>NOTE: OpenRefine will only export the rows of data selected in your current review. Be sure to remove all filters or facets before exporting.</blockquote>

26- Make sure this file has a unique name and is saved in a location where you can find it again.

27- Open this new CSV file in a spreadsheet program.

28- Check to see the pattern errors have been addressed.

29- Go through this same process for the `CSC_Database_Lab_TeamLocations.csv` file.

<blockquote>Q6: Compare your experience working in OpenRefine to other experiences you have had in a text editor or spreadsheet program. In what ways do you understand, perceive, or relate to the data differently through working in OpenRefine? Describe your experience cleaning this data in OpenRefine.</blockquote>

We are barely scratching the surface of what is possible with data wrangling in OpenRefine. The progam can also standardize capitalization, remove leading and trailing spaces, and address other commonly-found data errors. [Library Carpentry's OpenRefine tutorial](https://librarycarpentry.org/lc-open-refine/) goes in to greater detail about many of these other functions.
 
### Data Wrangling Using A Spreadsheet Program

Spreadsheet software programs are another commonly-used tool for interacting with structured data. Some spreadsheet programs like Microsoft Office's Excel or Apple's Numbers are proprietary software installed on a local computer. Other proprietary spreadsheet programs like Google Sheets run online and are not installed locally.

Open-source spreadsheet programs include OpenOffice's Calc and LibreOffice's Calc. The Raspbian operating system comes equipped with LibreOffice Calc. 

This tutorial works with Microsoft Excel.

<blockquote>Q7: Describe a past experience working with a spreadsheet program. What were you trying to do? How did it go? What was your overall feeling about working with data in a spreadsheet program?</blockquote>

We are going to go through a process in Microsoft Excel where we load our individual CSV files into a multi-sheet workbook file. Then we will use some of Excel's built-in table functionality to clean the data.

#### Loading CSV Files into Excel

30- Open a blank Microsoft Excel file.

31- Save the blank file as an Excel workbook.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_7.png?raw=true" alt="Capture_2"  /></p>

32- Click on `Data` in the top menu bar.

33- Under `Get External Data` select the `From Text` option.

34- In `Sheet1`, select the `Player_Birthplaces.csv` file.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_8.png?raw=true" alt="Capture_2"  /></p>

35- In the pop-up window, choose the `Delimited` option. Because we are importing a `csv` file, our fields are separated by a comma. In this case, the comma is our delimiter.

36- Select the `My data has headers.` option.

37- Click `Next`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_9.png?raw=true" alt="Capture_2"  /></p>

38- In the next window (Step 2 of 3), select `Comma` as your delimiter. 

39- Check the `Data preview` window.

40- Click `Next`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_10.png?raw=true" alt="Capture_2"  /></p>

41- In Step 3 of 3, select `General` for `Column data format`.

42- Click `Finish`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_11.png?raw=true" alt="Capture_2"  /></p>

43- In the `Import Data` window, you can tell the program where to import the new data.

44- Click `OK`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_12.png?raw=true" alt="Capture_2"  /></p>

45- You should now see the CSV data in the Excel workbook.

46- Rename `Sheet1` so you know what data is included in that sheet.

47- Go through the same process for the `CSC_Database_Lab_TeamLocations.csv` file.

48- Save the updated workbook.

#### Creating a Table

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_13.png?raw=true" alt="Capture_2"  /></p>

49- Now we need to convert the sheets in our workbook to tables so we can search, sort, and filter.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_14.png?raw=true" alt="Capture_2"  /></p>

50- Select all the cells that contain data.

<blockquote>One shortcut is to select cell A1, then press Control Shift and the right arrow key to select all columns with data. Then Control Shift and the down arrow key to select all rows with data.</blockquote>
 
<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_15.png?raw=true" alt="Capture_2"  /></p>
 
51- Click `Insert` in the top menu bar.
 
52- Select `Table` under `Insert` to insert a table.
 
<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_16.png?raw=true" alt="Capture_2"  /></p>
 
53- In the pop-up window, we have already selected the cells with data. `=$A$1:$I$3616` is an expression that selects selects column A through column I and row 1 through row 3616.
 
54- Select the `My table has headers` option.
 
55- Click `OK`.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_17.png?raw=true" alt="Capture_2"  /></p>
 
56- We have now converted the data in our sheet to a table.

#### Editing Data

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_18.png?raw=true" alt="Capture_2"  /></p>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_19.png?raw=true" alt="Capture_2"  /></p>
 
57- Click the drop-down arrow next to a column header to see additional options for that field.
 
58- Use these sort, search, and filter options to address data pattern errors.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_20.png?raw=true" alt="Capture_2"  /></p>

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_21.png?raw=true" alt="Capture_2"  /></p>
 
59- Alternatively, use the `Replace` option under `Find & Select` (in the `Home` menu section) to address pattern errors.
 
Consult the following resources as needed to understand this data:
- [ISO 3166 country code table (Wikipedia)](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Decoding_table)
- [United Nations geographic regions](https://unstats.un.org/unsd/methodology/m49/)
- [USPS list of state abbreviations](https://about.usps.com/who-we-are/postal-history/state-abbreviations.htm)
- [Wikipedia list of baseball team abbreviations](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Baseball/Team_abbreviations)
- [Wikipedia glossary of baseball jargon](https://en.wiktionary.org/wiki/Appendix:Glossary_of_baseball)

<blockquote>To change all cells in a column, click the cell in the first non-header row. Press <Control> and the down arrow key to select all cells with data in that column. Press <Control> and <D> to copy the first value into the other selected cells. Alternatively, move your cursor over the bottom right-hand corner of the cell in the first non-header row. Click and drag the plus icon that appears down through the column to copy the value in the first cell into the subsequent cells.</blockquote>

60- Go through this same process for the second sheet with data from the `Team_Locations` CSV file. 

#### Options for Saving Your Work

61- We will save the combined CSV files as an Excel workbook to use later in this lab.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_22.png?raw=true" alt="Capture_2"  /></p>

62- Click on the `File` menu section to show additional export options.

63- Under `Export` you can see some of the other options for exporting the data in Excel.

<blockquote>Note: While CSV files are best for digital preservation and interoperability, they only support a single sheet of data.</blockquote>

<blockquote>Q8: Compare your experience working in Excel to your experience working in OpenRefine. In what ways do you understand, perceive, or relate to the data differently through working in Excel? Describe your experience cleaning this data in Excel.</blockquote>

We are barely scratching the surface of what is possible with data wrangling in Excel (or other spreadsheet program). The progam can also standardize capitalization, remove leading and trailing spaces, and address other commonly-found data errors. [Library Carpentry's Tidy Data for Librarians tutorial](https://librarycarpentry.org/lc-spreadsheets/) goes in to greater detail about many of these other functions.

# Workflows for Data Entry

<blockquote>Q9: For the baseball datasets we have been working with in this lab, what do you think may have contributed to or caused the pattern errors we needed to address? How could these pattern errors be addressed in the data entry process?</blockquote>

According to Library Carpentry's [Tidy Data for Librarians tutorial](https://librarycarpentry.org/lc-spreadsheets/04-quality-control/index.html), "Quality assurance stops bad data from ever being entered by checking to see if values are valid during data entry. For example, if research is being conducted at sites A, B, and C, then the value V (which is right next to B on the keyboard) should never be entered. Likewise if one of the kinds of data being collected is a count, only integers greater than or equal to zero should be allowed."

Building in quality assurance constraints into a data entry workflow can help minimize pattern errors that require later cleaning.

## Survey Versus Spreadsheet

One option is use a survey with some pre-defined choices or drop-down options.

NEED TO CHANGE TO GOOGLE FORM INSTRUCTIONS

64- Log into your Grinnell OFfice 365 account.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_23.png?raw=true" alt="Capture_2"  /></p>

65- Select the Microsoft Forms app.

66- Click on the `New Form` option.

67- Explore the different question types. 

<blockquote>Q10: Describe how you would go about building a survey form or template for the <code>CSC_Database_Lab_PlayerBirthplaces.csv</code> file. You DO NOT need to actually create or submit a survey form. Describe what types of questions and pre-defined question or field options could you use to more effectively generate the data in this file.</blockquote>

## Data Validation

68- You can also use some of the built-in data validation options in Excel.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_24.png?raw=true" alt="Capture_2"  /></p>

69- Under `Data`, select the `Data Validation` option.

<p align="center"><img class=" size-full wp-image-55 aligncenter" src="https://github.com/kwaldenphd/tidy-data-principles/blob/main/figures/Figure_25.png?raw=true" alt="Capture_2"  /></p>

70- In the pop-up window, you can limit the  types of values that will be valid in a particular field. 

71- You can also define a list of options or values which will show up as drop-down options for cells in that field.

Visit Microsoft Office's ["Apply data validation to cells"](https://support.office.com/en-us/article/apply-data-validation-to-cells-29fecbcc-d1b9-42c1-9d76-eff3ce5f7249) article to learn more about data validation options.

<blockquote>Q11: Describe how you would go about using data validation to build a template for the <code>CSC_Database_Lab_PlayerBirthplaces.csv</code> file. You DO NOT need to actually create or submit a template. Describe what data validation options and pre-defined field options could you use to more effectively generate the data in this file.</blockquote>

# Project Prompts

# Lab Notebook Questions
