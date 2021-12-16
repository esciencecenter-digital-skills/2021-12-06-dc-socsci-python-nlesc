![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Data Carpentry Day 3

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

[Code of conduct report form](https://docs.google.com/forms/d/e/1FAIpQLSdi0wbplgdydl_6rkVtBIVWbb9YNOHQP_XaANDClmVNu0zs-w/viewform)
 
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

[link](https://github.com/esciencecenter-digital-skills/2021-12-06-dc-socsci-python-nlesc/raw/main/data/pandas-data.zip)

## 👩‍🏫👩‍💻🎓 Instructors

Leon Oostrum, Francesco Nattino, Sven van der Burg

## 🧑‍🙋 Helpers

Ou Ku

## 🗓️ Agenda

|  |  |
|--|--|
09:00 |	Recap of Day 2
09:15 |	Reading data from a file using Pandas
10:15 |	Coffee break
10:30 |	Extracting row and columns
11:30 |	Coffee break
11:45 |	Data Aggregation using Pandas
12:45 |	Wrap-up
13:00 |	END

## 🔧 Exercises

### Exercise: Creating functions
1. Write a function definition to calculate the volume of a cuboid. The function will use three parameters h, w and l and return the volume.
2. Supposing that in addition to the volume I also wanted to calculate the surface area and the sum of all of the edges. Would I (or should I) have three separate functions or could I write a single function to provide all three values together? Why?

Add code whithin:
```python=
nicely formatted code here 
```

- Alessandra 
```python=
    def cuboid_volume (height,width,length):
    '''
    This function calculate the volume of a cuboid given the three dimensions
    '''
    h = height
    w = width
    l = length
    if h >0 and w>0 and l>0 and h==w==l:
        volume = (h*w*l)
        return volume
    else: 
        print("not a cuboid")   
```      
- Anita
- Bram
- Elisa
```python=
        def cuboid_volume(h, l, w):
    '''
    This function calculates the volume of a cube
    '''
    volume = h * l * w
    return volume

height = 3
length = 3
weight = 3

print(cuboid_volume(height, length, weight)) #weight here should be width 🙈
```
    - I'd probably create separate functions, but I'm no Python master ye
    
- Jurgen
 ```python=
        length = 10
        width = 5
        height = 3
        def volume_cuboid (l, b, h):
            #    Calculate the volume of a cuboid
            volume = l*b*h
            return volume

        vol = volume_cuboid(length,width,height)
        print(vol)
 ```
     preferably separate functions
- Leonoor
- Maryam
```python
    def calculate_volume_cube(h, w, l):
    """
    this function calculets the volume of a cube based on three values of h, w, l
    """
    volume_cube = h*w*l
    return volume_cube
    
    def calculate_surface_cube(volume_cube, l):
    """
    this function calculets the volume of a cube based on three values of h, w, l
    """
    surface_cube = volume_cube/l
    return surface_cube
```
- Roel: 
  ```python=
    def calculate_cuboid_volume(h, w, l):
        '''
        Calculating the volume of the cuboid with dimensions h * w * l
        '''
        volume = h*w*l
        return volume
    ```
    - Better to have separate functions
- Rosanne
    ```python=
    def get_cuboid_volume(h,w,l):
        "This function calculates the volume of a cube"
        cuboid_volume = h*w*l
        return cuboid_volume
    ```
    - I'd put surface and sum in different functions so i can remove/alter them without breaking the whole thing.
- Suraya
- Thoa
```python
week=(Monday,Tuesday,Wednesday,Thursday)
def count_day(listday,sep)
    days=listday.split(sep)
    num_days=len(days)
    return num_days
number_of_day=nums_day(week,",")
print(number_of_day)
```
- Tom
```python=
def calc_vol_cube (h, l, b):
    '''
    Formula to calculate the volume of a cuboid based on size/parameters h, w, l
    '''
    volume = h*l*b
    return volume
```
- Veronica 
- X Ouyang 

#### Solution

```python=
def calculate_vol_cuboid(h, w, l):
    """
    Calculates the volume of the cuboid
    h, w, l are the height, width, and length
    """
    volume = h * w * l
    return volume


my_volume = calculate_vol_cuboid(2, 3, 4)
```
Use function to carry out a single operation - avoid to create tasks that are too complex


### Exercise: Pandas sep

1. What happens if you forget to specify `sep='\t'` when reading a tab delimited dataset?
2. (Optional): Use the help of the `read_csv` function. How do you read in the first 10 lines of the .tab file? How do you read in a subset of the columns? 
3. (Very optional): Write a function that reads in the data and returns a pandas dataframe

- Alessandra 1. It doesn't separate columns. 2. put the command nrows = 10. 3. usecols=[1,10]
- Anita put all inone line
- Bram
- Elisa
    - 1. It doesn't make a proper table because no separator is defined. Just all data jumbled after another
    - 2. Just solved it via [Stackoverflow](https://stackoverflow.com/questions/23853553/python-pandas-how-to-read-only-first-n-rows-of-csv-files-in/23853569)
- Jurgen: everything is put in one column
- Leonoor
- Maryam 
    -  omitting "sep ='\t'" loads all data in one column rather than multiple columns
   -  using nrows=n we can define the number of loaded rows: 
     ```python
        df =pd.read_csv("SN7577.tab", nrows =10, sep = '\t')
    ```
- Ricarda
- Roel: 1 it places all data in 1 column
    -    2 use nrows=10
    -    3. 
    ```python
    def read_data(name,separator):
        ''' Read data and return as pd.variable '''
        data = pd.read_csv(name,sep=separator)
        return data
   ```
- Rosanne: 
    - 1. It puts all columns into one. 
    - 2. nrows. usecols[]. 
    - 3. with some help LOL
```python=
def gib_pandas_dataframe (file, sep):
    """
    this function reads csv files and hopefully will return a pandas dataframe
    """
    return pd.read_csv(file, sep=sep)

df = gib_pandas_dataframe("SN7577.tab", "\t")
print(df)
```

- Suraya
- Thoa: 1. without sep, we can not see the full table. 2. df=pd.read_csv("SN7577.tab",nrows=10,usecols=10,sep ='\t'),
- Tom: 1. It puts everything in one big row. 2 
```python=
df_firstn = pd.read_csv("SN7577.tab", nrows=10, sep='\t')
print(df_firstn)
```
  3: couldn't figure that out.
- Veronica 1. All the nformation is on one column with 1286 rows.
- X Ouyang All in a single column.

#### Solution

1. Returns a single column - there is no comma to separate columns.
2. `pd.read_csv("SN7577.tab", sep="\t", nrows=10)`
3. `pd.read_csv("SN7577.tab", sep="\t", usecols=["Q1", "Q2"])`

### Exercise: head and tail
1. As well as the `head()` method there is a `tail()` method. What do you think it does? Try it.
2. (Optional) Both methods accept a single numeric parameter. What do you think it does? Try it.


- Alessandra: 
1. tail gives back the last 5 rows of a dataframe. 
2. you can have the first (head) or last (tail) n rows of a dataframe  df.tail(n), df.head(n) where n is a number
- Anita tail sows the end, and number of rows 
- Bram: shows first and last rows respectively. 5 is default, but can be n of choice
- Elisa
    - tail shows the end of the (rows and columns in) the dataset
    - the numeric parameter n specifies how many rows you'd like to see from the top (head) or the bottom (tail) of the dataframe
- Jurgen: only the five last rows are shown
- Leonoor
- Maryam it takes the last lines in the dataset
- Ricarda
- Roel: tail show the last lines. With the integer you can ask for a specific number of lines
- Rosanne: .head() shows the first () of lines, .tail() shows the last () of lines.
- Suraya: shows last 5 rows. with n you choose numbers of rows at head or tail. 
- Thoa: when use tail(), i see next 5 rows, from 5 to 9
- Tom: shows end of dataset (last 5 rows). With the parameter you can define how many lines starting from the bottom or top to be shown.
- Veronica 1. tail shows the last 5 rows. By adding a number, you can see the number of rows of either the head or tail.
- X Ouyang first 5 / last 5 rows / adding number in ()


#### Solution

1. Show the last few rows
2. Specify the number of rows shown


### Exercise: Print all columns
1. When we asked for the column names and their data types, the output was abridged, i.e. we didn’t get the values for all of the columns. Can you write a small piece of code which will print all of the values on separate lines. Paste your code in the collaborative document.
2. (optional): Using if statements, write a piece of code that prints 'big dataset' if the number of columns is larger than 10, and 'small dataset' if the number of columns is smaller.
3. (even more optional): Write a function that returns whether a dataset has more than 10 columns. (it should return a boolean value)


- Alessandra 
1. columns = list(df.columns) 
   columns
   ``` python=     
    if len(df.columns) > 10:
    print("Big dataframe")
    else: print("Small dataframe")
    ```


- Anita
- Bram
- Elisa
    - I googled it:
    ``` python=
    print(df.columns.tolist())
    ```
- Jurgen: list(df.columns)
- Leonoor
- Maryam
- Ricarda
- Roel
```python=
for item in df.columns:
    print(item)
    
if len(df.columns.to_list()) > 10:
    print("table is large")
else:
    print("table is small")

```
- Rosanne
    - 1. 
    ```python=
    for column in df.columns:
        print(column)
    ```
    - 2.
    ```python=
    if len(df.columns)>10:
        print("big dataset")
    else:
        print("small dataset")
    ```
    - 3.
    ```python=
    def dataset_more_columns(dataframe, ncolumns):
        if len(df.columns)>ncolumns:
            return True
        else:
            return False
dataset_more_columns(df, 10)
    ```
- Suraya
- Thoa: print(df.columns.tolist())
- Tom
- Veronica 
- X Ouyang 

#### Solution

```python=
for column in df.columns:
    print(column)
```

### Exercise: Pandas columns

What happens if you:
1. List the columns you want out of order from the way they appear in the file? E.g. in the order: ['Q3', 'Q2', Q1]?
2. Put the same column name in twice?
3. Put in a non-existing column name? (a.k.a Typo)


- Alessandra
    1. Shows columns in the order you put them
    2. Shows the column twice
    3. Gives an error, indicating the column does't exist in the index
- Anita list it in order you ask,show the column duble, key error 
- Bram: 1. orders them accordingly 2. shows that column twice 3. error msg: '[column name] not in index'
- Elisa
    - The order of the columns will change according to how you entered them
    - The column is printed twice
    - Scary error message
- Jurgen
- Leonoor
- Maryam
    - 1. order of columns printed will change accordingly
    - 2. the column will be printed twice
    - 3. a key error apears that says: "['xxx'] not in index"
- Ricarda
- Roel: 1 You get the data in the order you ask for. 2 you get the data twice. 3. you will get an error
- Rosanne: 
    - 1. It orders the columns in the listed order
    - 2. It lists the same column twice
    - 3. It results in an error because the name is not in the index.
- Suraya
- Thoa:1. put the column name in the order as you want or we use display(df[df.columns[::-1]]) to revesrse the column. 2. I type twice; 3. I see an error syntax
- Tom. 1. you get the order you put it in. 2. you get it twice. 3. I get 2 error codes. The 1st one I don't really get ("#take() does not accept boolean indexers")
- Veronica 1. You get the order you asked for 2. You get the same column twice in the order you input 3. You get an error "not in index"
- X Ouyang: 1&2. the data is in your order. 3. error


#### Solution

1. The order in the list is the order of columns in the dataframe returned
2. We get the column repeated
3. `KeyError` - error for missing key


### Exercise: filtering
Select all the rows where numkid is larger than 5 OR Q3 == 4, then select only numkid and Q3 columns. How many rows are left.

Hint: https://stackoverflow.com/questions/24775648/element-wise-logical-or-in-pandas

- Alessandra 362
- Anita 362
- Bram: I got 314? Not sure what's going on there
- Elisa 362 and second part :heavy_check_mark: 
- Jurgen
- Leonoor
- Maryam 362
- Ricarda
- Roel: 362 rows
- Rosanne: I have got 362 rows left.
- Suraya: 362
- Thoa: df[df['Q3']==4]:67; df[df['numkid']>5]=314; both is 362 rows
- Tom - getting an error: KeyError: False
```python= 
df[(df['numkid'] > 5) | (df['Q3' == 4])] [['Q1', 'Q2', 'Q3' 'numkid']]
```
- Veronica 362
- X Ouyang 


#### Solution

```python
df[(df['numkid'] > 5) | (df['Q3'] == 4)][['numkid', 'Q3']]
```
It has 362 rows (and 2 columns).

### Exercise: Number of values
Compare the count values returned for the B_no_membrs and the E19_period_use variables.
1. Why do you think they are different?
2. How does this affect the calculation of the mean values?
3. (optional): Use your search engine to find how to deal with missing values in pandas.

- Alessandra 
    - 1. there are nissing values in the E19_period_use column
    - 2. missing values are treated as 0 according to pandas manual
    - 3. you can change the missing values with 'fillna()' command
- Anita e19_period_use has NA
- Bram: 1. 131 vs 92, E19 has missing values. 2. E19 will not have a representative mean
- Elisa:
    - 1. 131 vs. 92 - probably missing data
    - 2. You can't compare means/the calculation will be off
    - 3. Currently reading manual [here](https://pandas.pydata.org/pandas-docs/stable/user_guide/missing_data.html)
- Jurgen
- Leonoor
- Maryam 131 vs. 92
    - df.isna()[['B_no_membrs','E19_period_use']]
- Ricarda
- Roel: 131 vs 92. E19_period has missing values
- Rosanne: 
    - 1. E19 might have missings compared to B. 
    - 2. Not sure, means are calculated with the values in the columns? 
    - 3. According to the internet: isnull(), isna() to detect missing values. df.isna() returns the dataframe with boolean values indicating missing values.
- Suraya
- Thoa: 131 and 92, because of the number of rows in two column, so we have the different. From that we have the different calculation on mean value.
- Tom
- Veronica 131 and 92
- X Ouyang 131 and 92. Missing values

#### Solution

```python=
df["B_no_membrs"].count()  # 131
df["E19_period_use"].count()  # 92
```
1. The difference is due to NaN values
2. The NaN values are skipped in the calculation of the mean
3. **Tomorrow**

## 🧠 Collaborative Notes

### Recap day 2

- JupyterLab 
- Variables and types
- Arithmetics (`+`, `-`, `*`, `**` (exponent), `%` (modulo))
- Help: `help(function)` or "Shift + Tab"
- Functions and methods (=functions belonging to objects, e.g. `string.upper()`)
- Lists: `[1, 2.0, "abc"]`
- Range: `range(start, end, step)`
- "If statement":
```python=
if condition 1:
    statement 1
elif condition 2:
    statement 2
else:
    statement 3
```
- "For loop":
```python=
for element in iterable:
    do something
```
- Functions:
```python=
def my_function_name(argument1, argument2):
    """
    Here I can explain what the function does
    """
    do something here
    return variable_to_return


result = my_function_name(1, 2)
```

### Pandas

Add comments to a cell using `#`:
```python=
# this is a comment
a = 3  # here as well 
```

Comments can also be added as Markdown text, selecting cell type to "Markdown" (or click "ESC" and then "M"). Text is rendered by pressing "Shift" + "Enter". For example:
```
# title

this is some text 

* item 1
* item 2
```

**Pandas**: Python library (=collection of functions and data structures) for data analysis.

#### Read data

Import library as:
```python=
import pandas as pd
```

Load data in pandas:
```python=
df = pd.read_csv("SN7577.tab", sep="\t")  # specify "Tab" separator
```

`df` is a DataFrame, i.e. a structure for tabular data:
```python=
type(df)
# pandas.core.frame.DataFrame
```

Get information about the dataframe:
```python=
# show first few rows
df.head() 
# show last few rows
df.tail()
# how many rows
len(df)
# how many rows, columns
df.shape
# number of cells
df.size
# column names
df.columns
# data types
df.dtypes
```

#### Extracting rows and columns

If you are in a new notebook:
```python=
import pandas as pd

df = pd.read_csv("SN7577.tab", sep="\t")
```

Access columns:
```python=
# acces single column
df["Q1"]
# alternative
df.Q1
# access multiple columns
df[["Q1", "Q2", "Q3"]]
```

Filtering by rows:
```python=
# select rows by index
df[1:4] # rows 1, 2, and 3
```

Also using "criteria" (masks):
```python=
df["Q2"] == -1  # True or False for each of the rows
df[(df["Q2"] == -1)]  # extract rows for which condition is True

df[(df["Q2"] == -1) & (df["numage"] > 60)]  # combine contitions: condition 1 AND condition 2

df[(df["Q2"] == -1) & (df["numage"] > 60)][["Q1",  "Q2", "numage"]]  # combine row filtering and column selection
```

Take a random (row) sample:
```python=
df.sample(10, replace=False)  # 10 records, do not select rows twice
```

### Data aggregation

In a new notebook:
```python=
import pandas as pd
df = pd.read_csv("SAFI_results.csv")
```

Describe our dataset:
```python=
df.describe()
# also for a single column
df["B_no_members"].describe()
```

Statistics can be accessed also from column methods:
```python=
# now many elements
df["B_no_members"].count()
# sum all elements
df["B_no_members"].sum()
```


## 📚 Resources

* Python documentation: https://docs.python.org/3/contents.html
* Python cheatsheet: https://www.pythoncheatsheet.org
* Markdown cheatsheet: https://www.markdownguide.org/cheat-sheet/


## Feedback

### Tip (what to improve)

- I would have liked to see more about how to import textual data or something like that - but if there's some written guidance on that I'd be very happy also
-
- Looking back on the previous 2 days, I think I would have preferred to start earlier with Python/Pandas and not spending time on OpenRefine. That was largely about organizing your dataset, which perhaps is suitable for a different course/more introductory. This Python intro of day 2 and 3 was great, so wished we already started on day 1 :smiley: 
- Some parts went a bit too fast for me today so I used the breaks to keep up 
- Maybe also say something about importing other datasets into Pyhton? Maybe this will be tackled tomorrow :-)
- Will we also practise the whole chain (meaning dataset, use OpenRefine and finally use Python to analyse it?)

### Top (what went well)
- Really nice! Pace is just right, looking forward to the next day.
- I liked how the trainers were so attentative to people who were struggling, and how they kept a close eye on the chat. Loved how they posted encouraging messages and compliments! 
-
- The lesson today is very useful, easy to understand and I can catch up everything. The instructor keep suitable speed and explain clearly what we ask. 
- I loved the lesson, it was clear, useful and easy to follow! I feel comfortable asking questions both in the chat or raising the end.
- Very nice and very clear 
- Really liked all the excercises, it made the indexing more clear to me with the double brackets.
- I  enjoyed the lesson, as with the past 2 lessons. I like the pace and like how you keep improving each lesson with the tips that apply to this class.
- The lesson is clear and helpful. Really engaging and help is friendly and responsive.
- Really liked the exercises and figuring stuff out, even when I couldn't figure it out
- I really find the whole workshop very well and nicely organized. A big Thanks to all the instructors
- Very useful. I could follow-up although, admitedly, I mostly copied what the instructor was doing. Not sure I can use this with independence (yet) but you made it seem perfectly doable. 
- Learned many useful things, thanks!
