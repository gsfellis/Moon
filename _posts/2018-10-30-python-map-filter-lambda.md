---
layout: post
title:  "Python: Map, Filter, and Lambda Functions"
date:   2018-10-30 14:58:00
excerpt: "A quick introduction to map, filter, and lambda expressions in Python."
tag:
- Python
- map
- filter
- lambda
comments: false
---

![Python](https://upload.wikimedia.org/wikipedia/commons/a/ad/Lozingle_10032014.jpg)

---

Now that school has wrapped up I'm working on preparing myself for the future. I'd like to see myself continue to progress in Computer Science, despite not working with code on a regular basis.  For now I'm working through some <a href="https://www.udemy.com" target="_blank">Udemy</a> courses that have been burning a hole in my back pocket while I focused on school.  Today I decided to take a look at <a href="https://www.udemy.com/user/joseportilla/" target="_blank">Jose Portilla</a>'s <a href="https://www.udemy.com/python-for-data-science-and-machine-learning-bootcamp/learn/v4/overview" target="_blank">Python for Data Science and Machine Learning Bootcamp</a>.  It rates very highly on Udemy, and so far it has not disappointed.

The opening section is a "crash course" in Python.  I like to think I'm relatively up to speed on the basics of the Python programming language, having just completed the [SNHU CS499 Capstone]({% post_url 2018-21-noob-snhubot %}) project, but looking through the section I noticed three things that I am far less familiar with than I care to admit: `map`, `filter`, and `lambda` expressions.  So I quickly brushed through the basics, and settled in to these three functions to get a better understanding of their place in Python.

## Map

The <a href="https://docs.python.org/3/library/functions.html#map" target="_blank">map</a> function in Python is used to apply a `function` over all items within an iterable object.  It technically returns an `iterator`, but will typically be combined with another function to output a new variable.

For our simple example, lets say we have a `list` of numbers, and we want to raise each of those numbers by a power of `2`.  We start by defining a simple function that will return `x` to the power of `2`, and our list that we will feed in to it.

```python
def raise_num(x, n):
    return x ** 2

lst = [1, 2, 3, 4, 5]
```

We want a new list with the values raised, so we could do this _the long way_ by creating a new empty list, running a `for` loop, and appending the new values:

```python
new_list = []
for x in lst:
    new_list.append(raise_num(x))

print(new_list)

# Output:
# [1, 4, 9, 16, 25]
```

_Or_ we can leverage the `map` function combined with the `list` function to convert the iterator to a new list:

```python
new_list = list(map(raise_num, lst))

print(new_list)

# Output:
# [1, 4, 9, 16, 25]
```

Very convenient and clean way to run a function over all elements in a list!  Undoubtedly, there are many other uses for `map`, but I'll be using this simple example often in the future.

## Filter

Like `map`, <a href="https://docs.python.org/3/library/functions.html#filterfilter" target="_blank">filter</a> can be used to generate an iterator over which a `boolean` function is applied on all elements in an iterable.  This is a convenient way to "filter" out values in a list that we don't want.  Suppose we have a list of words, but we want to find all the four letter words, we could use `filter`, again combined with `list` to create a new list of four letter words.

```python
def four_ltr_word(word):
    return len(word) == 4

words = ['lute', 'guitar', 'drum', 'harmonica', 'flute', 'oboe']
```

As above, we could use a `for` loop here, but we'll jump straight to creating a list of four letter words from `words`, using `filter` and `list`:

```python
four_ltr_words = list(filter(four_ltr_word, words))

print(four_ltr_words)

# Output:
# ['lute', 'drum', 'oboe']
```

Again, `filter` applies a `boolean` function over all elements in an iterable, which can be used to filter out elements that evaluate to `false`.

## Lambda

<a href="https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions" target="_blank">Lambda</a> expressions generate `anonymous`, single expression functions wherever they're needed.  In the `map` and `filter` examples, we passed `function` objects as arguments to each of the built-in functions.  We could have conveniently done these using `lambda` expressions, instead of having to define the single use functions that we did.

```python
lst = [1, 2, 3, 4, 5]

new_list = list(map(lambda x: x ** 2, lst))

print(new_list)

# Output:
# [1, 4, 9, 16, 25]

words = ['lute', 'guitar', 'drum', 'harmonica', 'flute', 'oboe']

four_ltr_words = list(filter(lambda word: len(word) == 4, words))

print(four_ltr_words)

# Output:
# ['lute', 'drum', 'oboe']
```

 So there you have it.  A quick introduction to `map`, `filter` and `lambda` expressions.  Again, these are simplistic, yet powerful examples that can be used to clean up a lot of code I've written.  It's easy to remember that you can use a `for` loop and a function definition to get what you want, but working in these short-hand versions will save time, SLOC (source lines of code), and, assuming those reading your code understand what these are doing, makes your code more legible.

 Until next time...
