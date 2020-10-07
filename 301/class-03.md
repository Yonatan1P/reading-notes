# Reading-03: Mustache and Flexbox
## Mustache
  Mustache is NOT a templating engine.
    Mustache is a specification for a templating language
  definition: is a logic-less template syntax.
  purpose: It can be used for HTML, config files, source code — anything
  method: expanding tags in a template using values provided in a hash or object

  ### Using Mustache
    mustache.js is an implementation of mustache templating in JavaScript
    Mustache syntax for placeholder: two braces around {{ name }}
      this is what is going to be replaced when mustache compiles the objects that will go in
    we would write templates according to the Mustache specification
      it can then be compiled by a templating engine
      
  ### Mustache Express
    mustache with Node and Express
    To install With NPM: run command '$ npm install mustache --save'
    This gives you an easy way to use Mustache and Express together

## FlexBox
   ### Background
      CSS flexbox layout
      parent element (the flex container)
      child elements (the flex items)
      purpose: providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is         unknown and/or dynamic
      flex layout is to give the container the ability to alter its items’ width/height (and order) to best fill the available space
      flexbox layout is direction-agnostic
        it doesnt matter which direction is changing, flexbox will resize the items to fit the container
      flexbox is a whole module and not a single property
   ### Basics and Terminology
      flex layout is based on “flex-flow directions”.
         main axis (from main-start to main-end)
          'main-start|main-end' will spread flex items along the main axis of the flex container
          'main-size' is the command for resizing the main flex dimension of the item
         cross axis (from cross-start to cross-end)
          'cross-start | cross-end' spreads the flex items across the cross axis, the non-main
          'cross-size' changes the size of the cross axis dimension
   ### Properties of Parents: Flex Containers
    Display: '.container {display: flex; /* or inline-flex */}'
    this will allow for a flex content on all the children of the container element
    Flex Direction: '.container {flex-direction: row | row-reverse | column | column-reverse;}'
    this flexes the direction of the child elements
      you can say row: ltr to change the order of the elements from left to right
      you can say row: rtl to change the order from right to left
      row-reverse gives you the opposite commands as for row
    Flex-wrap: '.container {flex-wrap: nowrap | wrap | wrap-reverse;}'
      allows items to wrap as needed instead of all being in one line
    Flex-flow: '.container {flex-flow: column wrap;}'
      shorthand for combining flex-direction and flex-wrap
    Justify-content: '.container {justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start     | end | left | right ... + safe | unsafe;}'
      flex-start, flex-end, center, space-between, space-around,space-evenly
    Align-items: '.container {align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start     | end | self-start | self-end + ... safe | unsafe;}'
    Align-content: '.container {align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;}'
   ### Properties of Children: Flex items
        order: '.item {
                order: 5; /* default is 0 */
               }'
       flex-grow
        
      
    
