---
title: "Iterable Iterator concept in Python"
date: 2023-05-13
---


**In short:** 
Iterbale support __iter__, and maintain the data.
Iterator support __next__, and reach the data.

# Iterable
## Official defination
Any object that supports *iter()* and return iterator is said to be "iterable."
example:
- list, str, and tuple are classical example of iterables
- Some non-sequence types like dict, file objects are iterables.
- Objects of any classes you define with an __iter__() method or with a __getitem__() method that implements sequence semantics are iterables.  

Iterables can be used in a for loop and in many other places where a sequence is needed.  
built-in function iter(), it returns an iterator for the object.  

# Iterator
## Official definition
The iterator objects themselves are required to support the following two methods, which together form the iterator protocol:
iterator.__iter__() return itself.
iterator.__next__() return one data and maintain state.

**But CPython doesn't consistently apply**

# Iterable vs. Iterator
```python
lst = [1,2,3]
i_lst = iter(lst)
```
- lst is iterable, but not iterator.
- i_lst is iterator and also iterable. i_lst is list_iterator object

An iterable can returns a **fresh** ITERATOR.
An iterator can return itself. 
And iterator also is an object with a __next__ method that returns the next value in the iteration and updates the state to point at the next value

# Pure iterables
Maybe we can produce a pure iterable concept.
Pure iterables typically hold the data themselves, and return a fresh iterator.
In contrast, iterators are not pure iterables that don’t hold the data but produce and maintians state. 

# Conclusion
Many people say iterator is iterable as well, and iterable don't have to be iterator. 
But they also say iterator and iterable are different, like iterables are more effecient in memory consumsion. 
That is confusing concept. 
I reckon iterator don't have to support __iter__().  That means iterator don't have to be iterable. Just like JavaScript.




