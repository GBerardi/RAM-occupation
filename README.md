# RAM occupation 

Python:
- every object in python has a reference count and a reference to the object type, in a 64 bit machine these alone are 16 bytes
  - python int: 28 bytes
  - python string: 49 bytes + 1 byte per character

Numpy:
- a numpy array has additional costs in general
  - Numpy will assign to an array of strings a dtype that is capable to contain the longest string, if the strings have different lenghts, this will occupy more memory than the needed amount ( > the python strings memory occupation). An alternative is to assign "object" as dtype, in this case the array will save a reference to every object, this results in a cost of 8 bytes per element (+ the element cost itself).



What cost a lot of memory:
- long strings arrays occupy an important amount of memory --> don't save long strings if possible, don't save full paths for example, save only the part that change and save in a different way the repeated part
- numpy.in1d results in memory picks (search for elements of an array in a second array)
