# React 2

## Conditional Rendering

Element Variables: can create elements like loggin and logout options

Inline If with Logical && Operator: wrap in curly braces

Inline If-Else with Conditional Operator: conditions to render elements

Preventing Component from Rendering: happens when the value of prop is false

## Lists and Keys

Rendering Multiple Components: using list elements and can be used with the map function

Basic List Component: contain keys and values

Keys: help keep the identity of the element stable with an ID

Extracting Components with Keys: the elements in the map function always need to have keys associated with them

Keys Must Only Be Unique Among Siblings: Only for elements being mapped in the same array do there need to be distinct keys

Embedding map() in JSX: embed any expression in curly braces like map()

## Forms

Controlled Components: puts all the elements in HTML for forms into one setState() function 

The textarea Tag: defines the values of the state so that the text area starts off with text in it

The select Tag: creates a drop-down list, and appends a selected attribute when changed

The file input Tag: you can put in a file in this element as a read-only submission

Handling Multiple Inputs: you can name the different input attributes to deal with different 

Controlled Input Null Value: undefined values are set as null when the value is not specified

Alternatives to Controlled Components: there are uncontrolled components to not have to pipeline every kind of controlled component

Fully-fledged solutions: Formik is a popular choice to do everything needed for full forms in JSX

