![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Data Carpentry Day 1

2021-12-06 Data Carpentry with Python

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

## 👮Code of Conduct

* Participants are expected to follow those guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, type `/hand` in the chat window.

To get help, type `/help` in the chat window.

You can ask questions in the document or chat window and helpers will try to help you.

## 🖥 Workshop website

Workshop website with and setup instructions
[link](https://esciencecenter-digital-skills.github.io/2021-12-06-dc-socsci-python-nlesc/)

Download files

[link](https://figshare.com/ndownloader/articles/6262019/versions/4)

## 👩‍🏫👩‍💻🎓 Instructors

Leon Oostrum, Francesco Nattino, Sven van der Burg

## 🧑‍🙋 Helpers

Ou Ku

## 🗓️ Agenda

|  |  |
|--|--|
09:00 | Welcome and introduction
09:15 |	Data Organization in Spreadsheets
10:45 |	Coffee break
11:00 |	Data Organization in Spreadsheets (continued)
12:00 |	Coffee break
12:15 |	OpenRefine for Data Cleaning
12:45 |	Wrap-up
13:00 |	END

## 🔧 Exercises
We’re going to take a messy version of the SAFI data and describe how we would clean it up.

Download the [messy data](https://ndownloader.figshare.com/files/11502824).

1. Open up the data in a spreadsheet program.
2. Notice that there are two tabs. Two researchers conducted the interviews, one in Mozambique and the other in Tanzania. They both structured their data tables in a different way. Now, you’re the person in charge of this project and you want to be able to start analyzing the data.
3. In your breakout room, identify what is wrong with this spreadsheet. Discuss the steps you would need to take to clean up the two tabs, and to put them all together in one spreadsheet. Write this down in a list in the collaborative document.
4. **Important** You don't have to clean the data, just write down the possible improvements;

After you go through this exercise, we’ll discuss as a group what was wrong with this data and how you would fix it.

Answers:

- Room 1:
    - Combine tables within each sheet based on the ID
    - Combine the Mozambique/Tanzania tabs and add column "country" (but mb the livestock table makes this difficult)
    - Make decision on dead cow: Y or N 
    - Uniform coding of missings (-99 vs. -999 vs. empty cell)
    - Uniform coding of y/n (not yes, no, y, n etc.)
    - Adjust spelling to be uniform (e.g. mabatisloping vs. mabati_sloping)
    - Add additional column for barn/shed y/n
    - values in column named "total" does not make sense 
    - In tab Tanzania, the animals quantity is not clear, it includes yes/no instead of numbers => be uniform
    - Make clear column headings

- Room 2:
    - missing values not consistently encoded (empty, -99, -999)
    - different tab per table please (or just one table with factors or long format)
    - notes difficult to find back (* / yellow color coding)
    - logical colums not entered consistently as logical values ( Y, yes, 1)
    - some columns are both yes and count
    - 4, (oxen ,  cows ,  goats ,  poultry) rather: per type: number or logical
    - mabati_sloping / mabatisloping
    - use consistent column / factor naming 
    -  Have same table format for both tabs.

- Room 3: We would combine the tables by using the key_id, one row for each ID with the data in the columns, with one type of information in each cell. Split roof_type into two variables y/n, underscores in the headings, split floor type as well y/n to avoid typos. Choose one variable format (0-1) and stick to it!
- Room 4:
    - Totallly incoherent structure, no ways to work with any of it, sort nor analyze
    - no description of data collection, data entering, ways to collaborate between the two persons
    - categories of animals are organized in different ways between the tabs
    - key IDs are not unique IDs
    - grammatical errors and inconsistenices will lead to issues
    - the highlighting probably leads to issues when analyzing
- Room 5: 
    - 1st tab: 
        - Several small tables within the same table – and multiple tables/categories per column.
        - Data are written down in different formats within even the same table
        - The highlight is not a useful way of marking that a barn is included.
        - 10th household is omitted in one of the tables
        -  Blank values, and impossible values for some IDs.
    -  2nd tab:
        -  More than one table within one spreadsheet
        -  Comments marked with an asterisk
        -  10 IDs in one table, 9 in another
        -  The livestock table writes the data differently from the first table
        -  Missing values
        -  Different data types within one column
        -  Values aren’t entered as numbers
    - In general: Since the data are entered differently, it’s hard to combine the data to clean/analyse them and compare countries

Consensus answers:
* Consistent naming & values
* Don't use spaces
* Consistency in missing values
* Don't leave blanks
* Don't use multiple tabs
* Don't use multiple tables for the same data
* Some columns need to be split
* Do not use formatting
* Do not use comments

### Exercise: Faceting

1. Using faceting, find out how many different `interview_date` values there are in the survey results.
2. Is the column formatted as Text or Date?
3. Use faceting to produce a timeline display for `interview_date`. You will need to use `Edit cells` > `Common transforms` > `To date` to convert this column to dates.
4. During what period were most of the interviews collected?

Done with the excercise?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: 
|Anita       | |
|Bram        | |
|Carlotta    | :heavy_check_mark:|
|Elisa       |:heavy_check_mark: |
|Henry       | |
|Jone        | |
|Josephine   | :heavy_check_mark: 
|Jurgen      | |
|Maryam      | :heavy_check_mark:  |
|Min         | |
|ricarda     | |
|Roel        | :heavy_check_mark:|
|Rosanne     | :heavy_check_mark:|
|Suraya      | :heavy_check_mark:|
|Thoa        | :heavy_check_mark:|
|Tom         | :heavy_check_mark:|
|Veronica    | :heavy_check_mark:|
|X Ouyang    | |
|Xingxing    | |

Solution:
Create a Facet by clicking on the interview_date column, then choosing Facet -> Text facet. 
1. There are 19 unique values.
2. It is formatted as text.
3. After convering the column to dates, use Facet -> Timeline facet.
4. From the timeline facet, we can see that this is around November 2016. We can drag the edges of the figure to select a smaller date range. This will automatically select a smaller range in the main screen of OpenRefine as well. (e.g. 82 matching rows out of a total of 131). When the facet is closed, all rows of the data are selected again.

### Exercise: Filtering
Click on the arrow of the respondent_roof_type column and click Text filter. In the box that appears on the left, type maba.

1. What roof types are selected by this procedure?
2. How would you restrict this to only one of the roof types?

Done?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: |
|Anita       | :heavy_check_mark: |
|Bram        | |
|Carlotta    | :heavy_check_mark:|
|Elisa       | :heavy_check_mark:|
|Henry       | |
|Jone        |  |
|Josephine   |  :heavy_check_mark: |
|Jurgen      |  |
|Maryam      | :heavy_check_mark: |
|Min         | :heavy_check_mark: |
|ricarda     |  |
|Roel        |  :heavy_check_mark:|
|Rosanne     |  :heavy_check_mark:|
|Suraya      |  :heavy_check_mark:|
|Thoa        |  :heavy_check_mark:
|Tom         | :heavy_check_mark: |
|Veronica    |  :heavy_check_mark:
|X Ouyang    |  :heavy_check_mark:|
|Xingxing    |  |

Solution:
1. To see the selected values, we can apply a facet on top of the filtering.
   Do Facet > Text facet on the respondent_roof_type column after filtering. 
   We then see two roof types: mabatipitched and mabatisloping
2. There are two ways: Either change the filtering to make it uniquely match one of the roof types, e.g. mabatip, or click on one of the roof types to only select that one (it then turns red)

### Exercise: Sorting

We discovered in an earlier lesson that the value for one of the village entries was given as `49`. This is clearly wrong. By looking at the GPS coordinates for the entries of the other villages can we decide what village the data in that column was collected from?

1. Sort on `gps_Latitude` as a number with the smallest first.
2. Add a sort on `gps_Longitude` as a number with the smallest first.
3. Using the drop down arrow on the `village` column, select `Edit column` > `Move column to end`. This will allow you to compare village names with GPS coordinates.
4. Scroll through the     entries until you find village `49`. Can you tell from it’s GPS coordinates which village it belong to?
5. Now sort only by `interview_date` as date. Move the village column to the start of the table. Does the row where village is `49` group with one particular village? Is it the same village as when comparing GPS coordinates?

Done?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: |
|Anita       | :heavy_check_mark:
|Carlotta    | :heavy_check_mark:|
|Elisa       | :heavy_check_mark:|
|Jone        | |
|Josephine   | :heavy_check_mark: |
|Jurgen      | |
|Maryam      |:heavy_check_mark: |
|Min         | :heavy_check_mark: |
|ricarda     | |
|Roel        | :heavy_check_mark: |
|Rosanne     |:heavy_check_mark: |
|Suraya      | :heavy_check_mark: |
|Thoa        | :heavy_check_mark:
|Tom         |:heavy_check_mark: |
|Veronica    | |
|X Ouyang    | :heavy_check_mark:|

Solution:
First remove any sorting.
1. Click on the arrow next to gps_Latitude, click sort and select smallest first
2. Click on the arrow next to gps_Longitude, click sort and select smallest first
3. Click on the arrow next to village, click edit column and select move column to the end
4. Village 49 is in between Chirodzo entries so that is most likely what it belongs to.
5. First remove any sorting. Then sort by interview_data as before. Again village 49 is in between Chirodzo entries.

Conclusion: Village 49 is Chirodzo.



## 🧠 Collaborative Notes

### OpenRefine
OpenRefine can be used to automatically clean messy data.
It can work with big datasets.

When you double-click the OpenRefine icon, the programme should open in your browser.

Is OpenRefine working for you?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark:|
|Anita       | :heavy_check_mark:|
|Carlotta    | :heavy_check_mark:|
|Elisa       |:heavy_check_mark:|
|Jone        | |
|Josephine   | :heavy_check_mark: |
|Jurgen      | :heavy_check_mark: |
|Maryam      | :heavy_check_mark: |
|Min         | :heavy_check_mark: |
|ricarda     | :heavy_check_mark:|
|Roel        | :heavy_check_mark:|
|Rosanne     | :heavy_check_mark:|
|Suraya      | :heavy_check_mark:|
|Thoa        | :heavy_check_mark: |
|Tom         |:heavy_check_mark:|
|Veronica    | :heavy_check_mark:
|X Ouyang    | :heavy_check_mark:|


In OpenRefine, click Create Project and open the SAFI_openrefine.csv file. This csv file 
was generated from the cleaned Excel sheet. csv stands for comma-separated values, which is a very simple file format that most programs (including Python) can read.

You will now see a preview of what the data would look like in OpenRefine. The data has not been imported yet!

When you're happy with how the data looks, click next and then create project (on the right) to import the data.

OpenRefine does not touch the raw data, so we cannot accidentally change those.

### Facets
Facets are a way to group all equal values that appear in a column. This can be useful to get an overview of your data.

As an example we will use this feature on the village column. Click on the arrow next to the village column, then click Facet -> Text Facet. Note that OpenRefine by default assumes that each column contains text. 

On the left you will now see the different values that appear in the village column, and how often they appear. E.g. God appears 43 times and Ruca appears twice.
We can see that two very similar village names appear (Chirodzo 37 times and Chirdozo once). The latter spelling is probably a miss-spelling of the former. There seem to be a few more typos. 

Exercise on line 200

### Clustering
We would like to merge values that probably represent the same thing (e.g. the different spellings of the same village). Using the clustering button in a facet we can do this. 
Use the key collision method and metaphone3 function for now. OpenRefine then finds two clusters: Firstly Ruaca and Ruca and secondly the two names that only differ in use of spaces. Tick the merge box and choose the value that should be used in the rightmost column. Click merge selected and close the screen. In the village facet we can now see that the miss-spelled versions of the village names are gone, they were changed into the new value that we chose.

We can also edit the values manually. With the edit button in the village facet, we can manually change Chirdozo to Chirodzo.

### Transformations
Now we will look at the items_owned column. We cannot use a text facet to look at the data in this column as it would use the entire list of items in a cell as a single value. There are also special characters in the values, such as quotes. 
Click the downward arrow, edit cells, then transform. This can be used to remove special characters. To remove the left square bracket, type the following in the expression field:
```
value.replace("[", "")
```
This will replace each "\[" character with an empty string (i.e. nothing).

Now we can do the same for the closing square bracket, spaces, and quotes.
Open the transform window again and use the history tab to reload the previous value.replace command using the reuse button.
We can do all replacements in one go:
```
value.replace(" ", "").replace("'", "").replace("]", "")
```

We need a more advanced facet to split the values in the cells. Choose facet -> custom text facet in the items_owned column. We want to split the values on the ; character. Use the following in the expression box:
```
value.split(";")
```
Now OpenRefine understands that the values are a list and each individual value is shown in the facet.

#### Undo/Redo
In the left screen, there is an undo/redo tab next to the facet/filter tab. 
You can click on any step in the undo/redo tab to go back to that step. 
When you go back to and old step and then make changes, you will lose all of the more recent changes!

#### Filtering
Imagine we want to look for all the rows that match a given search criterium in a given column. 

Click on the arrow of the respondent_roof_type column and click Text filter. In the box that appears on the left, type maba.

Exercise on line 228

#### Sorting
gps_Altitude will be used for sorting. Remember that OpenRefine interprets each column as text by default. For sorting however this doesn't matter, we can still sort it numerically. Click on the downward arrow, then click Sort.
In the pop-up window, you can select that the data should be sorted as numbers. You can also choose where blanks and errors should be put in the sorted data. Click ok to apply the sorting.

It is also possible to sort on multiple columns at the same time. For rows that have the same value, a second column can be used to define the sorting of those rows. E.g. apply sorting to gps_Accuracy as well.
All rows that have 0 as a gps_Altitude are now sorted by gps_Accuracy. Note that th e order in which you apply the sorting matters: We first applied the altitude sorting and then the accuracy sorting. The data are then sorted by altitude, and only the values that have equal altitude and then sorted by accuracy.

At the top you can click the sort menu and remove any applied sorting or apply the sorting permanently. You can also see the current sorting there.

Exercise on line 264

#### Exporting your results
You can export the transformations that were applied on top of the data, and/or the cleaned data.
The transformations can be exported from the undo/redo menu. Click the extract button. This shows all the steps that were applied on the data. With the checkboxes you can select which steps you want to export. 
On the right you can select all text and copy it, then paste it into your favourite text editor and save it.

To apply saved transformations, go to the undo/redo tab in a new dataset and click apply. Paste the earlier copied text and click apply. 

OpenRefine automatically saves all changes that are applied while we are working on a dataset. After closing OpenRefine and opening it again, you can click on open project to continue working on an earlier project. 

To share the OpenRefine project with someone else, click the export button in the top right and select OpenRefine project archive to file. This will download a .tar.gz file containing both the data and the transformations that were applied.

Finally we can export the cleaned data in a format that other programs can also understand. Again click export in the top right, but now select e.g. comma-separated values. Such a file can be opened in Python. 


## Tips

(What we can improve in the future?)

- Somehow I missed the pre-course instructions, including specifications for downloading relevant programs. It could have been me, but somehow I missed that communication.
- The SWC Install Python on Mac video on the workshop page is 5 years old, which means that most of the screenshots are outdated. It took me some time to understand what Anaconda is and how/why/if I could install those packages that are listed (numpy, pandas, matplotlib etc). It says "Bash", but I dont know what Bash is, nor does the GUI of Anaconda say something about it. Hopefully I don't have to do anything else on day 2 other than having Acaconda installed?
- Would be good to ask beforehand to create the HackMD account. 
- For me, the pace of the explanations could have been a little bit faster, but I'm, also happy that there was room to ask questions. Probably later on in the week I'll be happy that we're going slow!
- The sound of Leon was very good, but the quality of Ou, Sven and Francesco was sometimes a bit less. So, well, apparently Leon has great headphones+mic :)
- I downloaded/installed everything beforehand, but had to make the accounts during the talks. Maybe include "open the applications once and make accounts when needed" in prep?

## Tops

(What went well?)

- I have been to other workshops, but I liked the flow and type of materials presented here very easy to follow and logical. Very fruitful for me at least. THANKS!
- The exercises were really good and offered a good flow. And the explanations were given in a good order. I really feel like I learned something and looking forward to the rest of the week!
- The workshop is really good and the exercises are very easy to practice
- Really nice and friendly atmosphere, well done!
- Very clearly explained and enjoyable course so far. I'm a proper begginer and I could follow introductions and exercises easily. I really appreciate this.  
- I really like the flow and this collaborative document (with the information, instructions and being able to see others work, plus the conclusion). It was easy to follow even for a novice like me. Thanks!
- Clear talks, great pace and I really like the opportunities to ask questions! 


## 📚 Resources
[NL-RSE website](https://www.nl-rse.org)
[OpenRefine](https://www.openrefine.org)
[GREL functions](https://docs.openrefine.org/manual/grelfunctions)

