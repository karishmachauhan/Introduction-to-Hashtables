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


lsearch is the name of the function and A is the list and x is the target search element
```python
    def lsearch(A, search_element):

      #Looping through list to find the element x
	
      for row in A:
	
      # Condition if any element in A 
		
       if row == search_element:
		
        # The function returns True that means, search element is present in the list_A
			
        return True 
			
      return False
  
 # Creating a hash function 

    def hash(x):
      return x % 1000

# Make sure each bucket is a separate list

    buckets = [[] for i in range(1000)] 

# Filling up buckets


    for a in A:

      index = hash(a)
		
      values = buckets[index]
		
      if (values == None):
		
        values = []
			
      values.append(a)
		
      buckets[index] = values

# Hash search Function which returns true if element is present

    def hsearch(hashtable, search_element):

      index = hash(search_element)
		
      values = hashtable[index]
		
      for value in values:
		
        if (value == search_element):
			
          return True
				
      return False
```
