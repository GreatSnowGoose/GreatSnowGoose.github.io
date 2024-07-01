---
title: "Python Introduction"
date: 2024-05-29T12:47:35-06:00
lastmod: 2024-05-30T16:35:35-06:00
draft: true
summary: "Some very very basic python knowledge that can be found everywhere online."
tags: ["tutorial", "coding", "python"]
categories: ["TechDoc"]
series: ["Coding Essentials for My Successor"]
series_order: 1
---

In this post, we are going to install Python and code editor, look at the ten Python data types, and write a few lines of very simple Python code. You may need to use Terminal in some cases, but I won't touch the details about shell scripts here.

## Installation and Useful Links

Python: [Download from the official site.](https://www.python.org/downloads/)

Code editor:

- [Install JupyterLab](https://jupyterlab.readthedocs.io/en/latest/getting_started/installation.html)
  - [What are JupyterLab and Jupyter Notebooks?](https://jupyter.org)
  - [JupyterLab or Jupyter Notebooks?](https://stackoverflow.com/questions/50982686/what-is-the-difference-between-jupyter-notebook-and-jupyterlab) 👉 JupyterLab in short.
- [Install Visual Studio Code](https://code.visualstudio.com)
  - [Very Nice Editing Features!](https://code.visualstudio.com/docs/editor/codebasics)
  - [Use Jupyter Notebooks in VS Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- [Visualize and Breakdown Your Code](https://pythontutor.com)

### Notes

My current most frequently used editor is Visual Studio Code, since it has very powerful editing feathers including multiple selection, powerful find and replace, and easy folding and unfolding. With [Stata Enhanced](https://marketplace.visualstudio.com/items?itemName=kylebarron.stata-enhanced) extension, I even write Stata code in it, since the Stata do file editor cannot fold easily with tabs, and thus bad for long do files.

To start coding in Python, I think Jupyter Notebook is a good starting point, as you can get the output for each code block, which is very helpful to see what changes your code has made. After you are comfortable with coding, you can directly write your scripts in python files.

Then, let's open a new Jupyter notebook and write our very first line of code:

```python
print("Hello World!")
```

## Data Types

To get the type of a variable, use `type()` function. You can easily find all the python data types [online](https://www.w3schools.com/python/python_datatypes.asp). I'm going to cover the ones I usually use in this section.

### int

```python
i = 5
print(type(i))
```

### float

```python
f = 0.5
print(type(f))
```

**Note 1:** Division and multiplication will change integer to float, so use `int()` convert the data type if you do not wish this happens.

```python
f = 200
g = f/2
print(g, type(g))

k = f * 0.5
print(k, type(k))

l = int(f/2)
print(l, type(i))
```

**Note 2:** Division and multiplication are different in precision. Use `round()` to get desired number of digits.

```python
n = 56
a = n * 0.1
b = n / 10
print(a, b, a == b)
print(round(a,1), round(b,1), round(a,1) == round(b,1))
```

### str

Strings are indexed in Python. Therefore, you can apply slicing to strings.

```python
s = "String"
s1 = s[:4]
print(s1)
```

**Note 1:** Indices start from 0.

```python
s2 = s[0]
print(s2)
```

**Note 2:** String is immutable.

```python
s[0] = s
```

You will get a TypeError from the code above.

**Note 3:** f-string

You can use `+` to combine strings, but sometimes it can be tedious, and f-string can be a better choice.

```python
p = "A"
page_num = 220
s3 = "part " + p + " page " + str(page_num)
print(s3)
s4 = f"part {p} page {page_num}"
print(s4)
```

**Note 4:** You can use `""` inside `''` or `''` inside `""`.

```python
s = '"Cat"urday'
h = "Shakes'pear'e"
print(s, "\n", h) # "\n" to change line
```

**Note 5:** Python has many built-in functions for string. You can change cases of letters, removing extra spaces, finding the position of a certain word, etc. You don't need to remember them. You only need to be aware that they exist, and you can find them when you need to use them. Use Google to find these ==Python String Methods== and have an impression of them.

### bool

The values are `Ture` and `False`. When you write if-condition or while loop, the program proceed when the statement is `Ture`. Empty values, such as empty list and empty set, 0, and `False` itself are equavalent to `False`.

```python
print(bool(1))
print(bool(0))
print(bool([1]))
print(bool([]))
```

### set

Sets do no have orders or duplicate elements.

```python
set_1 = {1,2,3}
set_2 = {3,2,1}
set_3 = {1,2,3,3,3}
print(set_3)
print(set_1 == set_2, set_1 == set_3)
```

**Note 1:** You can not apply slicing to the set.

```python
print(set_1[1])
# And you will get a TypeError
```

**Note 2:** I do not usually use set in my code.

### list

List is my most frequently used data type. List items are ordered and mutable, allow duplicate values, and can contain any data type.

```python
# Indices also start from 0.
list_1 = [1,2,3,4]
print(list_1[0])

# Use slicing. Left index is included, but right index not.
list_2 = list_1[2:]
list_3 = list_1[0:2]
print(list_2)
print(list_3)

# mutable
list_3 = [0,1,2,3,4]
list_3[0] = 9
print(list_3)
```

**Note 1:** Working with list is much easier than working with string. Use `split()` and `join()`

```python
str_1 = "Splits the string at the specified separator"
list_1 = str_1.split()
str_2 = f"{"_".join(list_1[:4])} {" ".join(list_1[4:])}"
print(str_2)
```

**Note 2:** [Visualize](https://pythontutor.com) the code below to understand the mutability of list.

```python
# int is not mutable.
a = 1
b = a
a = 2
print(b) # b is still 1

# list is mutable
a = [1,2,3,4]
b = a
a[0] = 9
print(a)
print(b) # The first element will change as a changes
```

**Note 3:** Like string, there are also built-in list functions in python. Search ==Python List Methods== and have an impression of them.

### dict

Dictionaries store data in key:value pairs. I mainly use this to generate data frame in pandas.

```python
dict_1 = {
  'country': 'US',
  'state': 'Alabama',
  'capitol city': 'Montgomery'
}

print(dict_1['country'])
```

### range

## if

## for

### List Comprehension

## while

## Exercises

1. You have a 20-page pdf document and want to save each page as a single "png" file. Create a list of file names with the format of `page_#.png`.

2. Get the unique values of the list `l = [0, 1, 1, 1, 3, 4, 6, 2, 2, 5, 5, 10]` in ascending order

3. Print years 1900-1930 except for the leap years.

4. Generate a list of year-month pair from Jan 1800 to Dec 1850.
