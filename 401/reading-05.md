# Linked Lists
https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html
## What is a Linked List
 a sequence of Nodes that are connected/linked to each other
 each Node references the next Node in the link
 
 two types of Linked List - Singly and Doubly:
 
  A Singly linked list means that there is only one reference to the Next node
  
 A Doubly linked list means that there is a reference to both the Next and Previous node.
## Terminology
  Nodes are the individual items/links that live in a linked list
  
  Each node contains a property called Next, a reference to the next node in the list
  
  The Head is a reference type of type Node to the first node in a linked list.
  
  The Current reference is a reference type of type Node that is currently being looked at.
  
## What does it look like?
### Traversal
  traversal is through the use of a while() loop
  
  first setting Current to the Head
  
  continually check that the Next node in the list is not null.
  
  The Current will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.
### Big O
The Big O of time for Includes would be O(n)

The Big O of space for Includes would be O(1)

## Adding a Node
### Adding O(1)
Set Current equal to Head

set newNode.Next property to the same location that the Head node is pointing towards

re-assign Head to point at newNode

Pseudo code for an Add method on a Linked list 

    `Current <-- Head
    
			newNode.Next <-- Head
      
			Head <-- newNode
      
			Current <-- Head`
      
### Big O
always be a O(1) time and space

it takes the same amount of time to add a new node to the beginning of the list

### Adding a Node O(n)

example: Linked List of 5 nodes
WE want to set the value of node6 to be 16

We can do an AddBefore method or an AddAfter

Before moving Current to the next node, we want check if the value of the next node is equal to the value we are supposed to be watching for

Add Node6 Before Node4

node3.Next property is equal to node4
we can now set our node6.Next property also to node4
ow both node3 and node6 are pointing to the same next node.
node3.Next to point to the newly created node
tell Current (because it is pointing to the same memory location as node3) to change it’s Next to point to the new node

Psuedo Code for AddBefore 
`Current <-- Head

			while Current.Next is not equal to NULL
      
				if Current.Next.Value is equal to existingNode.Value
        
					newNode.Next <-- existingNode
          
					Current.Next <-- newNode

				Current <-- Current.Next;	`
### Big O
 time efficiency of this transaction would be O(n)
 
 Space efficiency would stay at an O(1)
 
 ## Print Out Nodes
 leveraging our Current node and a while loop to traverse through the existing linked list
 
 pseudo code:
 
 `Current <-- Head

			while Current.Next is not equal to NULL
      
				OUTPUT <-- "Current.Value --> "
        
				Current <-- Current.Next

			OUTPUT <-- "Current.Value --> NULL"`

while loop to check and make sure we are not at the end of a linked list

# What’s a Linked List, Anyway?
https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d

https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996
## Linear data structures
One characteristic of linked lists is that they are linear data structures: order matters!

In non-linear data structures, items don’t have to be arranged in order

## Memory management
When an array is created, it needs a certain amount of memory.
But, we’d need all of that memory in one contiguous block.

On the other hand, when a linked list is born, it doesn’t need 7 bytes of memory all in one place.
instead, the memory that they use can be scattered throughout.

The fundamental difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures.

If more elements needed to be added to a static data structure and it didn’t have enough memory, you’d need to copy the data of that array, for example, and recreate it with more memory, so that you could add elements to it.

On the other hand, a dynamic data structure can shrink and grow in memory. It doesn’t need a set amount of memory to be allocated in order to exist

## Parts of a linked list
A linked list is made up of a series of nodes

starting point of the list is a reference to the first node, which is referred to as the head
 
The end of the list isn’t a node, but rather a node that points to null, or an empty value.

A single node has just two parts: data, or the information that the node contains, and a reference to the next node.

A single node doesn’t know how long the linked list is, and it may not necessarily even know where it starts, or where it ends.

## Lists for all shapes and sizes
Singly linked lists are the simplest type of linked list, based solely on the fact that they only go in one direction.

doubly linked list, because there are two references contained within each node: a reference to the next node, as well as the previous node

A circular linked list is a little odd in that it doesn’t end with a node pointing to a null value. Instead, it has a node that acts as the tail of the list (rather than the conventional head node), and the node after the tail node is the beginning of the list.

makes it really easy to add something to the end of the list, because you can begin traversing it at the tail node

## Hey, so, what even is Big O?
Big O Notation is a way of evaluating the performance of an algorithm.

There are two major points to consider when thinking about how an algorithm performs: how much time it requires at runtime given how much time and memory it needs.

we use big O notation to express how quickly its runtime grows.

O(1) function takes constant time

O(n) function is linear

O(n²) function, which clearly takes exponentially more time and memory the more elements that you have

## Growing a linked list
unlike arrays, we don’t need to allocate memory in advance or copy and re-create our linked list

all we really need to do is rearrange our pointers

First, we find the head node of the linked list.

Next, we’ll make our new node, and set its pointer to the current first node of the list.

Lastly, we rearrange our head node’s pointer to point at our new node.

Big O for adding to the head: O(1)

inserting an element at the end of a linked list is a different story

Find the node we want to change the pointer of (in this case, the last node)

Create the new node we want to insert and set its pointer (in this case, to null)

Direct the preceding node’s pointer to our new node

Big O for adding to the end: a linear O(n)

## To list or not to list?
a linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element.
