# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!

SELECT * FROM tablename

WHERE id = 1

GROUP BY name

ORDER BY name ASC

- the order of the verbs

- "ORDER BY" id where it is possible

#### What layers can you name in a simple web application?

Three layer model: Presentation layer, Business layer, Data layer

### Error handling
#### What error can occur, when an array does not have an element on the requested index?



#### What is the “finally” block, and how would you use it?
#### Why should we catch special exception types?

First of all, in order to make the website user friendly. That means if there are some semantic errors - not enough letters in a password, not the right format, if a password is used already it is good to know about it. 

### Security
#### What is SQL injection? How to protect an application against it?

hashing the password

#### What is XSS? How to protect an application against it?

Cross-site scripting is a type of security vulnerability typically found in web applications.

#### How to properly store passwords?

hashed and salted, and in a database on the computer which cannot be reached by others

#### What is HTTPS?

HTTPS: Hypertext Transfer Protocol Secure

#### What is encryption and decryption?
#### What is hashing?
#### What is the difference between encryption and hashing? When would you use which?
#### What encryption methods do you know?
#### What hashing methods do you know?
#### How/where would you store sensitive data (like db password, API key, ...) of your application?

session, where it is stored only for a period of time

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
#### What is BubbleSort? Describe the main logic of this sorting algorithm.

https://www.w3resource.com/javascript-exercises/javascript-function-exercise-24.php

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





#### Explain the process of calculating the average value in an array of numbers!

#### What is Big O complexity? Explain time and space complexity!
#### Explain the process of calculating the average value in a list of numbers!

add up the values of the numbers, then divide the number with the length of the list

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
#### How to achieve a switch-case-like structure in Python?
#### Explain variable scoping in Python!
#### What’s the difference between const and var in JavaScript?

var

len

const

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

from ... import ...

#### How to import a function from another module in JavaScript?

dom.js

export let dom = {};

boards.js

```js 
import {dom} from "./dom.js";
```

### Functional
#### What is recursion?
#### Write a recursive function which calculates the Fibonacci numbers!
#### How to store a function in a variable in Python?
#### List the ways of defining a callable logical unit in JavaScript!
#### What is an event listener? How to attach one?
#### How to trigger an event in JavaScript?
#### What is a callback function? Tell some examples of its usage.
#### What is a Python decorator? How does it work? Tell some examples of its usage.

decorator is a function within a function

@app.route("/")

#### What is the difference between synchronous and asynchronous execution?

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?

postgresql

#### When do you use the DISTINCT keyword in SQL?

if I want to return (SELECT) different items in a database

#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?

WHERE is a filter, with which I can give a condition to a query

GROUP BY 

HAVING is a filter/condition

ORDER BY is can order the query results by a number 

#### What are aggregate functions in SQL? Give 3 examples.

COUNT, SUM, AVG, MAX or MIN

#### What kind of JOIN types do you know in SQL? Could you give examples?

[
SQL Joins - W3Schoolswww.w3schools.com › sql › sql_join](https://www.w3schools.com/sql/sql_join.asp)LEFT or RIGHT JOIN, FULL JOIN, INNER JOIN

#### What are the constraints in sql?
#### What is a cursor in SQL? Why would you use one?

a QUERY in SQL through python, to fetch data from a database table

#### What are database indexes? When to use?

primary key, foreign key

#### What are database transactions? When to use?

BEGIN TRANSACTION, SET TRANSACTION, COMMIT, ROLLBACK, SAVEPOINT, RELEASE SAVEPOINT 

#### What kind of database relations do you know? How to define them?

one-to-one,

one-to-many,

many-to-many

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

SELECT * FROM address WHERE city = 'Miskolc'

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

enable Change Tracking: 

ALTER DATABASE AdventureWorks2012   SET CHANGE_TRACKING = ON   (CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  



or by the git history

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?

XML

XHTML

HTML

#### How to include a JavaScript file in a webpage?

<script src="app.js"></script>

#### How to include a CSS file in a webpage?

<link rel="stylesheet" href="css/style.css">

#### How to select an element using its id in CSS?

with a (#)

e.g.

#itemName { align: center; }

#### How to select elements using their class in CSS?
with a (.)

e.g.

.className { color: blue; }

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

#### How to select all list items in all ordered lists on the page in CSS?
#### How to select elements using their attributes in CSS?
#### What are UX and UI?
#### Please list some points that an application should fulfill to have good UX.
#### What is XML, XSLT, DTD?
#### What is the difference between HTML and XML?

### Javascript

#### What is javascript?

~ is a programming language, that conforms to the ECMAScript specification.

It is high-level, often just-in-time compiled, and multiparadigm.

It is used for websites' client-side page behavior

#### When to use AJAX? Bring examples of its usage.

If you do not want to load the whole page when a button is pushed or a request is sent from another page

#### What is DOM and how to manipulate it from Javascript?

Document Object Model - JS can change its elements, attributes and styles;

JS also can add create, remove these elements, and JS can react to all existing HTML events on a page

#### What are events and how/why to use them in Javascript?
#### What is event bubbling/capturing? How would you use it?

Callback hell

#### What is JSON and how do we use it?

## Software engineering

### Version control

#### What type of branching strategy would you use?

branching by tasks, features

e.g.

if there is a webpage, and we have to build a login page and a user page there would be 2 different branches for the two.

#### What would you do if you find a bug on the production code (master branch)?
#### How can you move changes from one branch to another in GIT?

merge them 

#### How does a VCS help with code reviews?



#### What is your favorite git command? Why?

git push

#### What does remote/local mean in Git? 

### DevOps

#### Why is it good to use a package manager software?
#### Why is it good to use a virtual environment for a project?

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
#### What is JSON? When to use?
#### What is TCP/IP? What layers does it define, what are they responsible for?
#### What’s the difference between TCP and UDP?
#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

Methods: HEAD, GET, POST, PUT, DELETE, TRACE, OPTIONS, CONNECT

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
#### What is DNS? How does it work?

Domain Name Server

#### What is a web server?
#### Explain the client-server architecture.
#### What would you use a session for?

log in page

#### What would you use a cookie for?

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
#### What are the SCRUM roles?
#### What are the SCRUM ceremonies?
#### What are the SCRUM artifacts?
#### What is the main goal of a retrospective meeting?
#### Explain, when would you recommend to use the waterfall methodology?
