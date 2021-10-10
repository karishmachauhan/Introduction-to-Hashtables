# Introduction-to-Hashtables

Hash tables are data structures that efficiently implement sets and dictionaries in python. It is generally used for searching a particular element in millions of files or large datasets. It consists of a hash function that converts any value (list, sets, integer, etc.) to a numeric value. This numeric value is the index of a hash table where the corresponding values are stored.

# Analogy
Let's take an example of a library. A hash table bucket is like a rack in a library. Let's consider each shelf of the rack has books arranged in alphabetical order from top to bottom. The top shelf has all the books starting from A, and then the next shelf has all the books starting from B and so on. Now, if we want to look for a book titled 'Apple,' we will first locate where A is, and then we will linearly start looking at the names of each book on that shelf until we find the book with the name Apple. <br>
<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/library.gif" width="200" height="200" />
<br><br><br><br><br><br><br><br><br>
Here, the rack is an entire hash table, and each shelf is a bucket. Key is the book name, and value is the whole book that we wanted as a result. In hash tables as well, we have a certain number of buckets that hold a certain number of key-value pairs in them. So, whenever we want to look for a specific value, we provide its key to look where the value lies.

# Hashtable Visualization

Considering a hashtable with the hash key as the first letter of the element, this is how the strings would be stored in a hashtable

<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/visualization.png" width="300" height="450" />
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Examples to demonstrate where hash tables are effective and where it is not.

# Installing Libraries
1. pip install lolviz
2. pip install numpy
3. pip install pandas

# Importing libraries

1. from lolviz import *
2. import numpy as np
3. import pandas as pd

# Linear Search Function


lsearch is the function's name, A is the list, and x is the target search element. The function returns true when the element is found.
```python
    def lsearch(A, search_element):

      #Looping through list to find the element x
	
      for row in A:
	
      # Condition if any element in A 
		
       if row == search_element:
		
        # The function returns True that means, search element is present in the list_A
			
        return True 
			
      return False
 ```
  
# Creating a hash function 
 Hash function to calculate the index of buckets of size 1000
```python
    def hash(x):
      return x % 1000
```
# Initializing and filling buckets 
Initializing empty buckets and filling array values
```python
    buckets = [[] for i in range(1000)] 
    
# Filling up buckets
Filling buckets with array elements

    for a in A:

      index = hash(a)
		
      values = buckets[index]
		
      if (values == None):
		
        values = []
			
      values.append(a)
		
      buckets[index] = values
```
# Hash search Function
Hash function to search an element from the hash table, which returns true if the element is found
```python
    def hsearch(hashtable, search_element):

      index = hash(search_element)
		
      values = hashtable[index]
		
      for value in values:
		
        if (value == search_element):
			
          return True
				
      return False
```
# Comparison
Clearly, hashtables are much faster!

<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/comparison.png" width="400" height="250" />
<br><br><br><br><br><br><br><br><br><br>



# The Trade-off

Traded off Complexity for Time

*   Linear Search : 
        • Lesser Complexity
        • More Time
     
*   Hashtable Search :
        • More Complexity
        • Less Time

# Be careful with Hash functions

Sometimes you might create a hash function that will end up putting all elements in a single bucket. One such example is:
```python
def hashfunction(str):
    return len(str)
```
Now, if all elements of string have the same length, they will all end up in a single bucket like:
<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/single%20bucket.png" width="500" height="200" />
<br><br><br><br><br><br><br><br><br><br>
And this will make hashtables useless because it is even worse than a linear search. After all, it is like a linear search with added complexity.

# Summary

When we need to look through a huge corpus of data, a hash table is our best friend. However, you have to be careful if your data set is small or your hash function puts most or all of the data in a single bucket because you might end up increasing complexity without really getting the benefit of reduced execution time.
