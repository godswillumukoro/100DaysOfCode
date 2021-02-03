## DAY 25:

03-02-2021

Continuing  Lecture 7 - SQL

How to Update data 

```sql
UPDATE shows SET genres = "Comedy, Drama, Musical" WHERE title = "The Muppet Show";
```

Deleting data 

```sql
DELETE FROM shows WHERE title LIKE "Friends"
```

### Five Main SQL Datatypes

1. **Blob**: Binary Large objects, which means 0s and 1s can be stored in your database
2. **Integer**: just integers😀
3. **Numeric**: Number-like eg. Year or Time.
4. **Real**: is a float
5. **Text**: is a string

### Primary Key

A column in a table that uniquely identifies every row

### Foreign Key

In another table, you can refer back to the said primary key column by way of that iunique identifier. In this context , its a foreign key.

## Bridging the World of Python and SQL

You can execute SQL commands from your python code. Using the cs50 library, demonstrated below:

```sql
from cs50 import SQL
```

```sql
import csv

from cs50 import SQL

#w - write mode. this line creates the file and closes the file
open("shows.db", "w").close()
db = SQL("sqlite:///shows.db")

db.execute("CREATE TABLE shows (id INTEGER, title TEXT, PRIMARY KEY(id))")
db.execute("CREATE TABLE genres (show_id INTEGER, genre TEXT, FOREIGN KEY(show_id) REFERENCES shows(id))")

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        title = row["title"].strip().upper()
        id = db.execute("INSERT INTO shows (title) VALUES(?)", title)

        for genre in row["genres"].split(", "):
            db.execute("INSERT INTO genres (show_id, genre) VALUES(?, ?)", id, genre)
```

# Started Lecture 8 - HTML, CSS, Javascript

## What is the Internet?

The Network of networks. The network of all the computers around the world that are taking information from the network and also giving it information.

This is the infrastructure on top of which all of today's application are run. Eg. when using the web, an app, chat, zoom are all using the internet. Think of the internet as the lower level plumbing that gets all the 0s and 1s from you to someone else and back. And all the applications on top of that are all implemented in software.

### Routers

Like computers we know, contains CPU and RAM and Hard Disks too. They relay your data in order to get data from you to the web server you are trying to contact, and then back to you in form of a response.

But how does all of these work?

We need protocols to get/receive data over the network.

### TCP/IP

Two of the most commonly used protocols to get and receive data from point A to point B are called TCP/IP

**TCP - Transmission Control Protocol**

**IP - Internet Protocol**

Imagine an envelop **** with a delivery address and the sender address.

The envelop and the message therein are typically thought of as **packets.** 0r packets of information.

### IP - INTERNET PROTOCOL

Pretty much any device today eg. Mac, PC, Android, iPhone devices have been designed to understand IP, their creators have written software running on those devices that make sure all those devices support IP.

IP simply standardises how computers address each other. Just like a unique postal address you include in your letter before sending to the postal service to ensure the letter makes its way to that particular address.

Computers also have unique addresses known as  **IP address**. So when your computer sends data from itself to another server, the address that it writes on the outside of that virtual envelop is the **IP address of the remote server**.

The computer then hands that letter to the nearest router which will act as a postal services and help get the letter to its destination.

but how can I know your IP address when I do not know your location?

### DNS - Domain Name System

A technology, deployed through out the internet,  supported by Mac, PC, phones etc. that translates domain names from human readable characters to IP addresses.

DNS is a service that your ISP (Internet Service Provider) provides.

### TCP - Transmission Control Protocol

A solution to a couple of problems, one of which, the numbering of services, know as **port numbers** which represents specific services. eg.

80 HTTP

443 HTTPS

TCP also handles delivery, if any data gets lost going from point A to point B. TCP would compel you computer to resends the lost data.

Data does not follow on specific route, TCP/IP and other protocols support an adaptive solution to this problem.

Let us now abstract the internet away and think of is as a mechanism that gets data from one point to another. Assume that we have this fundamental public service that gets data from one point to another, we can now start to build on top of it in terms of software and other languages and use it for interesting things.

### HTTP - Hyper Text Transfer Protocol

The WWW. - World Wide Web is just one of the many services that run on top of the internet. Its one of the most popular service or application using the underlying plumbing (internet).

While TCP/IP governs what goes on outside the envelop, **HTTP governs what goes on inside the envelop.**

HTTP commands with a few different commands, including:

GET: How a browser requests/gets information from a server, can be seen on the browser's address bar.

POST: Same with GET, but more secured, in the sense that it can't be seen on the address bar.

# Started Lecture 9 - Flask

## FLASK

The library called Flask is a python framework. A framework is a way of doing things, a way of organising your code, writing your code, more specifically how you should use this library.

## The Design Pattern

Flask implements whats known as the MVC design pattern.

![Screenshot of MVP model](./images/01.png)

**MODEL: The database**

**VIEW: What the user sees**

**CONTROLLER: The logic code**
