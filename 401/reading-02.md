# Testing and Modules

The greatest advantage about TDD is to craft the software design first
Your code will be more reliable: after a change you can run your tests and be in peace
Beginning may be hard — and that’s fine. You just need to practice!

## Unit tests and TDD?

Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code.
But Test-Driven Development is a strategy to think (and write!) tests first.

## The freela
Let’s write our first test!
`def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’`
    
The first one is the test name. 
We need to be descriptive about it and to say what is expected and what we are testing.
The test file name should follow the same name of module name. 

AAA: Arrange, Act and Assert.
Arrange: you need to organize the data needed to execute that piece of code (input);
Act: here you will execute the code being tested (exercise the behaviour);
Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

## The Cycle

🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
✅ Write the feature and make the test pass! (you can dance after that)
🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

## TDD is not about the money/tests

More than any checking, we need to think about our software design first.

# Recurssion

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function.
This makes it easier to solve certain problems that need to call the same function many times.

## A Mathematical Interpretation

Rather than calling a functio each time you want to add a bunch of numbers, the function calls itself as many times as needed.

## What is base condition in recursion? 

he solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems.

## How a particular problem is solved using recursion? 

The idea is to represent a problem in terms of one or more smaller problems

## Why Stack Overflow error occurs in recursion? 
If the base case is not reached or not defined, then the stack overflow problem may arise.

## What is the difference between direct and indirect recursion? 

A function fun is called direct recursive if it calls the same function fun.

A function fun is called indirect recursive if it calls another function say fun_new and fun_new calls fun directly or indirectly.

## What is difference between tailed and non-tailed recursion? 

A recursive function is tail recursive when recursive call is the last thing executed by the function

## How memory is allocated to different function calls in recursion? 
he memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call

When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.

## What are the disadvantages of recursive programming over iterative programming? 

A function fun is called indirect recursive if it calls another function say fun_new and fun_new calls fun directly or indirectly. 
