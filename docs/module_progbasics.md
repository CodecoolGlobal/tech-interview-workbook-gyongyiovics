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

List: a collection which is ordered and changeable. Allows duplicate members. Indexing starts with zero. Lists are written with square brackets ( []).

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
```Python
def recur_fibo(n):
if n <= 1:
    return n
else:
    return(recur_fibo(n-1) + recur_fibo(n-2))
```
#### How do you find a max value in a list/array if you can’t use any built-in functions?
```Python
def max(values_list):
    values_list = [1,2,3,4,5,3]
    max_value = None
    for value in values_list:
        if not max_value:
            max_value = value
        elif value > max_value:
            max_value = value
    return max_value
```
#### How do you find the average of values in a list/array if you can’t use any built-in functions?
```Python
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
```

#### What do we call an *in-place* sort?

sort() - is a list method that modifies the list in place, 

sorted() - is a built-in function that creates a new list without touching the original one.

There are other methods beside these.

e.g. the "bubble-sort", which sorts the list element-by-element

```Pyhton
numbers = [1, 2, 56, 32, 51, 2, 8, 92, 15]
i = 0
j = 0
lenght = len(numbers)

for i in range(lenght):
    for j in range(1, lenght - i):
        if numbers[j-1] > numbers[j]:
            (numbers[j-1], numbers[j]) = (numbers[j], numbers[j-1])
```	    
  
	    

#### Explain an algorithm which sorts a list!

def bubble_sort(array):

​	n = len(array)

​	for i in range(n):

(create a flag that will allow the function to terminate early if there's nothing left to sort already_sorted = True. Start looking at each item of the list one by one, comparing it with its adjacent value. With each iteration, the portion of the array that you look at shrinks because the remaining items have already been sorted.)

​		for j in range(n - i - 1):

​			if array[j] > array[j+1]:

​			(if the item you are looking at is greater than its adjacent value, then swap them)

​				array[j], array[j+1] = array[j+1], array[j]

​				(since you had to swap two elements, set the 'already_sorted' flag to 'False', so the algorithm does not finish prematurely. IF there were no swaps during the last iteration, the array is already sorted, and you can terminate if already _sorted: break)

​	return array 

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

DICTIONARY: A ~ is a collection which is unordered, changeable and indexed. In Python dictionaries are written with curly brackets("{}"), and they have keys and values.

You can access the items of a dictionary by referring to its key name, inside square brackets:
thisdict = {"brand": "Ford", "model":"Mustang","year": 1964}

referring to a "key":
for x in thisdict:
	print(x)

referring to a "value":
for x in thisdict:
	print(thisdict[x]) 
	
referring to both:

for x, y in thisdict.items():
	print(x,y)
	
adding items to a dictionary:

thisdict {"size" : 56}

thisdict["color"] = "red"

thisdict = {"color": "red", "size": 56}

removing items from a dictionary:

thisdict.pop("model")

#### What does it mean that an object is immutable in Python?

Everything in Python (argument, variable, list, etc) is an object, and all objects can be either **mutable** or **immutable**.

A **mutable** object can be changed after it is created, and an **immutable** object can’t.

mutable objects: lists, dictionaries, sets
immutable objects: bools, integers, floats, tuples, strings, (frozensets)

#### What is conditional expression in Python?

if Statement:

e.g. if <expression>:

​	<statement>

The expression is evaluated in Boolean contexts - if the expression is true, then the statement will  be executed. If expression is false, then statement is skipped and not executed.

The else and elif clauses can be used, if we want to branch the executions because there are several alternatives. Elif clause can be  used several times after the if expression, and there always has to be an else statement as well.

e.g.

if 'expression1':

​	'statement1'

elif 'expression2':

​	'statement2'

elif 'expression3':

​	'statement3'

else:

​	'statement4'

#### What are different types of arguments in Python?

TYPES: 

1. default arguments:
   e.g. def myfunct(variable, message = "Hellobello")

message is a "default" argument, as it has a given a default value.
However if there is another value in the function, it overwrites the default one.
Once we have a ~, all the arguments to its right have to have default values.

2. keyword arguments: when we call a function with some values, these values get assigned to the arguments according to their position. When we call functions in this way, the order (position) of the arguments can be changed.

3. positional arguments:

   e.g.

   greet("Bruce", msg = "How do you do?")

   in this case, "Bruce" is a positional argument in the greet function.

   We can mix it with a keyword argument, but we must keep in mind that the order of the arguments must be:

   positional argument and then keyword argument (otherwise python will not understand the function and there will be an error message)

4. arbitrary arguments: if we do not know in advance the number of arguments that will be passed into a function, we can use arbitrary number of arguments.

   e.g. 

   names = ["Monica", "Luke", "Steve", "John"]

   def greet(*names):

   ​	for name in names:

   ​		print("Hello", name)

   greet("Monica", "Luke", "Steve", "John")

#### What is variable shadowing? (context: variable scope)

If a variable is given outside of a function and there is another variable with the same name, the latter can overshadow the "outside" variable, if both are used in the function. To avoid this situation, we can give a different name to the "inside" variable or we can add "global" to the "outside" variable's name.

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

Every item in a list lives at its own unique index; which are in order, starting from 0. If we remove an item, any item with an index greater than the one we've removed has now been shifted down. Therefore, if we remove an item during a for loop, the (e.g. with the index number 0), the item at index 1 becomes the item at index 0.

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?

A variable is only available from inside the region it is created. This is called **scope**. There are four major types of variable scope and is the basis for the LEGB rule:

L = local: Whenever you define a variable within a function, its scope lies ONLY within the function. it is accessible from the point at which it is defined until the end of the function and exists for as long as the function is executing.

E = enclosed: it happens, when we write a function with a nested function. In this case the "outside" function's variable has a larger scope than the "inner" function's, therefore it can be accessed from the inner function, but the variable defined in the inner function cannot be accessed through the outside function.

G = global: Whenever a variable is defined outside any function, it becomes a global variable, and its scope is anywhere within the program. Which means it can be used by any function

B = built-in: this is the widest scope. All the special reserved keywords fall under this scope. (e.g. pi in math)

lifetime of variables: and enclosed variable lifetime is between it is defined and the execution of the inner function

#### If you need to access the iterator variable after a for loop, how would you do it in Python?

An iterable is an object capable of returning its members one by one. Said in other words, an iterable is anything that you can loop over with a for loop in Python.

e.g.

list = [15, 9, 55]

sum = 0

for i in list:

​	sum = sum + i

iterable = > i is for the indexes of the elements of the list

#### What type of elements can a list contain in Python?

Lists can have any number of items and they may be of different types (string, integer, float, another list, dictionary)

If a list has an item which is also a list, that is called a nested list.

#### What is slice operator in Python and how to use?

The slice object is used to slice a given sequence (string, bytes, tuple, list or range) or any object which supports sequence protocol.

The syntax of slice() is:

slice(start, stop, step)

parameters:

start (optional) - Starting integer where the slicing of the object starts. Default to `None` if not provided.

stop - Integer until which the slicing takes place. The slicing stops at index (stop - 1), and the element at the stop index is not included.

step (optional) - Integer value which determines the increment between each index for slicing. Defaults to  "None" if not provided.

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?

Only + and *.

e.g. for +:

list_one = [1,2,3]

list_two = [4,5,6]

list_three =list_one + list_two

list_three = [1,2,3,4,5,6] - concatenated version of list_one and list_two

e.g. for *:

list = [3,4,5]

list_2 = 4*list

list_2 = [3,4,5,3,4,5,3,4,5,3,4,5] - that means, multiplication multiplies all of the elements of the same list and adds them up in another list

#### What is the purpose of the in and not in membership operators in Python?

It is to check is something is or is not in the list.

#### What does the + operator mean when used with strings in Python?

They concatenate the text, therefore add up the elements of the string

#### Explain f strings in Python?

Every **f-string** statement consists of two parts, one is character **f** or **F**, and the next one is a string which we want to format. The string will be enclosed in **single**, **double**, or **triple** quotes.

e.g.

f'"type some text here"

e.g. with variables:

name = "Gizi"

type_of_company = "Financial"

print(f"{name} works for a {type_of_company} company.")

Unlike format() method, in f-string we do not have to separate the variables from the text

e.g. for format()

print("{}, a computer science portal for geeks.".format(GeeksforGeeks))

#### Name 4 iterable types in Python!

An **iterable** is any Python object capable of returning its members one at a time, permitting it to be iterated over in a for-loop.

Familiar examples of iterables include lists, tuples, and strings - any such sequence can be iterated over in a for-loop. We will also encounter important non-sequential collections, like dictionaries and sets; these are iterables as well. It is also possible to have an iterable that “generates” each one of its members upon iteration - meaning that it doesn’t ever store all of its members in memory at once. We dedicate an entire section to generators, a special type of iterator, because they are so useful for writing efficient code.

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?

**Comprehension**: list-, set-, and dictionary comprehension - they return another list, set or dictionary.

e.g. 

dict1 = {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5} 

 double_dict1 = {k:v*2 for (k,v) in dict1.items()} print(double_dict1)



**Generator expression**: it returns a different type of object:

e.g.

x = 1

sum(x*x for x in range(10))

returns a number: the  summary of the squares for numbers from 1 to 10 (285)

#### Does the order of the function definitions matter in Python? Why?

Yes. Especially if I want to call a function within another function. 

E.g. in a game where there are different functions written for the different steps and there is a "main()" function, it is reasonable to write the main function at the end of the code, as it will use the other functions.

#### What does unpacking mean in Python?

We can  have a function that receives four arguments. We want to make call to this function and we have a list of size 4 with us that has all arguments for the function. If we simply pass list to the function, the call doesn’t work.

e.g.

my_list = [a,b,c,d]

def fun(*my_list):

​	print(a,b,c,d)

In this case, the function unpacks the elements from my_list to return them separately. We can also use dictionaries this way, but with them ** is used.

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

The return will be "None", because if there is no return statement (or just a return without an argument), an implicit return is added to the end of the function. 

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

We can use the try and except blocks in order to catch exceptions in our code without crashing it.

Unlike errors (syntactic or semantic), exceptions can be of many types that occur during the execution and are not unconditionally inoperable.

e.g. if there is a division written in the program, and there is an intervall which includes zero, we can catch and avoid the division by zero with handling it as an exception (ZeroDivision).

There can also be exceptions like: ValueError, RangeError.

#### What are the basics of exception handling in Python?

The steps of exception handling in python are:

try: to run the code

except: execute the code when there is an exception

else: no exceptions? Then run the code.

finally: Always run the code

#### In which case should we catch an exception? Why?

We can catch them in order to keep the code running, e.g. do not let it be stopped by an exception (e.g. there is an input and we are expecting a number, there can be an exception if the user enters a letter)

#### What can/should we do with an exception in the ‘except’ block?

We can give an exception statement.

e.g. 

print("you tried to divide by zero")

#### What does the else and finally statement do in a try-except block in Python?

Else and finally statements refer to the opposite case of the exception.

 Else refers to the case if the exception is not true (and the else block will be executed).

Finally is irrespective of whether there is an exception or not, that block of code will always be executed.

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

