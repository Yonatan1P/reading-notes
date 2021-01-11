# Generators
code that produces examples or more stuff

Generator functions are syntactic sugar for writing objects that support the iterator protocol. Generators abstract away much of the boilerplate code needed when writing class-based iterators.

The yield statement allows you to temporarily suspend execution of a generator function and to pass back values from it.

Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statemen

```class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value]
```
        
that is an example of an infinite generator

# Python Iterators: A Step-By-Step Introduction

You can iterate through a set or a list, but you can also iterate over integers and infinitely

for-in loops:

It first prepared the repeater object for iteration by calling its __iter__ method. This returned the actual iterator object.
After that, the loop repeatedly calls the iterator object’s __next__ method to retrieve values from it.

