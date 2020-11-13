# Reading and Writing Files in Python
by James Mertz 
https://realpython.com/read-write-files-python/

## What Is a File?
3 Parts :

  Header: metadata about the contents of the file (file name, size, type, and so on)
  
  Data: contents of the file as written by the creator or editor
  
  End of file (EOF): special character that indicates the end of the file
### File Paths
3 Parts: 

  Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
  
  File Name: the actual name of the file
  
  Extension: the end of the file path pre-pended with a period (.) used to indicate the file type
  
The double-dot (..) can be chained together to traverse multiple directories above the current directory (ex: ../../animals.csv.)
### Line Endings
representation of a new line or line ending.

characters (CR+LF or \r\n)

put this escape r or escape n at the end of the line to start a new line of code

### Character Encodings
An encoding is a translation from byte data to human readable characters. 

The two most common encodings are the ASCII and UNICODE Formats.

ASCII can only store 128 characters, while Unicode can contain up to 1,114,112 characters.
## Opening and Closing a File in Python
 open() built-in function
 
  open() has a single required argument that is the path to the file. open() has a single return, the file object
  
  file = open('dog_breeds.txt')
  
Warning: You should always make sure that an open file is properly closed.

  The first way to close a file is to use the try-finally block:
  
    reader = open('dog_breeds.txt')
    
      try:
      
          # Further file processing goes here
          
      finally:
      
          reader.close()
          
  The second way to close a file is to use the with statement:
  
    `with open('dog_breeds.txt') as reader:
    
    # Further file processing goes here`
Options when openning a file:
'r'	Open for reading (default)
'w'	Open for writing, truncating (overwriting) the file first

There are three different categories of file objects:
Text files
Buffered binary files
Raw binary files
'rb' or 'wb'	Open in binary mode (read/write using byte data)
## Iterating Over Each Line in the File
use the Python .readline() method to iterate over each line
Another way you could iterate over each line in the file is to use the Python .readlines() method of the file object.
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     for line in reader:
>>>         print(line, end='')
.write(string)	This writes the string to the file.
.writelines(seq)	This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).
## Working With Bytes
work with files using byte strings by adding the 'b' character to the mode argument
## Appending to a File
This is easily done by using the 'a' character for the mode argument
with open('dog_breeds.txt', 'a') as a_writer:
    a_writer.write('\nBeagle')
## Working With Two Files at the Same Time
d_path = 'dog_breeds.txt'
d_r_path = 'dog_breeds_reversed.txt'
with open(d_path, 'r') as reader, open(d_r_path, 'w') as writer:
    dog_breeds = reader.readlines()
    writer.writelines(reversed(dog_breeds))
## Creating Your Own Context Manager
