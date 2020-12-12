# Readings: FileIO & Exceptions

Source: [Reading and Writing Files in Python (Guide)](https://realpython.com/read-write-files-python/)

## What Is a File?

**At its core, a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.**

Files on most modern file systems are composed of three main parts:

- **Header**: metadata about the contents of the file (file name, size, type, and so on)
- **Data**: contents of the file as written by the creator or editor
- **End of file (EOF)**: special character that indicates the end of the file

![File System Example](https://files.realpython.com/media/FileFormat.02335d06829d.png)

## File Paths

The file path is a string that represents the location of a file. It’s broken up into three major parts:

- **Folder Path**: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
- **File Name**: the actual name of the file
- **Extension**: the end of the file path pre-pended with a period (.) used to indicate the file type

```
/
│
├── path/
|   │
│   ├── to/
│   │   └── cats.gif
│   │
│   └── dog_breeds.txt
|
└── animals.csv
```

## Line Endings

ASA standard states that line endings should use the sequence of the Carriage Return (CR or \r) and the Line Feed (LF or \n) characters (CR+LF or \r\n). The ISO standard however allowed for either the CR+LF characters or just the LF character.

## Character Encodings

Another common problem that you may face is the encoding of the byte data. An encoding is a translation from byte data to human readable characters. This is typically done by assigning a numerical value to represent a character. The two most common encodings are the ASCII and UNICODE Formats. ASCII can only store 128 characters, while Unicode can contain up to 1,114,112 characters.

ASCII is actually a subset of Unicode (UTF-8), meaning that ASCII and Unicode share the same numerical to character values. It’s important to note that parsing a file with the incorrect character encoding can lead to failures or misrepresentation of the character. For example, if a file was created using the UTF-8 encoding, and you try to parse it using the ASCII encoding, if there is a character that is outside of those 128 values, then an error will be thrown.

## Opening and Closing a File in Python

When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object.

It’s important to remember that it’s your responsibility to close the file. In most cases, upon termination of an application or script, a file will be closed eventually. However, there is no guarantee when exactly that will happen. This can lead to unwanted behavior including resource leaks. It’s also a best practice within Python (Pythonic) to make sure that your code behaves in a way that is well defined and reduces any unwanted behavior.

```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

> Notice the `open` command at the top and the `close` command at the bottom.

Other options for modes are fully documented online, but the most commonly used ones are the following:

| Character | Meaning |
| --- | --- |
| 'r' | Open for reading (default) | 
| 'w' | Open for writing, truncating (overwriting) the file first | 
| 'rb' or 'wb' | Open in binary mode (read/write using byte data) | 

## Reading and Writing Opened Files

Once you’ve opened up a file, you’ll want to read or write to the file. First off, let’s cover reading a file. There are multiple methods that can be called on a file object to help you out:

| Method | What It Does |
| --- | --- |
| .read(size=-1) | This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read. |
| .readline(size=-1) | This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read. |
| .readlines() | This reads the remaining lines from the file object and returns them as a list. |

## Iterating Over Each Line in the File

| Method	| What It Does | 
| --- | --- |
| .write(string) | This writes the string to the file.
| .writelines(seq) | This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).| 


## Working With Bytes

You can actually open that file in Python and examine the contents! Since the .png file format is well defined, the header of the file is 8 bytes broken up like this:

| Value	| Interpretation |
| --- | --- |
| 0x89 | A “magic” number to indicate that this is the start of a PNG |
| 0x50 0x4E 0x47 | PNG in ASCII |
| 0x0D 0x0A | A DOS style line ending \r\n |
| 0x1A | A DOS style EOF character |
| 0x0A | A Unix style line ending \n |

## Appending to a File

Sometimes, you may want to append to a file or start writing at the end of an already populated file. This is easily done by using the `'a'` character for the mode argument:

```
with open('dog_breeds.txt', 'a') as a_writer:
    a_writer.write('\nBeagle')
```

## Don’t Re-Invent the Snake

There are common situations that you may encounter while working with files. Most of these cases can be handled using other modules. Two common file types you may need to work with are .csv and .json. Real Python has already put together some great articles on how to handle these:

[Reading and Writing CSV Files in Python](https://realpython.com/python-csv/)

[Working With JSON Data in Python](https://realpython.com/python-json/)

Additionally, there are built-in libraries out there that you can use to help you:

- **wave**: read and write WAV files (audio)
- **aifc**: read and write AIFF and AIFC files (audio)
- **sunau**: read and write Sun AU files
- **tarfile**: read and write tar archive files
- **zipfile**: work with ZIP archives
- **configparser**: easily create and parse configuration files
- **xml.etree.ElementTree**: create or read XML based files
- **msilib**: read and write Microsoft Installer files
- **plistlib**: generate and parse Mac OS X .plist files

There are plenty more out there. Additionally there are even more third party tools available on PyPI. Some popular ones are the following:

- **PyPDF2**: PDF toolkit
- **xlwings**: read and write Excel files
- **Pillow**: image reading and manipulation

--- 
---

## Python Exceptions: An Introduction

Source: [Python Exceptions: An Introduction](https://realpython.com/python-exceptions/)

## Exceptions versus Syntax Errors

Syntax errors occur when the parser detects an incorrect statement. 

```
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

> The arrow indicates where the parser ran into the syntax error. 


## Raising an Exception

We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

![Exception Example](https://files.realpython.com/media/raise.3931e8819e08.png)

If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:

```
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

> The program comes to a halt and displays our exception to screen, offering clues about what went wrong.

## The AssertionError Exception

Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.

![Assertion Example](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

## The try and except Block: Handling Exceptions

The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.

![Try/Except Example](https://files.realpython.com/media/try_except.c94eabed2c59.png)

> The assert in this function will throw an AssertionError exception if you call it on an operating system other then Linux.

### Here are the key takeaways:

- A try clause is executed up until the point where the first exception is encountered.
- Inside the except clause, or the exception handler, you determine how the program responds to the exception.
- You can anticipate multiple exceptions and differentiate how the program should respond to them.
- [Avoid using bare except clauses.](https://realpython.com/the-most-diabolical-python-antipattern/)

## The else Clause

In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

![Else Clause Example](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)

## Cleaning Up After Using finally

Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.

![Finally Example](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)

## Summing Up

After seeing the difference between syntax errors and exceptions, you learned about various ways to raise, catch, and handle exceptions in Python. In this article, you saw the following options:

- raise allows you to throw an exception at any time.
- assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
- In the try clause, all statements are executed until an exception is encountered.
- except is used to catch and handle the exception(s) that are encountered in the try clause.
- else lets you code sections that should run only when no exceptions are encountered in the try clause.
- finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.


