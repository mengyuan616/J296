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

### Answer the questions:
#### Question 1: Which industries contributed the most to the Republican and Democratic parties? How much was contributed to each party? 
1. Highlighted the whole sheet and inserted a pivot table into a new sheets
2. Chose "Industry" as rows, "Amount" as values(summarized by SUM) and "Party" as columns
3. Then I got a table like this:


Media/Entertainment			$1,880,000
Republican/Conservative	$7,514,000																					

### Question 2: How much did donors from the Misc. Business sector contribute to the Democratic party? Which donors were based in Miami Lakes, FL? 
1. $3,520,000
2. Windmere Corp

### Question 3: What percentage of the tobacco industry’s donations does Philip Morris account for? How much is it? 
1. Filtered the dataset by 


Philip Morris	68.54%	$2,070,000																							




