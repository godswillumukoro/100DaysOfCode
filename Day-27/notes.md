## DAY 27:

05-02-2020

### How a Flask Application is Organized

The Flask framework exists to simply a lot of tasks that wold simply get boring pretty quickly.

The basic flask application would look like this:

```sql
application.py
requirements.txt
static/
templates/
```

Flask follows a certain design pattern called, Model View Controller or MVC.

This simply refers to the approach we would be using when building web applications with Flask.

### A Simple Flask Application

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
    return render_template("index.html", name=request.args.get("name", "world"))
```

### Handling Requests:

The Controller: 

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
    return render_template("index.html")

@app.route("/greet")
def greet():
    return render_template("greet.html", name=request.args.get("name", "world"))
```

The View for index: 

```html
<?DOCTYPE html>

<html lang="en">
    <head>
        <title>hello</title>
    </head>
    <body>
        <form action="/greet" method="get">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <input type="submit">
        </form>
    </body>
</html>
```

The View for greet: 

```html
<?DOCTYPE html>

<html lang="en">
    <head>
        <title>hello</title>
    </head>
    <body>
        hello, {{ name }}
    </body>
</html>
```

### GET is Invase

using get in our code thus far has leaked some data inside the address bar, so lets use a more secure form, POST.

### POST

Using POST in the Controller

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
    return render_template("index.html")

@app.route("/greet", methods=["POST"])
def greet():
    return render_template("greet.html", name=request.form.get("name", "world"))
```

Also changing to POST in the view 

```html
<?DOCTYPE html>

<html lang="en">
    <head>
        <title>hello</title>
    </head>
    <body>
        <form action="/greet" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <input type="submit">
        </form>
    </body>
</html>
```

### Generating Dynamic Pages

There exist many redundancy in our Views. Lets factor out that many commonalities and start creating Dynamic Pages. 

**First we create a layout.html page in out templates folder**

```html
<?DOCTYPE html>

<html lang="en">
    <head>
        <title>hello</title>
    </head>
    <body>
        {% block body %}{% endblock %}
    </body>
</html>
```

**Next, we extend the layout page into our View Pages so it looks like these:**

index:

```html
{% extends "layout.html" %}

{% block body %}
    <form action="/greet" method="post">
        <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
        <input type="submit">
    </form>
{% endblock %}
```

greet: 

```html
{% extends "layout.html" %}

{% block body %}

        hello, {{ name }}

{% endblock %}
```
