# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
- queries should be written in multiple lines (more readable)
- SELECT ... AS or ALIAS (naming convention)
- customized case-use (e.g. verbs with uppercase, table-names with lowercase)
- not to forget the ; at the end of the query
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
That means if there are some semantic errors - not enough letters in a password, not the right format, 
if a password is used already it is good to alert the user about them. 

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

hashed and salted, and in a database on the computer which cannot be read by others

#### What is HTTPS?

HTTPS: Hypertext Transfer Protocol Secure

#### What is encryption and decryption?

Encryption: ~ is a process which transforms the original information into an unrecognizable form.

Decryption: ~ is a process of converting encoded/encrypted data in a form that is readable and understood by a human or a computer.

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

SELECT * FROM address WHERE city = 'Miskolc';

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

enable Change Tracking: 

ALTER DATABASE AdventureWorks2012   SET CHANGE_TRACKING = ON   (CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  



or by the git history

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