# Flask_Study_Materials


## Python Flask Framework
- Flask is a popular Python framework for developing web applications. It comes with minimal built-in functionalities and requirements, making it simple to get started and flexible to use. The developer has the liberty to customize most aspects of the app, including database integration, accounts and authentication, and more.

## Creating Flask App Object
- The Python flask module contains all the classes and functions needed for building a Flask app. The Flask class can be imported to create the main application object. It takes the name of the app as an argument.
  
  Import Flask class
  from flask import Flask
  Create Flask object
  app = Flask(__name__)


## Running Flask App
- A Flask app can be run by exporting the FLASK_APP environment variable and running flask run in the terminal.

 " $ export FLASK_APP=app.py
   $ flask run "

## Creating a Route
- Routes in a Flask app can be created by defining a view function and associating a URL with it using the route() decorator. Routes specify how the Flask app handles requests it receives, such as what to display on the webpage at a certain URL.

  @app.route('/')
  def hello_world():
    return 'Hello, World!'
  Output: The text `Hello, World!` is displayed at the URL path '/'

## Returning HTML From Route
- In a Flask app, HTML can be returned from a view function to be rendered on a webpage. The HTML can be returned as a string.

  @app.route('/')
  def hello_world():
    return '<h1>Hello, World!</h1>'
  Output: The text `Hello, World!` is displayed as a level 1 heading at the URL path '/'

## Variable Rules
- Variable rules allow a Flask app to respond to dynamic URLs. Variable sections of a URL can be indicated by angular brackets and an optional converter: <converter:variable_name>. These variable parts will then be passed to the view function as arguments.

  Responds to `/page/1`, `/page/20`, etc.
  @app.route('/page/<int:pg_num>')
  def content(pg_num):
    return f'<h1>Displaying results for page {pg_num}</h1>'

## app = Flask(__name__)
- When creating a Flask object, we need to pass in the name of the application. In this case, because we are working with a single module, we can use the special Python variable, __name__.
- The value of __name__ depends on how the Python script is executed. If we run a Python script directly, such as with python app.py in the terminal, then __name__ is equal to the string '__main__'. On the other hand, if the script is being imported as a module into another Python script, then __name__ would be equal to its filename.
- this distinction can be useful when we have code that we want to be run only if the script is executed a particular way.

## Routing
- Each time we visit a URL in a browser, it makes a request to the web server, which processes the request and returns a response back to the browser. In our Flask app, we can create endpoints to handle the various requests. Requests from different URLs can be directed to different endpoints in a process called routing.
- To build a route, we need to first define a function, known as a view function, that contains the code for processing the request and generating a response. The response could be something as simple as a string of text. Then, we can use the route() decorator to bind a URL to the view function such that the function will be triggered when the URL is visited:
