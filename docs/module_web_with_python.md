# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
- queries should be written in multiple lines (more readable)
- SELECT ... AS or ALIAS (naming convention)
- customized case-use (e.g. verbs with uppercase, table-names with lowercase)
- not to forget the ";" sign at the end of the query
- in a SELECT use IN instead of OR if there are multiple choices (e.g. SELECT FROM actors WHERE name IN ...)

#### What layers can you name in a simple web application?
Three layer model: Presentation layer, Business layer, Data layer.

Conceptually **the three**-**tier architecture** is linear. However, the [model-view-controller] **MVC architecture** is triangular: the view sends updates to the controller, the controller updates the model, and the view gets updated directly from the model. **MVC** is a pattern used to make UI code easier to maintain and test.

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
If I want to pass an item of an array with a non-existing index-number (in console.log for example), 
the output is "nondefined", as the item is not part of the array.

#### What is the “finally” block, and how would you use it?
The try/catch/finally statement handles some or all of the errors that may occur in a block 
of code, while still running code.
the finally statement lets you execute code after try and catch, regardless of the result.

#### Why should we catch special exception types?
The special exceptions are caught in order to make the website user friendly. 
That means if there are some semantic errors - not enough letters in a password, not the right format, if a password is used already it is good to alert the user about them. 

### Security
#### What is SQL injection? How to protect an application against it?

SQL injection is a most common web hacking technique. It is a placement of malicious code in SQL statements, via web page input.

To protect a web site from SQL injection, you can use SQL parameters (SQL parameters are values that are added to an SQL query at execution time, in a controlled manner).

#### What is XSS? How to protect an application against it?

Cross-site scripting (XSS) is the injection of malicious scripts into a normally trusted web application. This is possible whenever user input is not sufficiently validated either on the client- or the server-side. These scripts contain malware that enables the hacker to perform a variety of attacks.

(malware = malicious software)

There are three main types of XSS attacks. These are:

- [Reflected XSS](https://portswigger.net/web-security/cross-site-scripting#reflected-cross-site-scripting), where the malicious script comes from the current HTTP request.
- [Stored XSS](https://portswigger.net/web-security/cross-site-scripting#stored-cross-site-scripting), where the malicious script comes from the website's database.
- [DOM-based XSS](https://portswigger.net/web-security/cross-site-scripting#dom-based-cross-site-scripting), where the vulnerability exists in client-side code rather than server-side code.

How to prevent an XSS attack?

Possible ways of defense: filtering the input on arrival, encoding the data on output, use of appropriate response headers, content security policy (CSP)

#### How to properly store passwords?

We can properly store passwords by hashing and salting, and in a database on the computer which cannot be read by others

#### What is HTTPS?

HTTPS: Hypertext Transfer Protocol Secure

#### What is encryption and decryption?

Encryption: ~ is a process which transforms the original information into an unrecognizable form.

Decryption: ~ is a process of converting encoded/encrypted data in a form that is readable and understood by a human or a computer.

#### What is hashing?

**Hashing** is an algorithm performed on data such as a file or message to produce a number called a **hash** (sometimes called a checksum). The **hash** is used to verify that data is not modified, tampered with, or corrupted. In other words, you can verify the data has maintained integrity.

#### What is the difference between encryption and hashing? When would you use which?

Hashing is used to validate the integrity of the content by detecting all modifications and thereafter changes to a hash output. Encryption encodes data for the primary purpose of maintaining data confidentiality and security. It requires a private key to reversible function encrypted text to plain text.

In short, encryption is a two-way function that includes [encryption and decryption](https://www.ssl2buy.com/wiki/what-is-encryption-and-decryption/) whilst hashing is a one-way function that changes a plain text to a unique digest that is irreversible.

hashing is used for digital signatures, forms of authentication

encryption is used in an online-correspondence, transmitting financial data 

#### What encryption methods do you know?

Hashing - creates a unique, fixed-length signature for a message or data set

Symmetric encryption method - private-key cryptography. Anyone with access to the key can decrypt the data. Using this method, a sender encrypts the data with one key, sends the data, and then the receiver uses the key to decrypt the data.

Asymmetric encryption method - public-key cryptography. This method uses two keys for encryption or decryption  (giving it the potential to be more secure). With this method, a public key freely available to everyone is used to encrypt messages, and a different, private key is used by the recipient to decrypt messages.

#### What hashing methods do you know?

Hash() function in Python.

Other methods: MD5, SHA-1, SHA-2, SHA-3, Whirlpool, BLAKE2

#### How/where would you store sensitive data (like db password, API key, ...) of your application?

- store the data in a portable device, file
- use encryption (e.g. the hash() method)

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?

A stack is a linear data structure in which elements can be inserted and deleted only from one side of the list, called the top.

The **queue data structure** follows the FIFO (First In First Out) principle, i.e. the element inserted at first in the list, is the first element to be removed from the list.

#### What is BubbleSort? Describe the main logic of this sorting algorithm.

```
let bubbleSort = (inputArr) => {
    let len = inputArr.length;
    let swapped;
    do {
        swapped = false;
        for (let i = 0; i < len; i++) {
            if (inputArr[i] > inputArr[i + 1]) {
                let tmp = inputArr[i];
                inputArr[i] = inputArr[i + 1];
                inputArr[i + 1] = tmp;
                swapped = true;
            }
        }
    } while (swapped);
    return inputArr;
};
```

#### Explain the process of finding the maximum and minimum value in a list of numbers!

The easy way:

```js
let min = Math.min.apply(null, arr),
    max = Math.max.apply(null, arr);
```

The more complicated but nicer way:

```js
function arrayMax(array) {
  return array.reduce((a, b) => Math.max(a, b));
}

function arrayMin(array) {
  return array.reduce((a, b) => Math.min(a, b));
}
```



#### Explain the process of calculating the average value in an array of numbers!

const grades = [80, 77, 67, 4, 56];

let total = 0;

for (let i = 0; i <grades.length; i++) {

​	total += grades[i];

}

let avg = total / grades.length;



#### What is Big O complexity? Explain time and space complexity!

Big O notation is used in computer science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used by an algorithm. It is hard to pin down the exact runtime required by an algorithm, it depends on what processor you use, what other programs the computer is running.

So instead of calculating that, we use a concept to see ***how quickly the runtime grows\****.* Imagine when we write a piece of code, we would more likely end up in refactoring it not just because we want to keep the application DRY, but we want to make sure the efficiency of our code, which is directly related to user experience.

#### Explain the process of calculating the average value in a list of numbers!

let sum = 0;

for (let i = 0; i < myArray.length; i++) {

sum += parseInt(myArray[i], 10);}

### Procedural
#### How the CASE condition works in SQL?

in Postgres:

e.g.

CASE 

​	WHEN condition_1 THEN result_1

​	WHEN conditon_2 THEN result_2

​	....

​	ELSE result_n

END



#### How the switch-case condition works in JavaScript?

switch(*expression*) {
 case *x*:
  *// code block
\*  break;
 case *y*:
  *// code block
\*  break;
 default:
   // *code block*
}

#### How to achieve a switch-case-like structure in Python?

I can achieve it with if-elif-else conditions or with a logical operator.

E.g. for if-elif-else code:

a = 200
b = 33
if b > a:
 print("b is greater than a")
elif a == b:
 print("a and b are equal")
else:
 print("a is greater than b")

E.g. for a code with logical operators:

a = 200
b = 33
c = 500
if a > b or a > c:
 print("At least one of the conditions is True")

#### Explain variable scoping in Python!

Local scope: A variable created inside a function belongs to the *local scope* of that function, and can only be used inside that function.

Global scope: A variable created in the main body of the Python code is a global variable and belongs to the global scope. Global variables are available from within any scope, global and local. 

#### What’s the difference between const and var in JavaScript?

var: Before 2015, using the `var` keyword was the only way to declare a JavaScript variable. The 2015 version of JavaScript (ES6 - ECMAScript 2015) allows the use of the `const` keyword to define a variable that cannot be reassigned, and the `let` keyword to define a variable with restricted scope.

len: variables declared with the ~ keyword can have Block scope. That means the variables declared inside a block cannot be accessed from outside the block. Redeclaring a variable with ~, in another scope, or in another block is allowed.

const: Constants are block-scoped, much like variables declared using the `let` keyword. The value of a constant can't be changed through reassignment, and it can't be redeclared.

#### How the list comprehension looks like in Python?

[expression for item in list]

with an example:

[letter for letter in 'human']

#### How the “ternary expression” looks like in Python?

a if condition else b

```
[on_true] if [expression] else [on_false] 
```

#### How the ternary expression looks like in JavaScript?

e.g.

var age = 19;

var canDrive = age > 16 ? 'yes' : 'no'

In this case, the output is 'yes', as the statement is true: 19 is bigger than 16.

#### How to import a function from another module in Python?

from main.py import my_function

#### How to import a function from another module in JavaScript?

dom.js

export let dom = {};

boards.js

```js 
import {dom} from "./dom.js";
```

### Functional
#### What is recursion?

The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion. 

For example, we compute factorial n if we know factorial of (n-1). The base case for factorial would be n = 0. We return 1 when n = 0. 

#### Write a recursive function which calculates the Fibonacci numbers!

In python:

```html
def recur_fibo(n):
   if n <= 1:
       return n
   else:
       return(recur_fibo(n-1) + recur_fibo(n-2))

nterms = 10

# check if the number of terms is valid
if nterms <= 0:
   print("Plese enter a positive integer")
else:
   print("Fibonacci sequence:")
   for i in range(nterms):
       print(recur_fibo(i))
```

In JavaScript:

function fibonacci(num, memo) {

memo = memo || {};

if (memo[num]) return memo[num];

if (num <= 1) return 1;

return memo[num] = fibonacci(num-1, memo) + fibonacci(num-2, memo);

}

#### How to store a function in a variable in Python?

Set a variable to a function and then use the variable as the function's name

def cube(number):

​	return number**3

make_cube = cube (without the parentheses)

#### List the ways of defining a callable logical unit in JavaScript!

- Function expression => arrow function

- Function in object literal - concise method syntax

- Constructor - class

- Generator functions and generator methods

- Function declaration => const + arrow function

- IIFE - immediately invokable function expression (

  ```
  function demoFunction(){
  
    alert("This is the function Definition");
  
  }
  ```

  )

  

#### What is an event listener? How to attach one?
The `addEventListener()` method attaches an event handler to the specified element.

The `addEventListener()` method attaches an event handler to an element without overwriting existing event handlers.

You can add many event handlers to one element.

You can add many event handlers of the same type to one element, i.e two "click" events.

You can add event listeners to any DOM object not only HTML elements. i.e the window object.

The `addEventListener()` method makes it easier to control how the event reacts to bubbling.

When using the `addEventListener()` method, the JavaScript is separated from the HTML markup, for better readability and allows you to add event listeners even when you do not control the HTML markup

#### How to trigger an event in JavaScript?

We can trigger an event by simulating a click on a checkbox using DOM methods:

```js
function simulateClick() {
  const event = new MouseEvent('click', {
    view: window,
    bubbles: true,
    cancelable: true
  });
  const cb = document.getElementById('checkbox'); 
  const cancelled = !cb.dispatchEvent(event);

  if (cancelled) {
    // A handler called preventDefault.
    alert("cancelled");
  } else {
    // None of the handlers called preventDefault.
    alert("not cancelled");
  }
}
```

#### What is a callback function? Tell some examples of its usage.

A callback is a function passed as an argument to another function.

E.g.

function myDisplayer(some) {
 document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2, myCallback) {
 let sum = num1 + num2;
 myCallback(sum);
}

myCalculator(5, 5, myDisplayer);

Callbacks can be used in asynchronous functions, where one function has to wait for another function (e.g. waiting for a file to load).

#### What is a Python decorator? How does it work? Tell some examples of its usage.

A decorator takes in a function, adds some functionality  and returns it.

```
def first(msg):
    print(msg)


first("Hello")

second = first
second("Hello")
```



#### What is the difference between synchronous and asynchronous execution?

Synchronous or *Synchronized* means "connected", or "dependent" in some way. In other words, two synchronous tasks must be aware of one another, and one task must execute in some way that is dependent on the other, such as wait to start until the other task has completed.
Asynchronous means they are totally independent and neither one must consider the other in any way, either in the initiation or in execution.

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?

postgresql, DataGrip

#### When do you use the DISTINCT keyword in SQL?

if I want to return (SELECT) different items in a database

#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?

WHERE is a filter, with which I can give a condition to a query

GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country". The GROUP BY statement is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.

 The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.

ORDER BY is can order the query results by a number 

#### What are aggregate functions in SQL? Give 3 examples.

COUNT, SUM, AVG, MAX or MIN

The following statement use the `AVG()` function to return the average list price of all products in the products table:

```html
SELECT
    AVG(list_price) avg_product_price
FROM
    production.products;
```

The following statement uses the `COUNT()` function to return the number of products whose price is greater than 500:

```html
SELECT
    COUNT(*) product_count
FROM
    production.products
WHERE
    list_price > 500;
```

The following statement uses the [MAX()](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-max/) function to return the highest list price of all products:

```htnl
SELECT
    MAX(list_price) max_list_price
FROM
    production.products;
```

#### What kind of JOIN types do you know in SQL? Could you give examples?

INNER JOIN - returns records that have matching values in both tables

LEFT JOIN - returns all records from the left table, and the matched records from the right table

RIGHT JOIN - returns all records from the right table, and the matched records from the left table

FULL JOIN - returns all records when there is a match in either left or right table

e.g.

SELECT column_name(s) FROM table1

LEFT JOIN table2 ON table1.column_name = table2.column_name;

(in this case, "table2" is the right table, therefore all of the columns are included of table1 and only the matched records from table2)

#### What are the constraints in sql?

SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.

Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.

#### What is a cursor in SQL? Why would you use one?

Execute a SQL query agains the database.

E.g.:

```
conn = db.connect()
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM Metatable WHERE TableName='%s'" % clsname)
    res = cursor.fetchall()
    ...
    cursor.close()
    conn.rollback()
```

#### What are database indexes? When to use?

Primary key: The PRIMARY KEY constraint uniquely identifies each record in a table. Primary keys must contain UNIQUE values, and cannot contain NULL values. A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

Foreign key: A FOREIGN KEY is a key used to link two tables together. A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table. The table containing the foreign key is called the child table, and the table containing the candidate key is called the referenced or parent table.

#### What are database transactions? When to use?

BEGIN TRANSACTION, SET TRANSACTION, COMMIT, ROLLBACK, SAVEPOINT, RELEASE SAVEPOINT 

A transaction should be used when you need a set of changes to be processed completely to consider the operation complete and valid. In other words,  it checks whether only a portion executes successfully, will that result in incomplete or invalid data being stored in your database.

For example, if you have an insert followed by an update, what happens if the insert succeeds and the update fails? If that would result in incomplete data (in this case, an orphaned record), you should wrap the two statements in a transaction to get them to complete as a "set".

#### What kind of database relations do you know? How to define them?

There are three types:

one-to-one: a row in table A can have only one matching row in table B and vice versa.

one-to-many or many-to-one: This is the most common relationship type. In this type of relationship, a row in table A can have many matching rows in table B,  but a row in table B can have only one matching row in table A. This can also be a Many-to-One relationship depending on which way we look at it.

many-to-many: in a ~ relationship, a row in table A can have many matching rows in table B, and vice versa.

In this case we can use an intermediary table or "junction table" which links the table A with table B with one key from each.

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

SELECT * FROM address WHERE city = 'Miskolc';

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

We can use the Change Tracking: 

ALTER DATABASE AdventureWorks2012   SET CHANGE_TRACKING = ON   (CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  

Otherwise, we can use the git history.

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?

XML - extensible markup language. It is a [markup language](https://en.wikipedia.org/wiki/Markup_language) that defines a set of rules for encoding [documents](https://en.wikipedia.org/wiki/Electronic_document) in a [format](https://en.wikipedia.org/wiki/File_format) that is both [human-readable](https://en.wikipedia.org/wiki/Human-readable_medium) and [machine-readable](https://en.wikipedia.org/wiki/Machine-readable_data).

XHTML - extensible hypertext markup language. XHTML is an application of [XML](https://en.wikipedia.org/wiki/XML), a more restrictive subset of SGML. XHTML documents are [well-formed](https://en.wikipedia.org/wiki/Well-formed_document) and may therefore be parsed using standard XML parsers, unlike HTML, which requires a lenient HTML-specific parser

HTML - hypertext markup language.  It is the standard [markup language](https://en.wikipedia.org/wiki/Markup_language) for documents designed to be displayed in a [web browser](https://en.wikipedia.org/wiki/Web_browser). It can be assisted by technologies such as [Cascading Style Sheets](https://en.wikipedia.org/wiki/Cascading_Style_Sheets) (CSS) and [scripting languages](https://en.wikipedia.org/wiki/Scripting_language) such as [JavaScript](https://en.wikipedia.org/wiki/JavaScript).

#### How to include a JavaScript file in a webpage?

There are 2 ways: 

in a "script" tag:

<script>document.getElementById("demo").innerHTML = "My First JavaScript";</script>

in a separate file with "js" extension. In this case we have to refer to the file location within the HTML file like this:

<script src="app.js"></script>

#### How to include a CSS file in a webpage?

inline,

style -tag

separate file

<link rel="stylesheet" href="css/style.css">

#### How to select an element using its id in CSS?

We can select an element using its id with a (#) sign.

e.g.

#itemName { align: center; }

#### How to select elements using their class in CSS?

We can select an element using its class-name by using the (.)

e.g.

.className { color: blue; }

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

style.css

.alpha {color: blue;}

.beta {width: 100%;}

#### How to select all list items in all ordered lists on the page in CSS?

style.css

ol li {text-align: center;}

#### How to select elements using their attributes in CSS?

E.g.

this example selects all <a> elements with a target attribute:

a[target] {
 background-color: yellow;
}

in the HTML file:

<a href = "disney.com" target="_blank">disney.com</a>

(click on the link to show code)

#### What are UX and UI?

UX - user experience. It is the interaction and experience users have **with a** company's products and services. 

User interface (**UI**) **is** the specific asset users interact with. For example, **UI** can deal with traditional concepts like visual design elements such as colors and typography.

#### Please list some points that an application should fulfill to have good UX.

error handling

username and password dependencies

- **Useful**: Your content should be original and fulfill a need
- **Usable**: Site must be easy to use
- **Desirable**: Image, identity, brand, and other design elements are used to evoke emotion and appreciation
- **Findable**: Content needs to be navigable and locatable onsite and offsite
- **Accessible**: Content needs to be accessible to people with disabilities
- **Credible**: Users must trust and believe what you tell them

#### What is XML, XSLT, DTD?

XML: **Extensible Markup Language** (**XML**) is a markup language that defines a set of rules for encoding documents in a format that is both human-readable and machine-readable. The design goals of XML emphasize simplicity, generality and usability across the Internet.

XSLT: **Extensible Stylesheet Language Transformations (XSLT)** is a language for transforming XML documents into other XML documents, or other formats such as HTML for web pages, plain text or XSL formatting objects. 

DTD: Document Type Definition (DTD) is a set of markup declarations that define a document type for an SGML-family markup language (GML, SGML, XML, HTML)

#### What is the difference between HTML and XML?

**Difference between HTML and XML:** There are many differences between HTML and XML. These important differences are given below:

|                      HTML                       |                             XML                              |
| :---------------------------------------------: | :----------------------------------------------------------: |
| HTML stands for **Hyper Text Markup Language.** |        XML stands for **extensible Markup Language.**        |
|                 HTML is static.                 |                       XML is dynamic.                        |
|           HTML is a markup language.            |      XML provides framework to define markup languages.      |
|          HTML can ignore small errors.          |                  XML does not allow errors.                  |
|           HTML is not Case sensitive.           |                    XML is Case sensitive.                    |
|         HTML tags are predefined tags.          |               XML tags are user defined tags.                |
|    There are limited number of tags in HTML.    |                   XML tags are extensible.                   |
|      HTML does not preserve white spaces.       |             White space can be preserved in XML.             |
|   HTML tags are used for displaying the data.   | XML tags are used for describing the data not for displaying. |
|    In HTML, closing tags are not necessary.     |             In XML, closing tags are necessary.              |

### Javascript

#### What is javascript?

~ is a programming language, that conforms to the ECMAScript specification. It is high-level, often just-in-time compiled, and multiparadigm. It is used for websites' client-side page behavior

#### When to use AJAX? Bring examples of its usage.

If you do not want to load the whole page when a button is pushed or a request is sent from another page.

For example: form validation, comments, filtering data, surveys and polls

#### What is DOM and how to manipulate it from Javascript?

Document Object Model - JavaScript can change its elements, attributes and styles;

JavaScript also can add, create, remove these elements, and JS can react to all existing HTML events on a page

#### What are events and how/why to use them in Javascript?

HTML events are "things" that happen to HTML elements. When JavaScript is used on HTML pages, JavaScript can react on these events.

E.g.

<button onclick="document.getElementById('demo').innerHTML=Date()">The time is?</button>

#### What is event bubbling/capturing? How would you use it?

When an event happens on an element, it first runs the handlers on it, then on its parents, then all the way up on other ancestors.

E.g.

<style>   body * {     margin: 10px;     border: 1px solid blue;   } </style>  <form onclick="alert('form')">FORM   <div onclick="alert('div')">DIV     <p onclick="alert('p')">P</p>   </div> </form>

In this case a click on the inner <p> first runs onclick:

on that <p> tag

then on the outer <div>

then on the outer <form>, and so on upwards till the document object.

#### What is JSON and how do we use it?

JSON: JavaScript Object Notation. ~ is a syntax for storing and exchanging data.

When exchanging data between a browser and a server, the data can only be text.

JSON is text, and we can convert any JavaScript object into JSON, and send JSON to the server. We can also convert any JSON received from the server into JavaScript objects. This way we can work with the data as JavaScript objects, with no complicated parsing and translations.

E.g. in flask, the jsonify() function creates a response with the JSON representation of the given arguments with an application/json mimetype. The arguments to this function are the same as to the dict constructor.

## Software engineering

### Version control

#### What type of branching strategy would you use?

branching by tasks, features

e.g.

If there is a webpage, and we have to build a login page and a user page there would be 2 different branches for the two.

#### What would you do if you find a bug on the production code (master branch)?

I can make a "bugfix branch" from the master branch,  making some commits on the bugfix branch to fix the problem, and then merge it into the master branch.

#### How can you move changes from one branch to another in GIT?

I can move changes from one branch to the other by merging them.

e.g.

branch feature/pagination

branch feature/counter

I can checkout - switch to the "feature/counter" branch - and merge all the changes from the "feature/pagination" branch into it. 

If I am at the right place - in the "feature/counter" branch in this case - all I have to do is merge the "feature/pagination" branch:

merge feature/pagination 

Then if there is any git conflicts I can also look through them and merge or ignore them.

I can do this via the terminal, through the pyCharm IDE  or through the github repository.

#### How does a VCS help with code reviews?

In computer [software engineering](https://en.wikipedia.org/wiki/Software_engineering), revision control is any kind of practice that tracks and provides control over changes to [source code](https://en.wikipedia.org/wiki/Source_code). [Software developers](https://en.wikipedia.org/wiki/Software_developer) sometimes use revision control software to maintain documentation and [configuration files](https://en.wikipedia.org/wiki/Configuration_file) as well as source code.

### 1. Clone the Repository

First, you’ll clone the repository where you will contribute code onto your local workstation. Cloning is common in Git. It’s done to create a local copy of the repository.

### 2. Branch and Merge Properly

Next, you’ll want to make a local branch for your work, so you can keep your work separate from the branch residing on the code host. Following proper [branching and merging practices](https://www.perforce.com/blog/vcs/best-branching-strategies-high-velocity-development) is important.

When you’re done with your work (bug fixes or new code), you’ll push your branch up to the code host, using the Git push command.

### 3. Create a Merge/Pull Request

Now, you’ll need to share the code you’ve just written, so it will become part of the work of the team. Depending on the code host, this will be a merge or pull request. Generally, this is done in the web interface of the code host.

In most systems, the path to getting your code merged is through a code review. This ensures the changes are reviewed before they are merged. It’s best to write a clear description of the changes you’ve made in the merge or pull request, so the reviewer knows what to review.

#### What is your favorite git command? Why?

The "git push". This is my favorite because whenever I use it that means I have finished a task in the given project - or finished up a feature.

#### What does remote/local mean in Git?

Remote repositories are versions of your project that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either read-only or read/write for you. Collaborating with others involves managing these remote repositories (repos) and pushing, pulling data to and from them when you need to share work.

### DevOps

#### Why is it good to use a package manager software?

A **package manager** or **package-management system** is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a [computer](https://en.wikipedia.org/wiki/Computer)'s [operating system](https://en.wikipedia.org/wiki/Operating_system) in a consistent manner.[[1\]](https://en.wikipedia.org/wiki/Package_manager#cite_note-1)

A package manager deals with [*packages*](https://en.wikipedia.org/wiki/Package_format), distributions of software and data in [archive files](https://en.wikipedia.org/wiki/Archive_file). Packages contain [metadata](https://en.wikipedia.org/wiki/Metadata), such as the software's name, description of its purpose, version number, vendor, [checksum](https://en.wikipedia.org/wiki/Checksum) (preferably a [cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)), and a list of [dependencies](https://en.wikipedia.org/wiki/Coupling_(computer_programming)) necessary for the software to run properly. Upon installation, metadata is stored in a local package database. Package managers typically maintain a database of software dependencies and version information to prevent software mismatches and missing prerequisites. They work closely with [software repositories](https://en.wikipedia.org/wiki/Software_repository), [binary repository managers](https://en.wikipedia.org/wiki/Binary_repository_manager), and [app stores](https://en.wikipedia.org/wiki/App_store).

#### Why is it good to use a virtual environment for a project?

Python applications will often use packages and modules that don’t come as part of the standard library. Applications will sometimes need a specific version of a library, because the application may require that a particular bug has been fixed or the application may be written using an obsolete version of the library’s interface.

This means it may not be possible for one Python installation to meet the requirements of every application. If application A needs version 1.0 of a particular module but application B needs version 2.0, then the requirements are in conflict and installing either version 1.0 or 2.0 will leave one application unable to run.

The solution for this problem is to create a [virtual environment](https://docs.python.org/3/glossary.html#term-virtual-environment), a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages.

Different applications can then use different virtual environments. To resolve the earlier example of conflicting requirements, application A can have its own virtual environment with version 1.0 installed while application B has another virtual environment with version 2.0. If application B requires a library be upgraded to version 3.0, this will not affect application A’s environment.

### Networks

#### What kind of HTTP status codes do you know?

1xx - general information

2xx - successful request

3xx - redirection

4xx - client error (404 - cannot be found)

5xx - server error

#### What is a API?

Application Programming Interface

#### What is REST API?

**Representational state transfer** (**REST**) is a [software architectural](https://en.wikipedia.org/wiki/Software_architecture) style that defines a set of constraints to be used for creating [Web services](https://en.wikipedia.org/wiki/Web_service). Web services that conform to the REST architectural style, called *RESTful* Web services, provide interoperability between computer systems on the [internet](https://en.wikipedia.org/wiki/Internet). RESTful Web services allow the requesting systems to access and manipulate textual representations of [Web resources](https://en.wikipedia.org/wiki/Web_resource) by using a uniform and predefined set of [stateless](https://en.wikipedia.org/wiki/Stateless_protocol) operations. Other kinds of Web services, such as [SOAP](https://en.wikipedia.org/wiki/SOAP) Web services, expose their own arbitrary sets of operations.[[1\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-1)

"Web resources" were first defined on the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web) as documents or files identified by their [URLs](https://en.wikipedia.org/wiki/URL). However, today they have a much more generic and abstract definition that encompasses every thing, entity, or action that can be identified, named, addressed, handled, or performed, in any way whatsoever, on the Web. In a RESTful Web service, requests made to a resource's [URI](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) will elicit a response with a [payload](https://en.wikipedia.org/wiki/Payload_(computing)) formatted in [HTML](https://en.wikipedia.org/wiki/HTML), [XML](https://en.wikipedia.org/wiki/XML), [JSON](https://en.wikipedia.org/wiki/JSON), or some other format. The response can confirm that some alteration has been made to the resource state, and the response can provide [hypertext](https://en.wikipedia.org/wiki/Hypertext) links to other related resources. When [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) is used, as is most common, the operations ([HTTP methods](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)) available are GET, HEAD, POST, PUT, PATCH, DELETE, CONNECT, OPTIONS and TRACE.[[2\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-rfc_7231-2)

By using a stateless protocol and standard operations, RESTful systems aim for fast performance, reliability, and the ability to grow by reusing components that can be managed and updated without affecting the system as a whole, even while it is running.

The term *representational state transfer* was introduced and defined in 2000 by [Roy Fielding](https://en.wikipedia.org/wiki/Roy_Fielding) in his doctoral dissertation.[[3\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-Fielding-Ch5-3)[[4\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-4) Fielding's dissertation explained the REST principles that were known as the "HTTP object model" beginning in 1994, and were used in designing the [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) 1.1 and [Uniform Resource Identifiers](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) (URI) standards.[[5\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-5)[[6\]](https://en.wikipedia.org/wiki/Representational_state_transfer#cite_note-Fielding-Ch6-6) The term is intended to evoke an image of how a well-designed Web application behaves: it is a network of Web resources (a virtual state-machine) where the user progresses through the application by selecting resource identifiers such as http://www.example.com/articles/21 and resource operations such as GET or POST (application state transitions), resulting in the next resource's representation (the next application state) being transferred to the end user for their use.

#### What is JSON? When to use?

JSON - JavaScript Object Notation. It is an open standard file format, and data interchange format, that uses human-readable text to store and transmit data objects consisting of [attribute–value pairs](https://en.wikipedia.org/wiki/Attribute–value_pair) and [array data types](https://en.wikipedia.org/wiki/Array_data_type) (or any other [serializable](https://en.wikipedia.org/wiki/Serialization) value). It is a very common [data](https://en.wikipedia.org/wiki/Data) format, with a diverse range of applications, such as serving as a replacement for [XML](https://en.wikipedia.org/wiki/XML) in [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) systems.

JSON is a language-independent data format. It was derived from JavaScript, but many modern programming languages include code to generate and parse JSON-format data. 

Example: 

```
{
  "firstName": "John",
  "lastName": "Smith",
  "isAlive": true,
  "age": 27,
  "address": {
    "streetAddress": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postalCode": "10021-3100"
  },
  "phoneNumbers": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "office",
      "number": "646 555-4567"
    }
  ],
  "children": [],
  "spouse": null
}
```

#### What is TCP/IP? What layers does it define, what are they responsible for?

~ is the internet protocol suite. It is the conceptual model and set of communications protocols used in the internet and similar computer networks. It is commonly known as **TCP/IP** because the foundational protocols in the suite are the [Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) (TCP) and the [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol) (IP).

The Internet protocol suite provides [end-to-end data communication](https://en.wikipedia.org/wiki/End-to-end_principle) specifying how data should be packetized, addressed, transmitted, [routed](https://en.wikipedia.org/wiki/Routing), and received. This functionality is organized into four [abstraction layers](https://en.wikipedia.org/wiki/Abstraction_layer), which classify all related protocols according to the scope of networking involved.[[1\]](https://en.wikipedia.org/wiki/Internet_protocol_suite#cite_note-rfc1122-1)[[2\]](https://en.wikipedia.org/wiki/Internet_protocol_suite#cite_note-rfc1123-2) From lowest to highest, the layers are the [link layer](https://en.wikipedia.org/wiki/Link_layer), containing communication methods for data that remains within a single network segment (link); the [internet layer](https://en.wikipedia.org/wiki/Internet_layer), providing [internetworking](https://en.wikipedia.org/wiki/Internetworking) between independent networks; the [transport layer](https://en.wikipedia.org/wiki/Transport_layer), handling host-to-host communication; and the [application layer](https://en.wikipedia.org/wiki/Application_layer), providing process-to-process data exchange for applications.

#### What’s the difference between TCP and UDP?

TCP: Transmission Control Protocol

UDP: User Datagram Protocol

| TCP is a connection-oriented protocol. Connection-orientation means that the communicating devices should establish a connection before transmitting data and should close the connection after transmitting the data. | UDP is the Datagram oriented protocol. This is because there is no overhead for opening a connection, maintaining a connection, and terminating a connection. UDP is efficient for broadcast and multicast type of network transmission. |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| TCP is reliable as it guarantees delivery of data to the destination router. | The delivery of data to the destination cannot be guaranteed in UDP. |
| TCP provides extensive error checking mechanisms. It is because it provides flow control and acknowledgment of data. | UDP has only the basic error checking mechanism using checksums. |
| Sequencing of data is a feature of Transmission Control Protocol (TCP). this means that packets arrive in-order at the receiver. | There is no sequencing of data in UDP. If ordering is required, it has to be managed by the application layer. |
| TCP is comparatively slower than UDP.                        | UDP is faster, simpler and more efficient than TCP.          |
| Retransmission of lost packets is possible in TCP, but not in UDP. | There is no retransmission of lost packets in User Datagram Protocol (UDP). |
| TCP has a (20-80) bytes variable length header.              | UDP has a 8 bytes fixed length header.                       |
| TCP is heavy-weight.                                         | UDP is lightweight.                                          |
|                                                              |                                                              |
| TCP doesn’t supports Broadcasting.                           | UDP supports Broadcasting.                                   |
| TCP is used by HTTP, HTTPs, FTP, SMTP and Telnet.            | UDP is used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP.         |

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

This is an example of an HTTP Request:

```php+HTML
GET /hello.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.tutorialspoint.com
Accept-Language: en-us
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
```

The request-header fields allow the client to pass additional information about the request, and about the client itself, to the server. These fields act as request modifiers. Here is a list of some important Request-header fields that can be used based on the requirement:

- Accept-Charset
- Accept-Encoding
- Accept-Language
- Authorization
- Expect
- From
- Host
- If-Match
- If-Modified-Since
- If-None-Match
- If-Range
- If-Unmodified-Since
- Max-Forwards
- Proxy-Authorization
- Range
- Referer
- TE
- User-Agent

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?

This is an example from the web:

```php+HTML
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
Content-Length: 88
Content-Type: text/html
Connection: Closed
```

The response-header fields allow the server to pass additional information about the response which cannot be placed in the Status- Line. These header fields give information about the server and about further access to the resource identified by the Request-URI.

- Accept-Ranges
- Age
- ETag
- Location
- Proxy-Authenticate
- Retry-After
- Server
- Vary
- WWW-Authenticate

#### What is DNS? How does it work?

Domain Name Server.

The process of DNS resolution involves converting a hostname (e.g. www.index.hu) into a computer-friendly IP address (such as 192.168.1.1). An IP address is given to each device on the internet, and that address is necessary to find the appropriate internet device (like a street address is used to find a particular home).

#### What is a web server?

A ~ is a server software or hardware dedicated to running this software, that can satisfy client requests on the world wide web.  A web server can, in general, contain one or more [websites](https://en.wikipedia.org/wiki/Website). A web server processes incoming [network](https://en.wikipedia.org/wiki/Computer_network) requests over [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) and several other related [protocols](https://en.wikipedia.org/wiki/Communication_protocol).

The primary function of a ~ is to store, process and deliver web pages to clients.

#### Explain the client-server architecture.

**Client Server Architecture** is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection. This system shares computing resources. **Client/server architecture** is also known as a networking computing model or client/server network because all the requests and services are delivered over a network.

#### What would you use a session for?

Session data is stored on the server. The session is the interval at which the client logs on to the server and logs out the server. The data that is required to be saved in the session is stored in a temporary directory on the server.

e.g. if there is a login page (in the flask file), the login data (username, password) has to be stored in a session, and then it can be removed from that session (with another function)

#### What would you use a cookie for?

HTTP **cookies**, or internet **cookies**, are built specifically for Internet **web** browsers to track, personalize, and save information about each user's session. A “session” just refers to the time you spend on a site. **Cookies** are created to identify you when you visit a new **website**.

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?

Waterfall methodology: ~ is viewed as an "old school" method, it is divided into self-contained stages of steps. The stages are relatively rigid and often follow this sequence: determine the project's requirements and scope, analyze the requirements, design, implement, test, deploy and finally maintain.

Agile SDM (software development methodology): Centered round the idea of iterative development, where requirements and solutions evolve through collaboration among self-organizing cross-functional teams. This method values individuals and their relationships and interactions over tools, it responds to change instead of following a set-in-stone plan.

SCRUM methodology: similar to agile SDM, but more structured - it uses an iterative approach in which the team is front and center. Team members break down end goals into smaller goals at the beginning and work through them using fix-length iterations (sprints).

#### What are the SCRUM roles?

Product owner: determines what needs to be done and sets the priorities to deliver the highest value, controls the work

Development team:  the self-organizing group, the team takes on and determines how to deliver chunks of work in frequent increments 

Scrum master: the leader who protects the scrum process and prevents distractions

#### What are the SCRUM ceremonies?

Sprint planning, daily scrum, sprint review and sprint retrospective

#### What are the SCRUM artifacts?

Scrum describes three primary artifacts: 

the Product Backlog (list of tasks), the Sprint Backlog (list of everything that the team commits to achieve in a given sprint), and the Product Increment (the product upon which the team had agreed to complete by the end of the sprint - fully tested and fully approved)

#### What is the main goal of a retrospective meeting?

It is an opportunity for the scrum team to assess its performance and improve itself.

#### Explain, when would you recommend to use the waterfall methodology?

The waterfall methodology is a breakdown of project activities into linear sequential phases, where each phase depends on the deliverables of the previous one and corresponds to a specialization of tasks. 

This method is mainly used in the areas of engineering design (where each phase depends on the previous one). In software development it tends to be among the less flexible approaches.