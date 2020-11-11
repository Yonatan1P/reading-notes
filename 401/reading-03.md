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
