---
layout: post
title:  "Numpy (Numeric Python)"
date:   2016-06-24 13:41:47 +0530
categories: [python, python3, numpy, array]
tags: [python, python3, numpy, array]
image: NumpyLogo.jpg
---

![NumpyLogo](https://4.bp.blogspot.com/-i4w-atnTgS4/V203GmzZ8FI/AAAAAAAAEeo/Aoa4oZetH7o2I20abq1iORYDe6VDEHZ-gCKgB/s1600/numpy_project_page.jpg "NumpyLogo")
<marquee>
<i class = 'fa fa-soccer-ball-o fa-spin'></i>&nbsp;
<i class = 'fa fa-soccer-ball-o fa-spin'></i>&nbsp;
<i class = 'fa fa-soccer-ball-o fa-spin'></i>&nbsp;
<i class = 'fa fa-soccer-ball-o fa-spin'></i>&nbsp;
</marquee>
**NumPy** is the fundamental package for scientific computing with Python.

It contains among other things:
* a powerful N-dimensional array object
* sophisticated (broadcasting) functions
* tools for integrating C/C++ and Fortran code
* useful linear algebra, Fourier transform, and random number capabilities
* Numeric Python
* Alternative to Python List: Numpy Array
* Calculations over entire arrays
* Easy and Fast

# Installation
* In the terminal:
```bash
pip3 install numpy
```
or
```bash
python3 -m pip install numpy
```

# Introduction
```python
In [6]: import numpy as np
In [7]: np_height = np.array(height)
In [8]: np_height
Out[8]: array([ 1.73, 1.68, 1.71, 1.89, 1.79])
In [9]: np_weight = np.array(weight)
In [10]: np_weight
Out[10]: array([ 65.4, 59.2, 63.6, 88.4, 68.7])
In [11]: bmi = np_weight / np_height ** 2
In [12]: bmi
Out[12]: array([ 21.852, 20.975, 21.75 , 24.747, 21.441])
```
First we imported the numpy package as np
then, we created a new numpy array using **"np.array(LIST_NAME)"**

# Element Wise Calculation
```python
In [13]: height = [1.73, 1.68, 1.71, 1.89, 1.79]
In [14]: weight = [65.4, 59.2, 63.6, 88.4, 68.7]
In [15]: weight / height ** 2
TypeError: unsupported operand type(s) for **: 'list' and 'int'
In [16]: np_height = np.array(height)
In [17]: np_weight = np.array(weight)
In [18]: np_weight / np_height ** 2
Out[18]: array([ 21.852, 20.975, 21.75 , 24.747, 21.441])
```

# Numpy: Remarks
* Numpy arrays: contain only one type
* Different types: different behavior!

```python
In [19]: np.array([1.0, "is", True])
Out[19]:
array(['1.0', 'is', 'True'],
 dtype='')
# Numpy arrays: contain only one type
# Different types: different behavior
In [20]: python_list = [1, 2, 3]
In [21]: numpy_array = np.array([1, 2, 3])
In [22]: python_list + python_list
Out[22]: [1, 2, 3, 1, 2, 3]
In [23]: numpy_array + numpy_array
Out[23]: array([2, 4, 6])
```


Numpy Arrays can only store values of one datatype, if you insert more then one type values, then the complete array will be converted in the highest precise datatype, most of the time, it is string

# Numpy Subsetting

You can with regular Python lists. When you want to get elements from your array, for
example, you can again use square brackets.
Suppose you want to get the `bmi` for the
second person, so at index 1.

This will od the trick:
Specifically for Numpy, there's also another way to do list subsetting: using an array
of booleans.

Say you want to get all BMI values in the bmi array that are over 23.

A first step is using the greater than sign, like this:
The result is a Numpy array containing booleans: True if the corresponding bmi is above 23,
False if it's below. Next, you can use this boolean array inside square brackets to dosubsetting. Only the elements in `bmi` that are above 23, so for which the corresponding
boolean value is True, is selected. There's only one BMI that's above 23, so we end up
with a Numpy array with a single value, that BMI.
Using the result of a comparison to make a selection of your data is a very common way to get surprising insights

```python
In [24]: bmi
Out[24]: array([ 21.852, 20.975, 21.75 , 24.747, 21.441])
In [25]: bmi[1]
Out[25]: 20.975
In [26]: bmi > 23
Out[26]: array([False, False, False, True, False], dtype=bool)
In [27]: bmi[bmi > 23]
Out[27]: array([ 24.747])
```
