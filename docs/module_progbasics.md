# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!

Python offers a range of compound data types often referred to as sequences. List is one of the most frequently used and very versatile data types used in Python.

METHODS: 
List index, negative indexing,
slicing - range of elements separated by a colon (:),
adding elements - one element: append(), several elements: to the end of the list: extend(), 

to insert multiple elements into the list: insert(),
delete or remove elements - del() - even can delete one or more elements (referring to them by their index), 

remove() - , clear() - empties the whole list, pop() - removes the last item if the index is not provided
List methods:
List comprehension - a method to create a new list:
e.g pow2 = [2**x for x in range(10)]

#### What is the difference between a list/array and a set?

List: a collection which is ordered and changeable. Allows duplicate members.
Array: a variable, which can hold more than one value at a time
Set: sequence of unique items (they cannot have duplicates), ordering of the elements is arbitrary 

#### What is the purpose and methods of a dictionary/map data structure?

DICTIONARY: in a ~ an item has a key and a corresponding value that is expressed as a pair(key: value) in curly brackets({}). 

While the values can be of any data type and can repeat, keys must be of immutable types (string, number or tuple with immutable elements) and must be unique.

Method to query information in the dictionary:

Method to create new dictionary:

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.

def recur_fibo(n):

​    if n <= 1:

​        return n

​    else:

​        return(recur_fibo(n-1) + recur_fibo(n-2))

#### How do you find a max value in a list/array if you can’t use any built-in functions?
#### How do you find the average of values in a list/array if you can’t use any built-in functions?
#### What do we call an *in-place* sort?
#### Explain an algorithm which sorts a list!

### Programming paradigms - procedural

#### What is the call stack?
#### What is “Stack overflow”?
#### What are the main parts of a function?

### Programming languages - Python  
#### How do you use a dictionary in Python?
#### What does it mean that an object is immutable in Python?
#### What is conditional expression in Python?
#### What are different types of arguments in Python?
#### What is variable shadowing? (context: variable scope)
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
#### What type of elements can a list contain in Python?
#### What is slice operator in Python and how to use?
#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
#### What is the purpose of the in and not in membership operators in Python?
#### What does the + operator mean when used with strings in Python?
#### Explain f strings in Python?
#### Name 4 iterable types in Python!
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
#### Does the order of the function definitions matter in Python? Why?
#### What does unpacking mean in Python?
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
#### What does step over, step into and step out mean while using the debugger?
#### How can you start to debug a program from a certain line using the debugger?

### Version control

#### What are the advantages of using a version control system?
#### What is the difference between the working directory, the staging area and the repository in git?
#### What are remote repositories in git?
#### Why does a merge conflict occur?
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
#### What does it mean atomic commits and descriptive commit messages?
#### What’s the difference between git and GitHub?

## Software design

### Clean code

#### What does clean code mean?
#### What steps do we usually do during a clean code refactoring?

### Error handling

#### What is exception handling?
#### What are the basics of exception handling in Python?
#### In which case should we catch an exception? Why?
#### What can/should we do with an exception in the ‘except’ block?
#### What does the else and finally statement do in a try-except block in Python?

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

## Programming environment

### Unix

#### What is UNIX and what is Linux?
#### What do we call the shell in Linux?
#### What does root means in a Linux environment?
#### How do you access your personal files in Linux?
#### How can you install an application in Linux?
#### What is package management in Linux, what are repositories?
#### How do you navigate in the filesystem with the command line?
#### What does the following commands do: mkdir, rm, cat, cp, touch?
#### How can you look up what does a command do in Linux if you have no internet connection?
#### What does the following commands do: head, tail, more, less?
#### How do you download a file from internet using the terminal?
