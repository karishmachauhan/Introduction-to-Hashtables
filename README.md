# Introduction-to-Hashtables
Basic introduction and implementation of Hashtables

Hash tables are data structures that efficently implements sets and dictionaries in python. It is generally used for searching a particular element in millions of files or large datasets. It consists of a hash function which basically converts any value (list, sets, integer etc.) to a numeric value. This numeric value in hash table signifies a particular bucket where those elements in datasets are inserted that satisfy the hash function.

# Analogy
Let's take an example of a library. A hash table bucket is like a rack in a library. Let's consider each shelf of the rack has books arranged in alphabetical order from top to bottom. The top shelf has all the books starting from A, and then the next shelf has all the books starting from B and so on. Now, if we want to look for a book titled 'Brooklyn,' we will first locate where B is, and then we will linearly start looking at the names of each book on that shelf until we find the book with the name box. <br>
<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/library.gif" width="200" height="200" />
<br><br><br><br><br><br><br><br><br><br><br>
Here, the rack is an entire hash table, and each shelf is a bucket. Key is the book name, and value is the whole book that we wanted as a result. In hash tables as well, we have a certain number of buckets that hold a certain number of key-value pairs in them. So, whenever we want to look for a specific value, we provide its key to look where the value lies.

# Hashtable Visualization

Considering a hashtable with hash key as first letter of element. This is how string would be stored in a hashtable:

<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/visualization.png" width="200" height="200" />

We will use one example each to demonstrate where hash tables are effective and where it is not.

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
# Comparison


<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/comparison.png" width="200" height="200" />



# The Trade-off

Complexity for Time

*   Linear Search : 
        • Lesser Complexity
        • More Time
     
*   Hashtable Search :
        • More Complexity
        • Less Time

# Be careful with Hash functions

Sometimes you might end up creating a hash function that will end up putting all elements in single bucket, once such example is:
```python
def hashfunction(str):
    return len(str)
```
Now if all elements of string have same length they will all end up in single bucket like:
<img align = 'left' src="https://github.com/karishmachauhan/Introduction-to-Hashtables/blob/main/Images/single%20bucket.png" width="200" height="200" />
And this will make hashtables useless because it is even worse then linear search because it is like linear search with added complexity.
