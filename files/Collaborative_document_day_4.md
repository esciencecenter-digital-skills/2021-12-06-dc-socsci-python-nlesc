![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Data Carpentry Day 4

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

[link](https://github.com/esciencecenter-digital-skills/2021-12-06-dc-socsci-python-nlesc/raw/main/data/pandas-data.zip)

Zoom call

[link](https://us02web.zoom.us/j/81382525117?pwd=VGVvMHl4bDhCSXd4VE5tZnJnbTY2UT09)

## 👩‍🏫👩‍💻🎓 Instructors

Leon Oostrum, Francesco Nattino, Sven van der Burg

## 🧑‍🙋 Helpers

Ou Ku

## 🗓️ Agenda

|  |  |
|--|--|
09:00 |	Recap of Day 3
09:15 |	Joining Pandas Dataframes
10:15 |	Coffee break
10:30 |	Data visualisation using Matplotlib
11:30 |	Coffee break
11:45 |	Data visualisation using Matplotlib (continued)
12:45 |	Wrap-up & Post-workshop survey
13:00 |	END

## 🔧 Exercises

### Exercise: aggregation
(10 mins for this excercise)
In breakout rooms. Discuss the answers in your group and write the answers in the collaborative document.
1. Read in the SAFI_results.csv dataset.
2. Get a list of the different E26_affect_conflicts values.
3. Groupby E26_affect_conflicts and describe the results.
4. How many of the respondents never had any conflicts?
5. (optional) Using groupby find out whether farms that use water ('E01_water_use') have more plots ('D_plots_count') than farms that do not use water.


Answer:

Room 1:
- 2. array([nan, 'once', 'never', 'more_once', 'frequently'], dtype=object):pd.unique(df['E26_affect_conflicts'])
- 3. groupdata=df.groupby(['E26_affect_conflicts']): we get 4 rows
- 4. 46 never had a problem; 
5. group_1=df.groupby(['E01_water_use','D_plots_count']); No:3 rows; Yes: 7 rows

Room 2:

Question 5. mean for 'yes' water use is 2.5 plots, and those who have 'no' for water use has a 1,58 mean, so that's a lower number of plots. Heres the command we used:
```python=
grouped_water_plots = df.groupby(['E01_water_use'])
grouped_water_plots['D_plots_count'].describe()
```

Room 3:
```python=
    pd.unique(df["E26_affect_conflicts"])
```
```python=
    grouped_data = df.groupby("E26_affect_conflicts")
    grouped_data.describe()
```
46 respondents never had conflicts
```python=
    grouped_data = df.groupby(["E01_water_use"])
    grouped_data["D_plots_count"].describe()
``` 
Room 4:


Solution:

```python=
df = pd.read_csv("SAFI_results.csv")
unique_values= pd.unique(data['E26_affect_conficts'])
groupped_data = data.groupby('E26_affect_conficts')
groupped_data.describe() # We can see there are 46 respondents
```

### Exercise: Plotting with Pandas

1. Make a scatter plot of `years_farm` vs `years_liv` and color the points by `buildings_in_compound`.
2. Make a bar plot of the mean number of rooms per wall type (use columns `rooms` and `respondent_wall_type`).
3. (optional) Try plotting by both wall and roof type (`respondent_roof_type`)!

Answers with code:
- Alessandra 
    1 
    ```python=
    df.plot.scatter(x="years_farm", y = "years_liv", c = 'buildings_in_compound', colormap = 'viridis')
    ```
    2
     ```python=
    grouped_data = df.groupby(['respondent_wall_type'])
    mean_room = grouped_data['rooms'].mean()
    mean_room.plot.bar()
    ```

- Anita
- Bram 
- Elisa 
    - 1.
    ```python=
    df.plot.scatter(x="years_farm", y="years_liv", c="buildings_in_compound", colormap="viridis")
    ```
    - 2. 
- Jurgen 
- Maryam 
```python=

df.plot.scatter(x ='years_farm', y='years_liv' , c='buildings_in_compound')
##not sure if the following is correct?!
df.hist(column ='rooms', by='respondent_wall_type'layout =(1,4), figsize=(12,3))
df.hist(column ='rooms', by=['respondent_wall_type','respondent_roof_type'], figsize=(12,10)) 
```



- ricarda
- Roel 
``` python=
df.plot.scatter(x='years_farm',y='years_liv',c='buildings_in_compound',colormap='plasma',)
```
- Rosanne
``` python=
df.plot.scatter(x="years_farm", y="years_liv", c="buildings_in_compound", colormap="viridis")
```
``` python=
group_rooms = df.groupby("respondent_wall_type")
mean_rooms = group_rooms["rooms"].mean()
mean_rooms.plot.bar()
```


- Suraya 
df.plot.scatter(x="years_farm", y="years_liv", c="buildings_in_compound", colormap="viridis")
- Thoa:df.plot.scatter(x='years_farm',y='years_liv', c='buildings_in_compound', colormap='cividis') 
- Tom 
- Veronica: df.plot.scatter(x='years_farm', y='years_liv', c='buildings_in_compound', colormap='viridis') 
- X Ouyang

Solution:

Q1:
```python=
df.plot.scatter(x='years_liv', y='years_farm', c='buildings_in_compound', colormap='viridis')
```

Q2:
```python=
grouped = df.groupby('respondent_wall_type')
room_means = grouped.mean()['rooms']

room_means.plot.bar()
```

Q3 (optional):
```python=
grouped = df.groupby(['respondent_wall_type', 'respondent_roof_type'])
room_means = grouped.mean()['rooms']

room_means.plot.bar()
```

### Exercise: Recap
Take a few minutes to write down your thoughts on what we learned in this course:
* What questions do you still have?
* Whether there are any incremental improvements that can benefit your projects?
* What’s nice that we learnt but is overkill for your current work?

Answer:
- Alessandra
    I usually work with R, and most of the libraries and packages for statistical analysis are made for R, 
    but lots of bioinformaticians prefer Python, so I don't understand why... I love the course and I will start using Python as well! 
- Anita I like the course. Now i have to practice. 
- Bram 
- Elisa
    * How can I keep this up so that I don't forget most of what I've learnt? I don't usually work with this kind of data a lot, so do you have recommendations for exercises that I can do or how I can learn more?
        * Code through the exercises again
        * Read books about how to write (nice) Python
        * Practise with a hobby project and look up online documentation
    * I do occasionally work with (user) data and what I've learnt is going to be massively useful!
    * Some of the more complicated statistical stuff
- Jurgen : nice course, gives a good overview of the possibilities in which you can use Python. Maybe having a 'full' excersize, having a dataset in Excel, use OpenRefine to fine tune it and finally use Python to analyse it would be nice.  
- Maryam 
    - questions I have:
      *  We normally work with ATOM. I was wondering if I copy the codes from Atom to Jupyter, will it work automatically or does it need more work to convert?  
          *  Maybe: VSCode or Pycharm?
       *  How could we think like a computer?! I sometimes do not know how to immidiately come up with a way to solve the problem using a code!
- ricarda
- Roel: nice course, good description on the difference between [] and () to acces your data. 
- Rosanne: 
    - If you could give us one piece of advice for working with python, what would it be? 
    - Directly applying what I learned would be challenging, but at least now i know where to start! I definitely feel more confident now, compared to before the course. The presentations were well-paced and I found the different elements within the course very useful.
    - No overkills on this side! To apply it in my daily work, i'd need to look into statistical packages a bit more.
- Suraya: 
    - 1. Data organisation and cleaning, launching JupyterLabs (or in my case Notebook), learning basic functions, methods, working with various data formats, importing datasets, creating statistical summaries, analysing data, visualising/plotting data. 
    - 2. The course was very complete. You covered a lot of topics but was detailed enough -with practical examples- to give it a focus/specific stream. You have helped me massively to demystify Python. Personally, towards the end I felt I couldn't take any more info, but in all honesty to get a good picture of what can be achieved with Python, we needed it all. 
    - 3. Nobody at work has asked me to learn this, and I won't be needing it for my day-to-day job. I felt an obligation to learn to fully understand my "clients" needs. I was actually scared of Python, but you made it seem beautifully doable to me. Thank you. In order to retain this, however, I will need to continue attending these type of courses. 
- Thoa: This is the first I work with Python. However, it is really exciting and I collected a lot of things. I need to practice more on it.I have never used Pythont on my owrk but now I think I can connect my data with Python, use Python to make it more clear and easy to analysis.
- Tom: I hardly ever done any research or data collection that only involved myself. There are always colleagues, supervisors, student assistants that work with you. I assume that will be the case for most researchers and research support staff. Perhaps some time or pointers as to how to collaborate with others, would be very useful for the daily job of research.
- Tom: especially for people from the Social Sciences, I will expect the big step will be to make the transition from SPSS to Python. Perhaps good to point people, perhaps even before the course starts, to the fact that you can do Python in SPSS these days. This would have helped me to try out Python with my own data and the program that I'm used to. Useful link here: https://www.spss-tutorials.com/python-for-spss-what-is-it/
- Tom: I think it was really well organized! I think it was very useful also to often ask for feedback at the end of each day, and to say something about it at the start of the next day. Very attentive!
    * You can use GitHub for collaboration. eScience Center will also give workshop on that.
- Veronica: 
    - Reflection: This is my first ever time learning Python without knowing any information previously, other than the fact that it is a programming language. I found the course really engaging. As a Communications Advisor, I write a lot of stories about various projects but this gives me a small glimpse into how engineers work and what's involved in projects. 
    - Question: Will we be able to acccess these collaborative notes again - say if we want to go through the exercises again? 
        - We wil share them after the course!
- X Ouyang: This is the first time that I learned Python and this is a great introductory course. If I would like to continue learning Python, what should I do?
        * Code through the exercises again
        * Read books about how to write (nice) Python
        * Practise with a hobby project and look up online documentation
## 🧠 Collaborative Notes

### Recap of Day 3

- Pandas
- Data filtering
- Data aggregation

### Dealing with missing values
See how many missing values are there?
```python=
df.isnull().sum()
```

See how many missing for one column
```python=
df['E19_period_use'].isnull().sum()
```

Drop all rows with at least one missing value:
```python=
df_dropped = df.dropna()
```

Drop rows where a specific column has missing value
```python=
df_dropped2 = df[df['E_no_group_count'].notnull()]
```
where `df['E_no_group_count'].notnull()` is a filter (A Series with True or False values) selecting all rows where 'E_no_group_count' is not null.

Missing value shows as "NaN", which we also call a "null" value. It means a certain place in the table is not filled.

You can also replace all NaN value with another value:
```python=
import numpy as np
df['E19_period_use'].replace(-999, np.nan, inplace=True)
```
`inplace=True` modifies the variable `df`. If it is set to `False`, `df` will not be modified.

### Categorical values and grouping them

To inspect what rood types are there in the data.
```python=
pd.unique(df['C01_respondent_roof_type'])
```
`unique` selects all unique data in a Series.

Group data based on roof type, find out the statistics of each type:
```python=
grouped_data = df.groupby('C01_respondent_roof_type')
grouped_data.describe()
```

Group data based on a combination of two types, and inspect the statistics.
```python=
grouped_data = df.groupby(['C01_respondent_roof_type', 
                           'C02_respondent_wall_type'])
grouped_data.describe()
```

Inpesct one Series (Note it's A11 (eleven) but not All
``` python=
grouped_data['A11_years_farm'].describe()
grouped_data['A11_years_farm'].mean()
```

### Plotting: histogram

`matplotlib` is one of the Python libraries you can use for data visualization. It has good integration with `pandas`

Maigic command in Jupyter to setup the environment. (Only neccessary for very old Jupyter environment)
```python=
%matplotlib inline
```

Load another dataset
```python=
import pandas as pd
df = pd.read_csv("SAFI_full_shortname.csv")
```

Plot a histogram of one column:
```python=
df['years_liv'].hist()
```

Plot with differenc number of bins:
```python=
df['years_liv'].hist(bins=20)
```

Call `hist` from DataFrame directl allow you to do it together with grouping.
```python=
df.hist(column='years_liv', by='village')
```

Change the figure layouts
```python=
df.hist(column='years_liv', by='village', layout=(1,3), figsize=[12,3], sharex=True)
```

Save a DataFrame to csv
```python=
df.to_csv('my_SAFI_dataset.csv')
```

### Plotting: Scatter plot

Plot out locations.
```python=
df.plot.scatter(x='gps_Latitude', y='gps_Longitude')
```

Color the scatter dots with another column, choose a colormap
```python=
df.plot.scatter(x='gps_Latitude', y='gps_Longitude', c='gps_Altitude', colormaps='viridis')
```
More about [matplotlib colormaps](https://matplotlib.org/stable/tutorials/colors/colormaps.html).

### Plotting: Box plot
Box plot shows statistics of on one column:
```python=
df.boxplot(column = ['buildings_in_compound'])
```

Box plot by group
```python=
df.boxplot(column = ['buildings_in_compound'], by="village")
```

### Seaborn
To install Seaborn:
```python=
! pip install seaborn
```

Scatter plot:
```python=
import seaborn as sns
sns.boxplot(data=df, x='village', y='buildings_in_compound')
```

Linear regression plot
```python=
sns.lmplot(data=df, x='years_farm', y='years_liv')
```

Linear regression plot with grouped by `village` coolumn
```python=
sns.lmplot(data=df, x='years_farm', y='years_liv', hue='village')
```

Improve your plot:
```python=
import matplotlib.pyplot as plt

df.boxplot(column = ['buildings_in_compound'], by="village")

# Set a title
plt.title('Buildings in compound per village') # This command will affect the lastplot you made, same as the following commands

# Remove the auto generated title
plt.suptitle('')

# Set y axis label
plt.ylabel('Number of buildings')

# Remove x axis label
plt.xlabel('')

# Remove grid
plt.grid(None)

# Save figure as pdf
plt.savefig('figure.pdf') # Need to be in the same cell of your plotting function

# Save figure as png
plt.savefig('figure.png', dpi=150)
```


## 📚 Resources
[eScience Center newsletter subscription](https://esciencecenter.us8.list-manage.com/subscribe?u=a0a563ca342f1949246a9f92f&id=31bfc2303d)

[matplotlib colormaps](https://matplotlib.org/stable/tutorials/colors/colormaps.html)

[matplotlib subplots](https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html)

[seaborn gallery](https://seaborn.pydata.org/examples/index.html)

[matplotlib gallery](https://matplotlib.org/2.0.2/gallery.html)

[SPSS with Python](https://www.spss-tutorials.com/python-for-spss-what-is-it/)

[Google Colab](https://colab.research.google.com/?utm_source=scs-index)
