![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Data Carpentry Day 2

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
09:00 |	Recap of Day 1
09:15 |	Introduction to Python
10:15 |	Coffee break
10:30 |	Introduction to Python (continued)
11:30 |	Coffee break
11:45 |	Introduction to Python (continued)
12:45 |	Wrap-up
13:00 |	END


## 🔧 Exercises

### Excercise: helf function in Jupyter
1. Type "print"
2. Press "Shift + Tab"
3. Read the help function, try to use different options of the "print" command. Try to figure out what does "sep" and "end" mean.

#### Answers:
Alessandra: sep put a space, or a value between values, end defines the last part of the line 
Anita 
Bram 
Carlotta: sep defines a separator between values; end is what appears after the last value
Elisa: sep defines a separator, end defines the end of a line
Josephine: separate values by space and start a new line
Jurgen
Maosheng
Marte
Maryam
Min
ricarda: separator and end of line 
Roel: **sep** devines what to use as separator, **end** controls what is done at the end. ie new line or add ; or both
Rosanne: With sep i can give the character that i want to see between multiple values, with end, the character that i want to see on the end.
Suraya: Will happily see this in practice (from someone else)
Thoa
Tom: separator/white space? end: I don't know, getting an error
Veronica.
X Ouyang sep is the seperator; end is something added to the end.

Solution:
sep: separator of multiple print contents. By default this is a space " ". 
We can see how it works by trying:
```python
print("a is", a, "b is", b)
print("a is", a, "b is", b, sep="_")
```

end: the string appended to the end of the print line. By default this is a line change "\n"
We can see how it works by comparing:
```python
print("a is", a, "b is", b, end="\n")
print("end")
```
```python
print("a is", a, "b is", b, end=" ")
print("end")
```

### Exercise: Boolean values
Imagine you are considering different ways of representing a boolean value in your data set and you need to see how Python will behave based on the different choices. Fill in the blanks using the built-in functions we’ve seen so far in following code excerpt to test how Python interprets text.
Which ways of representing a boolean value result in Python interpreting it as a boolean True?

Hint: Use "type" or "bool" function to replace the "___".

```python
bool_val1 = 'TRUE'
print('read as type ',___(bool_val1))
print('value when cast to bool',___(bool_val1))

bool_val2 = 'FALSE'
print('read as type ',___(bool_val2))
print('value when cast to bool',___(bool_val2))

bool_val3 = 1
print('read as type ',___(bool_val3))
print('value when cast to bool',___(bool_val3))

bool_val4 = 0
print('read as type ',___(bool_val4))
print('value when cast to bool',___(bool_val4))

bool_val5 = -1
print('read as type ',___(bool_val5))
print('value when cast to bool',___(bool_val5))
```
Answers:
Alessandra type; bool. TRUE, FALSE, 1, -1 are boolean values, but not 0
Anita
Bram
Carlotta
Caterina
Elisa: str; str; int; int; int; True, True, True, False, True. Question :question: why are FALSE and -1 considered True by Python?
Josephine: val1: str, True; val2: str, true; val3: int, true; val4:
Jurgen: True, True, True, False, True
Maosheng
Marte
Maryam read as type  <class 'str'>
value when cast to bool True
read as type  <class 'str'>
value when cast to bool True
read as type  <class 'int'>
value when cast to bool True
read as type  <class 'int'>
value when cast to bool False
read as type  <class 'int'>
value when cast to bool True
Min
ricarda
Roel: str, true; str, true; int, true; int, false; int, true
Rosanne: T,T,T,F,T. Strings are bool-True unless they are empty, intergers are bool-True unless they are zero.
Suraya
Thoa: bool_val1, bool_val2 is str, true; bool_val3: int; true; bool_val4 int; false; bool_val5 int true
Tom: str/true; 
Veronica
X Ouyang 'str' True; 'str' True; 'int' True; 'int' False; 'int' True

#### Solution and explaination:

Types: str, str, int, int, int
Bools: True, True, True, False, True

Python treats all strings and non-zeros numbers as True. 'True' and 'False' are also strings. 1 and -1 are both non-zero number so they are also True. 


### Exercise: List indexing
Complete the code below and display the value of last_num_in_list which is 11 and values of odd_from_list which are 5 and 11 to check your work.
```python=
num_list = [4,5,6,11]

last_num_in_list = num_list[____]
print(last_num_in_list)

odd_from_list = [num_list[_____], ______]
print(odd_from_list)
```

Done?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: 
|Anita       | |
|Bram        | |:heavy_check_mark:
|Carlotta    | |
|Caterina    | |
|Elisa       |:heavy_check_mark: |
|Josephine   | |
|Jurgen      | :heavy_check_mark:|
|Maosheng    | |
|Marte       | |
|Maryam      | :heavy_check_mark:|
|Min         | |
|ricarda     | |
|Roel        | :heavy_check_mark:|
|Rosanne     | :heavy_check_mark:|
|Suraya      | :heavy_check_mark: 
|Thoa        | :heavy_check_mark:
|Tom         | :heavy_check_mark:|
|Veronica    | |
|X Ouyang    |:heavy_check_mark: |

Solution:
Last number:
```python=
num_list = [4,5,6,11]

last_num_in_list = num_list[3]
print(last_num_in_list)

last_num_in_list = num_list[-1]
print(last_num_in_list)
```
Note the `list` also accept negative indexcing, counting from the end of the list. 

Odd number:
```python=
odd_from_list = [num_list[1], [num_list[-1]]
print(odd_from_list)
```

### Exercise: Ranges
We have created a list using range + step value:
```python=
list(range(2,11,2))
```

1. What is produced if you change the step value in my_list to -2 ? Is this what you expected?
2. Create a list using the range() function which contains the even numbers between 1 and 10 in reverse order ([10,8,6,4,2])

Done?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: 
|Anita       | |
|Bram        | :heavy_check_mark:
|Carlotta    | |
|Caterina    | |
|Elisa       |:x: (can't solve the second question) |
|Josephine   | |
|Jurgen      | :heavy_check_mark: |
|Maosheng    | |
|Marte       | |
|Maryam      | |
|Min         | |
|ricarda     | :heavy_check_mark:|
|Roel        | :heavy_check_mark:|
|Rosanne     | :heavy_check_mark:|
|Suraya      | :heavy_check_mark:|
|Thoa        | |
|Tom         | :heavy_check_mark:|
|Veronica    | |
|X Ouyang    |:heavy_check_mark: |

Solution:

1. You get an empty list, because Python starts at 2, count with a step value of -2, to 11, which is a wrong counting direction. Therefore we have a empty list.
2. You can switch the start/end of the range, and use a negative step size:
```python=
list(range(10, 1,-2))
```

### Exercise: for-loop
Suppose that we have a string containing a set of 4 different types of values separated by "," like this:
```python=
variablelist = "01/01/2010,34.5,Yellow,True"
```
Research the `split()` method and write a for-loop that prints each of the 4 components of `variablelist`

Done?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: 
|Anita       | |
|Bram        | :heavy_check_mark:
|Carlotta    | |
|Caterina    | |
|Elisa       |:heavy_check_mark: |
|Josephine   | |
|Jurgen      | :heavy_check_mark:|
|Maosheng    | |
|Marte       | |
|Maryam      | |
|Min         | |
|ricarda     | |
|Roel        | :heavy_check_mark:|
|Rosanne     | :heavy_check_mark:|
|Suraya      | :heavy_check_mark:|
|Thoa        | :heavy_check_mark:
|Tom         |:heavy_check_mark: |
|Veronica    | |
|X Ouyang    |:heavy_check_mark: |

Solution:
You can set `sep=","` to split the long variable into a list with comma.
Then you can loop through the list.
```python=
variablelist = "01/01/2010,34.5,Yellow,True"
for word in variablelist.split(sep=","):
    print(word)
```


## 🧠 Collaborative Notes

### Python installation working?
| Name       | :heavy_check_mark: or :x: |
|------------|-|
|Alessandra  | :heavy_check_mark: 
|Anita       | :heavy_check_mark:
|Bram        | |
|Carlotta    | :heavy_check_mark:|
|Caterina    | |
|Elisa       |:heavy_check_mark: |
|Josephine   | :heavy_check_mark: 
|Jurgen      | :heavy_check_mark:
|Maosheng    | |
|Marte       | |
|Maryam      |:heavy_check_mark: |
|Min         | |
|ricarda     | :heavy_check_mark:|
|Roel        | :heavy_check_mark: |
|Rosanne     | :heavy_check_mark:|
|Suraya      | :x: |
|Thoa        | :heavy_check_mark:
|Tom         | :heavy_check_mark:|
|Veronica    | :heavy_check_mark:
|X Ouyang    | :heavy_check_mark:|

### Reason to use Python
- Easy to use: can run what you type directly
- Open and active community: many ready-to-use packages

### Creating variables
1. Create a new Notebook using the interface icon
2. Good to rename your Notebook to find this Notebook back later
3. Cell: the small box in the JupterNotebook you can type your commands in
4. Create varialble and assign values to them:

```python
    a = 2
    b = 3.142
```
5. To exectute the cell, press "Shift + Enter"
6. Print the variable:

```python
   print(a)
```

JupyterNotebook also automatically print thelast commad you run. You can print the variable `a` by simply typing "a" in your cell.

### Type of the variable

There are different types of a variable. You can check this by:

```python=
    print(type(a))
    print(type(b))
```

Common types are `int`(intiger), `float`(decimal), and `str`(string)

### Export a Notebook

File -> export Notebook as...
If you choose "executable scripts", you will have an executable ".py" file can run with Python.

### Manipulate variables

Sum:
```python=
print(a+b)
```

The results (5.141999999999...) will not be exactly mathematically correct due to how computer store the float number. A tiny bias always exists.

More manipulations:

Multiplication: `print(a*b)`

Power:`print(a**b)`

Division: 
```python=
d = 8
e = 3
print(d/e)
```

Modulo (remainder of division):`print(d%e)`

Long formula: `print(2*(a+b))`

### Help function

Excercise on line 116.

Way 1: type in a function in the cell and press "Shift + Tab"

Way 2: Put the function name in the `help` command:`help(print)`

### Type conversion

Create a string "3.142" and assign it to "a":`a = "3.142"`
This string can be converted to a float:
`float(a)`. You can verify by `print(type(float(a)))`
The conversion does not always work. E.g `int(a)` will give an error.
Covert int to float: `float(2)` gives you 2.0
Convert float to int will cut off the decimal part: `float(3.9)` gives 3. (THIS IS NOT ROUNDING!)

### Strings

Create a string with a name: 
```python=
name="Leon"
print(name)
```

Create a sentence and add the name in: 
```python=
my_sentence = "My name is " + name + '.' 
print(my_sentence)
```
Should give you "My name is Leon."

Counting characters in the centence using the "len" function: `len(my_sentence)`

Convertiong all characters to upper case: `my_sentence.upper()`. In this case "upper()" is a method available within the `str` type.

You can check available functions within a variable using `dir()` function. E,g,: `print(dir(my_sentence))`

Some functions, like "print()", "len()" and "dir()", are Python built-in functions, which is available when Python is lauched. Some methods, like ".upper()", are appened to a certain type, and can only be used with a string instance, e.g. "my_sentence.upper()".

See if a string starts with a certain pattern:

```python=
    my_string = "The quick brown fox"
    my_string.startwith("The")
```
This give True

It case sensitive so `my_string.startwith("the")` gives False.

Find postion of a pattern:
```python=
    my_string.find("quick")
```
This gives 4 since it starts at the 5th character. Note that Python counts from 0. It only find the first occurance

Count words:
```python=
    my_string.find("fox")
```
Gives 1 since "fox" only occurred once.

Replace:
```python=
    my_string.replace(" ", "_")
```

### Boolean type
(A fancy name for True and False)

`True` and `False` are reserved keywords in Python. You cannot create a varaible named "True" or "False".
Python is case sensitive so "true" or "false" are not Boolean values.

Equal comparision: double equal sign: "=="
`print("hello" == "HELLO")` gives False.
`print(3 == 4)` gives False.

Unequal comparision: "!="
`print(3 != 4)` gives True.

Number comparision: "<" ">"
`print(3 < 4)` gives True.

Exercise at line 161.

### List

Create a list with square brackets "[]"

```python=
    list1 = [6, 54, 89]
    print(list1)
    print(type(list1))
```
should give "[[6, 54,89]]" and "<class 'list'>"

List can contain different types:
```python=
    list2 = [6, "hello", 3.1]
```

Extract a single element:`list2[0]` gives 6. Note that Python counts starting from 0.

Select a range in the list:`list1[0:2]` gives [6, 54]. "0:2" is a "slice" which specifies continuous indexes. Note 0:2 does not include the element 2.

Select multiple non-adjacent elements: `list3 = [list1[0], list1[2]]`.

Exercise on line 228.

### Numpy (additional info)
It's also quite common in the academic community to save list of numbers via [numpy array](https://cs231n.github.io/python-numpy-tutorial/#arrays). Note that to run `import numpy as np` you need to install numpy in your Python environment first.
```python=
import numpy as np
numpy_list_np_array = np.array(num_list)
# Find odd number
numpy_list_np_array = np.array(numpy_list_np_array%2==1)
```

we will cover this part in the later part of the workshop (Day 3 and Day 4).

### Range
You can also create a list from `range` function

```python=
list(range(5))
```
Gives[0, 1, 2, 3, 4]

```python=
list(range(1,9))
```
Gives[1, 2, 3, 4, 5, 6, 7,8]

```python=
list(range(2,11,2))
```
Gives[2, 4, 6, 8, 10]

Execercise on line 282.

### "if" statement

"if" statement conditionally executes your script.

Structure:
```python=
if statement:
    statement 1
    statement 2
    
statement always executed
```
Pay attention to: the colon and indentation.

Example:
```python=
value = 5
threshold = 4
print("value is", value, "threshold is", threshold)
    
if value>threshold:
    print(value "is bigger than", threshold)
```
This will execute both the first and the second `print`. However if you change the value to 3, the second `print` won't be executed.

You can also add an `else` to your `if` statement, to excute some code if the statement is not True

```python=
value = 5
threshold = 4
print("value is", value, "threshold is", threshold)
    
if value>threshold:
    print(value "is bigger than", threshold)
else:
    print(value "is not bigger than", threshold)
    
print("end")
```

Another keyword "elif" can be used to add extra statements:
```python=
value = 5
threshold = 4
print("value is", value, "threshold is", threshold)
    
if value>threshold:
    print(value "is bigger than", threshold)
elif value==threshold:
    print(value "is euqal to", threshold)
else:
    print(value "is smaller than", threshold)
    
print("end")
```

### "for" loop
Commonly used to loop over the items in the list.

For exmaple we create a new list:
```python=
my_list = [1,2,3,True,"hello"]
print(my_list)
```

We can print the list item one by one:
```python=
for item in my_list:
    print(item)
```

We can also use for loops on string. First we create a long string and split it into a list. Then print every word out:
```python=
long_string = "The quick brown fox jumped over the lazy sleeping dog"
for word in long_string.split():
    print(word)
    print(word.upper())
```

Excercise on line 323.

### Functions

We have used funtions e.g. `int()` , `range()` which are Python built-in functions.

Functions can be re-used in your code.

An example of using a function: given a long string `items_owned` to find how many items are owned. The 

```python=
items_owned = "bycycle;televvision;solar_panel;table"
```

we can define a function like:
```python=
def get_item_count(item_str, sep):
    '''
    This function counts the number of items in a string.
    '''
    item_list = item_str.split(sep)
    num_items = len(item_list)
    return num_items
```
You can use triple quotes (''') to add help info to your function.

When you execute the above cell, nothing will show up in Jupyter. But the function will be saved in your environment. Then you can call this function by:

```python=
number_of_items = get_item_count(items_owned, ";")
print(number_of_items)
```

## Tips
- In addition to saying which line number a certain excercise is in, it would be useful to get a direct link, so you don't have to scroll that much and don't have to go to the editor mode
- It was tough/fast to learn about 'the vision' (division...) and 'modular' (modulo). Perhaps useful to give some links for 'pre-reading' to familiarize oneself with certain concepts that are being used. In this case, I was able to catch up a bit by quickly Googling and reading on https://www.freecodecamp.org/news/the-python-modulo-operator-what-does-the-symbol-mean-in-python-solved/ what Modulo was
- It would be great that we can have a notebook about all the teaching meterials. Like you mentioned you skipped the "if" exercises. And I think it would be great if we can have this and practice after class. Thanks!
- It was difficult to read the numbers in the collaborative document and check the lines were the exercises were. Plus, I had issues entering the zoom link. Would be nice to have extra exercises to practice with.
- What might have been helpful for my fellow course-takers was if you'd said that you can use # to insert a comment into the code. That was really helpful to me because for each line of code I also wrote a short comment of what the code does. Yeah, a "book" of exercises would also help me in the future, I guess :slightly_smiling_face: 
- The zoom link was unclear this morning. 
- I did notice that quite a few people were not able to put :heavy_check_mark: , I was wondering if they were being helped out by a helper in a breakout room
- Perhaps make clear when the teacher is showing stuff, whether the participants are advised to type along or not. When I typed along, it helped me, but at the same time, it was difficult to have enough attention to Leon
- I don't know how I'll be able to remember it all. As the session progress it all makes more sense but I hope there will be some spcae towards the end of the course to discuss how I can use Python with large financial datasets. I support students/researchers with large datasets from financial databases, and would like to see Python in practice within my field.
- I struggled a bit today navigating the collaborative document, I kept losing the location of exercises, wasted a bit of time trying to find stuff in there. 
## Tops
- Very clear! I loved it! Also the exercises were useful and not too difficult to execute. Got immediate help with the zoom link from the organizers. I like the fact that wuestions have a lot of spaces and answered immediately.
- Very clear and very nicely paced!  
- clear description on the data types and the functions you can use on a variable
- Just like yesterday, I really like the atmosphere and I feel at ease to ask questions. 
- Great pace and very easy to follow! Had fun!
- Good pace, but I'm a slow learner. Doing while listening was very helpful.I really appreciate the additional support for slow coaches such as myself.  
- I collect much things from Python, very good execises

## 📚 Resources
[Google Colab](https://colab.research.google.com)
