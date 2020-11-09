# BIG O Notation

Big O notation is used in Computer Science to describe the performance or complexity of an algorithm.

## Common Notations

O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.
A process that doesn't involve a calculation being performed on any piece of data in the data set.

O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set.
A function that does an operation on each piece of data in the data set.

O(N^2) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. 
A function that does on operation using 2 data points for every data position.

O(2^N) denotes an algorithm whose growth doubles with each additon to the input data set.
This is a function where each additional data point means each calculation for the function must be done 1 more time.
A good example is a fibonacci sequence.

O(log N) is slightly trickier to explain.Doubling the size of the input data set has little effect on its growth as after a 
single iteration of the algorithm the data set will be halved and therefore on a par with an input data set half the size.
This makes algorithms like binary search extremely efficient when dealing with large data sets.
