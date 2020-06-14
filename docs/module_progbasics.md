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

List: a collection which is ordered and changeable. Allows duplicate members. Indexing starts with zero. lists are written with square brackets ( []).

Array: An array can hold many values under a single name, and you can access the values by referring to an index number. Python does not have built-in support for Arrays, but they can be used as lists.

Set: sequence of unique items (they cannot have duplicates), ordering of the elements is arbitrary . ~ s are written with curl brackets ({}). 

#### What is the purpose and methods of a dictionary/map data structure?

DICTIONARY: in a ~ an item has a key and a corresponding value that is expressed as a pair(key: value) in curly brackets({}). 

While the values can be of any data type and can repeat, keys must be of immutable types (string, number or tuple with immutable elements) and must be unique.

Method to query information in the dictionary: 

get() - finds a key if it is in the dictionary

e.g.: my_dict['name'] means the same as my_dict.get('name')

keys(), values() - returns the keys or values of a dictionary 

items() - loops through both keys and values

pop(), remove() - removes items from the dictionary

Method to create new dictionary: 

copy() - returns a copy of a dictionary 

clear() - removes all items from a dictionary 

if we want to merge 2 dictionaries, we can use the + sign: dict_a + dict_b = dict_c (where the items of dict_c are the items from dict_a and items from dict_b)

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.

def recur_fibo(n):

​    if n <= 1:

​        return n

​    else:

​        return(recur_fibo(n-1) + recur_fibo(n-2))

#### How do you find a max value in a list/array if you can’t use any built-in functions?

def max(values_list):
    values_list = [1,2,3,4,5,3]
    max_value = None
    for value in values_list:
        if not max_value:
            max_value = value
        elif value > max_value:
            max_value = value
    return max_value

#### How do you find the average of values in a list/array if you can’t use any built-in functions?

list = [15, 9, 55, 41, 35, 20, 62, 49]

def list_average(list):

​    sum = 0

​    count = 0

​    for i in list:

​        sum = sum + i

​        count = count + 1

​    avg = sum / count

​    return avg

print("The average is, " + str(list_average(list)))

#### What do we call an *in-place* sort?

numbers = [1, 2, 56, 32, 51, 2, 8, 92, 15]
i = 0
j = 0
lenght = len(numbers)

for i in range(lenght):
    for j in range(1, lenght - i):
        if numbers[j-1] > numbers[j]:
            (numbers[j-1], numbers[j]) = (numbers[j], numbers[j-1])

#### Explain an algorithm which sorts a list!

### Programming paradigms - procedural

#### What is the call stack?

CALL STACK: in computer science, ~ is a stack data structure that stores information about the active subroutines of a computer program.

#### What is “Stack overflow”?

STACK OVERFLOW: 

1. ~ is a question and answer site for professional and enthusiast programmers.

2. ~ (as a general term) occurs in software, if the call stack pointer exceeds the stack bound.
   This can happen e.g. when there is an excessively deep or infinitive recursion in a program

   e.g.
   def foo():
   	return foo()

#### What are the main parts of a function?

1. In Python, a function is a group of related statements that performs a specific task.

   Functions help break our program into smaller and modular chunks. As our program grows larger and larger, functions make it more organized and manageable.

   Furthermore, it avoids repetition and makes the code reusable.

   Syntax of a function:

   def function_name(parameters):

   ​	statement

   ​	return 

Above shown is a function definition that consists of the following components.

1. Keyword "def" that marks the start of the function header.
2. A function name to uniquely identify the function. 
3. Parameters (arguments) through which we pass values to a function. They are optional.
4. A colon (:) to mark the end of the function header.
5. Optional documentation string (docstring) to describe what the function does.
6. One or more valid python statements that make up the function body. Statements must have the same indentation level (usually 4 spaces).
7. An optional return  statement to return a value from the function.

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

Reading the program, and understanding what it does (filter semantic issues if there is any), running the program (in order to see if there is a typo or a syntactic error), using tools like a debugger (e.g. Thonny).

#### What does step over, step into and step out mean while using the debugger?

If we start the debugger (e.g. the built-in debugger in Visual Studio Code), the debug console panel is displayed and shows the debugging output, and the debug status appears in the status bar:

Through the debug toolbar we can select a line in our code, and step into that to see what the issue is. We can also step over an issue, leaving it as it is and step out of the current line if we are done or corrected the error.

#### How can you start to debug a program from a certain line using the debugger?

I can step into the line (a red dot appears beside the line I am interested in), run the program with the debugger, which will stop if there is an issue, and show the errors on the status bar. 

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

All the variable names, function names are placed correctly in order, they are readable, d.r.y, naming is clear: variable names are using nouns, function names use verbs

#### What steps do we usually do during a clean code refactoring?

Make the code clearer and easier to read. e.g. if there is a magic number, we can give a name to it.

### Error handling

#### What is exception handling?
#### What are the basics of exception handling in Python?
#### In which case should we catch an exception? Why?
#### What can/should we do with an exception in the ‘except’ block?
#### What does the else and finally statement do in a try-except block in Python?

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

A retrospective is a meeting held by a software development team at the end of a project or process to discuss success and failure and future improvements after each iteration.
Sticky notes written after or during the sprint, with:
What went well?
Where to improve?
S.M.A.R.T. action items (specific, measurable, achievable, relevant, time based)
scrum: discuss changes & implement changes results in constant improvements

## Programming environment

### Unix

#### What is UNIX and what is Linux?

UNIX: the ~ OS was born in the 1960s. Ken Thompson began to develop it, it is a proprietary OS. The ~ works on CLI (Command Line Interface). Popular in companies, universities.

LINUX: ~ is an OS, built by Linus Torvalds in 1991. The name comes from the Linux kernel. It is the software on a computer which enables applications to perform some functions.
Support multitasking
Programs consist of one or more processes, and each process have one or more threads
It can easily co-exists along with other Operating systems.
It can run multiple user programs
Individual accounts are protected because of appropriate authorization
Linux is a replica of UNIX but does not use its code.

UBUNTU: ~ is a Linux distribution based on Debian mostly composed of free and open-source software. It is released in every 6 months (newest version is "Focal Fossa", v20.04)

("Ubuntu" means (after the Nguni phylosophy): "humanity to others. I am what I am because of who we all are.") 

Debian: "Deb and Ian" - from Ian Murdoch; collection of linux extensions

#### What do we call the shell in Linux?

SHELL: ~  origins: "C Shell" sounds like "seashell".
~ is the connection between the kernel and the user.
e.g. GUI - graphical user interface (Windows)
CLI - command line interface (Linux)

#### What does root means in a Linux environment?

ROOT:
The ~ is the user name or account that by default has access to all commands and files on a Linux or other Unix-like operating system. It is also referred to as the root account, root user, and the superuser.

#### How do you access your personal files in Linux?

Every **user** on a **Linux** system, whether created as an account for a real human being or associated with a particular service or system function, is **stored** in a file called "/etc/passwd". The "/etc/passwd" file contains information about the **users** on the system.

#### How can you install an application in Linux?

I can install them with the 'sudo', super user.

To install from a software repository, there's usually a command:

$ sudo apt update

$ sudo apt install python 3.8.

If we search for installing something with ubuntu, there is usually a step-by-step description on how to do it.

#### What is package management in Linux, what are repositories?

Package management is a method of installing and maintaining (which includes updating and probably removing as well) software on the system. In the early days of **Linux**, programs were only distributed as source code, along with the required manual pages, the necessary configuration files, and more.

#### How do you navigate in the filesystem with the command line?

Commands for files and directories:

1. To navigate into the root directory, use "cd /"
2. To navigate to your home directory, use "cd" or "cd ~<foldername>"
3. To navigate up one directory level, use "cd .."
4. To navigate to the previous directory (or back), use "cd -"

#### What does the following commands do: mkdir, rm, cat, cp, touch?

mkdir: creates a new directory

rm: removes files and directories
cat: creates files with the text I type in the terminal
cp: copy files
touch: creates empty files

#### How can you look up what does a command do in Linux if you have no internet connection?

I can use the $ help, man (for manual), info, or whatis

#### What does the following commands do: head, tail, more, less?

head: displays the first ten lines of a file, unless otherwise stated.
tail: display the last part of the file
more: to view a text file one page at a time, (press spacebar to go to the next page)
less: you can navigate the page up/down using the less command and not possible in more command. You can search a string in ~ command

#### How do you download a file from internet using the terminal?

Using the 'wget' command

e.g.:

$ wget https://askubuntu.com/questions/207265/how-to-download-a-file-from-a-website-via-terminal

