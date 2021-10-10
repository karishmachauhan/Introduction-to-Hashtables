# Introduction-to-Hashtables
Basic introduction and implementation of Hashtables

Hash tables are data structures that efficently implements sets and dictionaries in python. It is generally used for searching a particular element in millions of files or large datasets. It consists of a hash function which basically converts any value (list, sets, integer etc.) to a numeric value. This numeric value in hash table signifies a particular bucket where those elements in datasets are inserted that satisfy the hash function.

We will use one example each to demonstrate where hash tables are effective or where it is not?

# Installing Libraries
1. pip install lolviz
2. pip install numpy
3. pip install pandas

# Importing libraries

1. from lolviz import *
2. import numpy as np
3. import pandas as pd

# Linear Search Function


lsearch is the name of the function and A is the list and x is the target search element. The function returns true when the element is found.
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
 Hash function to calculate index of buckets of size 1000
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
Hash function to search an elements from hash table which returns true if element is found
```python
    def hsearch(hashtable, search_element):

      index = hash(search_element)
		
      values = hashtable[index]
		
      for value in values:
		
        if (value == search_element):
			
          return True
				
      return False
```
