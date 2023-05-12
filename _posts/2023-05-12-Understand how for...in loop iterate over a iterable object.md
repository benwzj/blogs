---
title: "Understand how for...in loop iterate over a iterable object"
date: 2023-05-12
---


- What the core point is that it is a lazy processing.

- I am going to make two example to display how for...in loop work underneath the cover.
First one is loop over a enumerate object, and second one is loop over a range object, it raise error.

-- First example:
lst = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for i, value in enumerate(lst):
   lst.pop(i)
print(lst)

- There are No error raising for these codes, but they are not work as expected.
the code print below:
[1, 3, 5, 7, 9] 
- enumerate object is generator object which will yield value from lst. It is lazy process. 
- When lst change, value from enumerate object change as well, but i is keep going. 

- for...in is equivalent to:
_iter = iter(enumerate_obj) 
while 1:
 try:
   x = _iter.__next__() 
 except StopIteration:
   break
 # statements

- enumerate() is equivalent to:
def enumerate(lst):
    n = 0
    for i in lst:
        yield n, i
        n += 1

-- Second example:
lst = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for i in range(len(lst)):
   lst.pop(i)

- This code will raise IndexError



- range() is iterable, but len(lst) in range() parameter here have been replace with constant value 10. Because len(lst) is not a lazy process. it don’t change any more. So i will up to 9. 

- So the codes are equivalent to:
for i in range(9):
   lst.pop(i)
