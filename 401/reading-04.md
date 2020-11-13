# Python Testing with pytest: Fixtures and Coverage
## Fixtures
You'll want to have some objects available to all of your tests.
Those objects might contain data you want to share across tests, or they might involve the network or filesystem. 
These are often known as "fixtures" 
you define fixtures using a combination of the pytest.fixture decorator
you don't invoke it with parentheses, but it's actually a function under the hood
the fixture, in contrast with regular-old data, can make calculations and decisions
if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time
You can do this by passing the scope parameter to the @pytest.fixture decorator:
## Coverage
Can you be sure you've actually tested all of the possible paths through those functions?
There are ways in which the function could give a totally different result (for example, raise an exception) that the test didn't check.

Now, 100% code coverage doesn't mean that your code is perfect or that it lacks bugs. But it does give you a greater degree of confidence in the code and the fact that it has been run at least once.

# Thinking Recursively in Python
## Dear Pythonic Santa Claus…
This is the typical structure of a recursive algorithm. If the current problem represents a simple case, solve it. If not, divide it into subproblems and apply the same strategy to them.
## Recursive Functions in Python
This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result.
All recursive functions share a common structure made up of two parts: base case and recursive case.
Decompose the original problem into simpler instances of the same problem.
those subproblems must eventually become so simple that they can be solved without further subdivision. 
Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. 
## Maintaining State
keep in mind that each recursive call has its own execution context
Thread the state through each recursive call so that the current state is part of the current call’s execution context
Keep the state in global scope
## Recursive Data Structures in Python
Starting with an empty list, We apply a function to an argument, then pass that result on as an argument to a second application of the same function, and so on
List is not the only recursive data structure. Other examples include set, tree, dictionary, etc.
Recursive data structures and recursive functions go together like bread and butter. 
## Naive Recursion is Naive
Let’s write a recursive function to compute the nth Fibonacci number:
Naively following the recursive deﬁnition of the nth Fibonacci number was rather inefficient.
lru_cache is a decorator that caches the results. Thus, we avoid recomputation by explicitly checking for the value before trying to compute it.
the function must be hashable

# Classes and Objects
Objects are an encapsulation of variables and functions into a single entity.
Objects get their variables and functions from classes.
Classes are essentially a template to create your objects.
## Accessing Object Variables
    class MyClass:
        variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.variable
You can create multiple different objects that are of the same class
## Accessing Object Functions
    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.function()
