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

I can keep the older versions if there is a step I want to ignore, or go back.
I can see all the versions I have created of the program, and keep track of them.
Others can reach my creations and I can reach other peoples creations as well.

#### What is the difference between the working directory, the staging area and the repository in git?

3 sections in a git project:
working directory: ~ is a single checkout of one version of the project. These files are pulled out of the database and placed on a disk for you to use or modify.

staging area: ~ is a file, in your git directory, that shows data about what will go into your next commit, other name for it is "index".
repository: ~ is where git stores the metadata and object database for your project. This is what is copied, when you clone a repository from another computer.

#### What are remote repositories in git?

A remote in Git is a common repository that all team members use to exchange their changes. In most cases, such a remote repository is stored on a code hosting service like GitHub or on an internal server. 
In contrast to a local repository, a remote typically does not provide a file tree of the project's current state.

#### Why does a merge conflict occur?

Because it happens if there are 2 or more different updates on the same file at the same time (from different users). Therefore they will not match and conflict each other.

We will have to resolve this merge conflict by adding a new commit before we can merge the branches again.

(Navigate to the local git repository, generate a list of the files affected by the merge conflict, open the file with a text editor (vim), delete the conflict markers (<<<<<<<, =======, >>>>>>>>) and make changes in the final merge. Add or stage the changes, commit them.

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?

Through pulling and pushing.

This command will pull the file to my local repository 

git pull --> https:// www.code.com/myfile

git add <myfile>

git commit -m "message"

git push (or git pull origin master and then git push origin master)

These command will push back my updated document to the remote repository

#### What does it mean atomic commits and descriptive commit messages?

Atomic commits: as short as possible (e.g. name of a finalized function in a code)
Descriptive commit messages: has a title and a body (separated by an empty line), it is good to use concise commits, with punctuation, right grammar

#### What’s the difference between git and GitHub?

GIT: version control system. ~ helps us manage our project files.
GITHUB: ~ is a web-based service for version control using git.

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
