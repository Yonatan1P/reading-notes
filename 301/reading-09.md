# Refactoring
“Complexity is anything that makes software hard to understand or to modify." — John Outerhout

What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs 
— that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia

## Pure functions: 
It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects
If our function reads external files, it’s not a pure function — the file’s contents can change.

Random number generation: Any function that relies on a random number generator cannot be pure.

It does not cause any observable side effects: Examples of observable side effects include modifying a global object or a parameter passed by reference.

Observation: mutability is discouraged in functional programming

Pure functions benefits: The code’s definitely easier to test.

## Immutability
Unchanging over time or unable to be changed.
When data is immutable, its state cannot change after it’s created.
Instead, you create a new object with the new value.
With recursion, we keep our variables immutable.

## Referential transparency
pure functions + immutable data = referential transparency

## Functions as first-class entities
Functions as first-class entities can:
-refer to it from constants and variables
-pass it as a parameter to other functions
-return it as result from other functions

## Higher-order functions
takes one or more functions as arguments, or
returns a function as its result

## Filter
Imperative approach
-create an empty array evenNumbers
-iterate over the numbers array
-push the even numbers to the evenNumbers array
Filter Array problem: The problem idea is to filter a given array of integers and output only those values that are less than a specified value X.

## Declarative approach
A declarative Javascript solution would be something like this:
```
function smaller(number) {
  return number < this;
}

function filterArray(x, listOfNumbers) {
  return listOfNumbers.filter(smaller, x);
}

let numbers = [10, 9, 8, 2, 7, 5, 1, 3, 0];

filterArray(3, numbers); // [2, 1, 0]
```

## Map
The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

In a imperative Javascript way, it would be:
```
var people = [
  { name: "TK", age: 26 },
  { name: "Kaio", age: 10 },
  { name: "Kazumi", age: 30 }
];

var peopleSentences = [];

for (var i = 0; i < people.length; i++) {
  var sentence = people[i].name + " is " + people[i].age + " years old";
  peopleSentences.push(sentence);
}

console.log(peopleSentences); // ['TK is 26 years old', 'Kaio is 10 years old', 'Kazumi is 30 years old']
```
In a declarative Javascript way, it would be:
```
const makeSentence = (person) => `${person.name} is ${person.age} years old`;

const peopleSentences = (people) => people.map(makeSentence);
  
peopleSentences(people);
// ['TK is 26 years old', 'Kaio is 10 years old', 'Kazumi is 30 years old']
```
The whole idea is to transform a given array into a new array.

## Reduce
The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
In imperative way, we would iterate the order list and sum each product amount to the total amount.
```
var orders = [
  { productTitle: "Product 1", amount: 10 },
  { productTitle: "Product 2", amount: 30 },
  { productTitle: "Product 3", amount: 20 },
  { productTitle: "Product 4", amount: 60 }
];

var totalAmount = 0;

for (var i = 0; i < orders.length; i++) {
  totalAmount += orders[i].amount;
}

console.log(totalAmount); // 120
```
Using reduce, we can build a function to handle the amount sum and pass it as an argument to the reduce function.
```
let shoppingCart = [
  { productTitle: "Product 1", amount: 10 },
  { productTitle: "Product 2", amount: 30 },
  { productTitle: "Product 3", amount: 20 },
  { productTitle: "Product 4", amount: 60 }
];

const sumAmount = (currentTotalAmount, order) => currentTotalAmount + order.amount;

const getTotalAmount = (shoppingCart) => shoppingCart.reduce(sumAmount, 0);

getTotalAmount(shoppingCart); // 120
```
Another way to get the total amount is to compose map and reduce.
```
const getAmount = (order) => order.amount;
const sumAmount = (acc, amount) => acc + amount;

function getTotalAmount(shoppingCart) {
  return shoppingCart
    .map(getAmount)
    .reduce(sumAmount, 0);
}

getTotalAmount(shoppingCart); // 120
```
We want the total amount of all books in our shopping cart. Simple as that. The algorithm?
filter by book type
transform the shopping cart into a collection of amount using map
combine all items by adding them up with reduce
```
let shoppingCart = [
  { productTitle: "Functional Programming", type: "books", amount: 10 },
  { productTitle: "Kindle", type: "eletronics", amount: 30 },
  { productTitle: "Shoes", type: "fashion", amount: 20 },
  { productTitle: "Clean Code", type: "books", amount: 60 }
]

const byBooks = (order) => order.type == "books";
const getAmount = (order) => order.amount;
const sumAmount = (acc, amount) => acc + amount;

function getTotalAmount(shoppingCart) {
  return shoppingCart
    .filter(byBooks)
    .map(getAmount)
    .reduce(sumAmount, 0);
}

getTotalAmount(shoppingCart); // 70
```

# Refactoring JavaScript for Performance and Readability

## Scenario 1
We're an URL-shortening website, like TinyURL. We accept a long URL and return a short URL that forwards visitors to the long URL.
```
// Unrefactored code

const URLstore = [];

function makeShort(URL) {
  const rndName = Math.random().toString(36).substring(2);
  URLstore.push({[rndName]: URL});
  return rndName;
}

function getLong(shortURL) {
  for (let i = 0; i < URLstore.length; i++) {
    if (URLstore[i].hasOwnProperty(shortURL) !== false) {
      return URLstore[i][shortURL];
    }
  }
}
```
Problem: what happens if getLong is called with a short URL that isn't in the store? Nothing is explicitly returned so undefined will be returned.
The refactor here is to change the data-structure of URLstore.
The answer is to use some form of hash function, which Maps and Sets use under the surface. 
```
// Refactored code

const URLstore = new Map(); // Change this to a Map

function makeShort(URL) {
  const rndName = Math.random().toString(36).substring(2);
  // Place the short URL into the Map as the key with the long URL as the value
  URLstore.set(rndName, URL);
  return rndName;
}

function getLong(shortURL) {
  // Leave the function early to avoid an unnecessary else statement
  if (URLstore.has(shortURL) === false) {
    throw 'Not in URLstore!';
  }
  return URLstore.get(shortURL); // Get the long URL out of the Map
}
```
It's easy to tack on addendums about scaling and redundancy.

## Scenario 2
We're a social media website where user URLs are generated randomly. Instead of random gibberish,
we're going to use the friendly-words package that the Glitch team works on. 
They use this to generate the random names for your recently created projects!
```
// Unrefactored code

const friendlyWords = require('friendly-words');

function randomPredicate() {
  const choice = Math.floor(Math.random() * friendlyWords.predicates.length);
  return friendlyWords.predicates[choice];
}

function randomObject() {
  const choice = Math.floor(Math.random() * friendlyWords.objects.length);
  return friendlyWords.objects[choice];
}

async function createUser(email) {
  const user = { email: email };
  user.url = randomPredicate() + randomObject() + randomObject();
  await db.insert(user, 'Users')
  sendWelcomeEmail(user);
}
```
You may have also noticed that there is some duplicated logic in our random functions.
Let's write one function that accepts a list of friendly things.
```
// Refactored code

const friendlyWords = require('friendly-words');

const generateURL = user => {
  const pick = arr => arr[Math.floor(Math.random() * arr.length)];
  user.url = `${pick(friendlyWords.predicates)}-${pick(friendlyWords.objects)}` +
    `-${pick(friendlyWords.objects)}`; // This line would've been too long for linters!
};

async function createUser(email) {
  const user = { email: email };
  // The URL-creation algorithm isn't important to this function so let's abstract it away
  generateURL(user);
  await db.insert(user, 'Users')
  sendWelcomeEmail(user);
}
```
## Strategies
There are no absolutes when it comes to clean code — there's always an edge case!
```
function showProfile(user) {
  if (user.authenticated === true) {
    // ..
  }
}

// Refactor into ->

function showProfile(user) {
  // People often inline such checks
  if (user.authenticated === false) { return; }
  // Stay at the function indentation level, plus less brackets
}
```
Cache variables so functions can be read like sentences:
```
function searchGroups(name) {
  for (let i = 0; i < continents.length; i++) {
    for (let j = 0; j < continents[i].length; j++) {
      for (let k = 0; k < continents[i][j].tags.length; k++) {
        if (continents[i][j].tags[k] === name) {
          return continents[i][j].id;
        }
      }
    }
  }
}

// Refactor into ->

function searchGroups(name) {
  for (let i = 0; i < continents.length; i++) {
    const group = continents[i]; // This code becomes self-documenting
    for (let j = 0; j < group.length; j++) {
      const tags = group[j].tags;
      for (let k = 0; k < tags.length; k++) {
        if (tags[k] === name) {
          return group[j].id; // The core of this nasty loop is clearer to read
        }
      }
    }
  }
}
```
Check for Web APIs before implementing your own functionality:
```
function cacheBust(url) {
  return url.includes('?') === true ?
    `${url}&time=${Date.now()}` :
    `${url}?time=${Date.now()}`
}

// Refactor into ->

function cacheBust(url) {
  // This throws an error on invalid URL which stops undefined behaviour
  const urlObj = new URL(url);
  urlObj.searchParams.append('time', Date.now); // Easier to skim read
  return url.toString();
}
```
