## Python Pickle
Python pickle module is used for serializing and de-serializing a python object structure. Any object in Python can be pickled so that it can be saved on disk.
Picking is a way to convert a Python object(list, dictionary, etc.) into a character stream. The idea is that this character stream contains all the information necessary to reconstruct the object in another Python script. It provides a facility to convert any Python object to a byte stream. This Byte stream contains all essential information about the object so that it can be reconstructed, or “unpickled” and get back into its original form in any Python.

example

```
import pickle

# initializing data to be stored in db
Omkar = {'key' : 'Omkar', 'name' : 'Omkar Pathak', 
'age' : 21, 'pay' : 40000}
Jagdish = {'key' : 'Jagdish', 'name' : 'Jagdish Pathak',
'age' : 50, 'pay' : 50000}

# database
db = {}
db['Omkar'] = Omkar
db['Jagdish'] = Jagdish

# For storing
# type(b) gives <class 'bytes'>;
b = pickle.dumps(db) 

# For loading
myEntry = pickle.loads(b)
print(myEntry)
```

Advantages of Using Pickle in Python
1. Recursive objects: Pickle keeps track of the objects it has already serialized, so later references to the same object won’t be serialized again. 
2. Object sharing: This is similar to self-referencing objects. Pickle stores the object once, and ensures that all other references point to the master copy. Shared objects remain shared, which can be very important for mutable objects.
3. User-defined classes and their instances: Pickle can save and restore class instances transparently. The class definition must be importable and live in the same module as when the object was stored.

Disadvatages of Using Pickle in Python
1. Python Version Dependency: Data of pickle is so sensitive to the version of Python that produced. Pickled object created with one version of Python that might not be unpickled with a various versions.
2. Non-Readble: The format of pickle is binary and not easily readable or editable by humans. The contracts that are in JSON or XML format can be easily modified.
3. Large data inefficiency: Large datasets can slow down the pickling and unpickling. Serialization might be more appropriate for such use-cases.


## Joblib Module
Joblib module can be used to dump and load different results, datasets, models, etc like the Pickle module from anywhere on the device, but we can also simply pass the path alongside the file name to load it or dump it.

```
import joblib

data_dictionary = {'books': 12, 'articles': 100, 'subjects': ['math', 'programming', 'data science']}
joblib.dump(value=data_dictionary, filename='readings.job', compress=True)

data = joblib.load(filename='readings.job')
data
```