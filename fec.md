# Campaign Finance Data Analysis
**Original data source**: Federal Election Commission https://www.fec.gov/data/ <br>
**Dates covered**: Jan 1995 to Dec 1996

## Step 1: Clean up the data

### First steps:
1. Downloaded the dataset from as a csv file
2. Uploaded it to OpenRefine and created a new project

### Some edits I made in OpenRefine:
1. Applied  "Facet" - "Text Facet" to every column to check for anything that didn't make sense; Modified some of the donors' and recipients' names for better consistency.<br>
   > For example: <br>
   Repub → Republican <br>
   Cmte → Committee <br>
   DNC → Democratic National Committee <br>
2. Checked the city column and edited some wrong city names by looking up their zip codes:
   > "Sonnywhale" to "Sunnyvale" <br>
   "New Yorkrook" to "New York" <br>
   "Athertono" to "Atherton" <br>
3. In the "Party" column, in addition to "R" and "D", there was also a value called "3". The three recipients under party 3 were all "Natural Law Party of the United States". Since we are focusing on the two major parties here, I changed "3" to "Other". <br>
4. Spotted two blank zip codes. I added it for "American Airlines" based on where it headquartered in. The other was from donor "Robert Wookd Johnson", and I wasn't able to find its specific location. 

**Note**: There were 12 duplicated rows spotted. I didn't remove them as it may require more fact-checking. 


## Step 2: Explore the data
### First steps:
1. Exported the cleaned dataset from OpenRefine, and opened it in Google Sheets
2. Made a copy of the dataset
3. Froze the first row and made it bold

### **Question 1**: Which industries contributed the most to the Republican and Democratic parties? How much was contributed to each party? 
The results:
* The **Media/Entertainment** industry contributed the most to the Democratic parties, with the amount of **$1,880,000**
* The **Republican/Conservative** industry contributed the most to the Republican parties, with the amount of **$7,514,000**

How I got there:
1. Highlighted the whole sheet and inserted a pivot table into a new sheets
2. Chose "Industry" as rows, "Amount" as values(summarized by SUM) and "Party" as columns
3. Then I got a table like this:
> !['Pivot table for question 1'](/pivot_q1.png)
(This is only a part of the table)
4. Copied the values of this table and pasted them into a new sheet called "Q1"
5. Sorted by the column for Democratic parties in descending order to find out which industry contributed the most; and then sorted by the column for Republican parties
> !['largest amount donated to R'](/q1_table_part1.png)
> !['largest amount donated to D'](/q1_table_part2.png)

												
### **Question 2**: How much did donors from the Misc. Business sector contribute to the Democratic party? Which donors were based in Miami Lakes, FL? 
The results:
* Donors from the Misc. Business contributed **$3,520,000** to the Democratic parties.
* **Windmere Corp** was based in Miami Lakes, FL

How I got there:
1. Applied filter to the "Sector" column, cleared all values and only selected "Misc Business"
2. Applied filter to the "Party" column, and only selected "D"
3. Then copied and pasted the filtered table into a new sheet called "Q2":
> !['New sheet for Q2'](/q2_sheet.png)
4. Applied the SUM formula in a blank cell to calculate the total amount: =SUM(B2:B34)
> !['Amount for D from Misc Biz'](/q2_sum.png)
5. Applied filter to the "City" column and selected "Miami Lakes" only
> !['Donors in Miami Lakes'](/q2_miamilakes.png) 

### **Question 3**: What percentage of the tobacco industry’s donations does Philip Morris account for? How much is it? 
The results:
* Philip Morris acounts for **68.54%** of the tobacco industry's donations.
* The amount is **$2,070,000**.

How I got there:
1. Applied filter to the "Industry" column, and selected Tabacco only
2. Copied and pasted the current table into a new sheet called "Q3"
> !['New sheet for Q3'](/q3_sheet.png)
3. Highlighted the whole Q3 sheet and inserted a pivot table into a new sheet
4. Added "Donor" for rows, "Amount" for values(summarized by SUM and show as Default), then added "Amount" for values again and chose show as % of grand total
5. Then I got a total like this:
> !['results for Q3'](/q3_philipmorris.png)




			




