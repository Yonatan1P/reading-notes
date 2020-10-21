# Read: 13 - Update/Delete

## Client/server architecture

a client (usually a web browser) sends a request to a server
The server answers the request using the same protocol.

## On the client side: defining how to send the data

The action attribute:  defines where the data gets sent.
<form action="https://example.com">
When specified with no attributes, as below, the <form> data is sent to the same page that the form is present on

The method attribute: defines how data is sent. 
The GET method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource."
'<form action="http://www.foo.com" method="GET">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>'

The POST method:. It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." 
'<form action="http://www.foo.com" method="POST">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>'

The Content-Length header indicates the size of the body,
Content-Type header indicates the type of resource sent to the server.

## On the server side: retrieving the data

Example: Raw PHP
'<?php
  // The global $_POST variable allows you to access the data sent with the POST method by name
  // To access the data sent with the GET method, you can use $_GET
  $say = htmlspecialchars($_POST['say']);
  $to  = htmlspecialchars($_POST['to']);

  echo  $say, ' ', $to;
?>'
Example: Python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/', methods=['GET', 'POST'])
def form():
    return render_template('form.html')

@app.route('/hello', methods=['GET', 'POST'])
def hello():
    return render_template('greeting.html', say=request.form['say'], to=request.form['to'])

if __name__ == "__main__":
    app.run()
    
 ## A special case: sending files
 The enctype attribute
 Set the method attribute to POST because file content can't be put inside URL parameters.
Set the value of enctype to multipart/form-data because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).
Include one or more <input type="file"> controls to allow your users to select the file(s) that will be uploaded.

<form method="post" action="https://www.foo.com" enctype="multipart/form-data">
  <div>
    <label for="file">Choose a file</label>
    <input type="file" id="file" name="myFile">
  </div>
  <div>
    <button>Send the file</button>
  </div>
</form>

## Security issues

Be paranoid: Never trust your users
Escape potentially dangerous characters. The specific characters you should be cautious with vary depending on the context in which the data is used and the server platform you employ, but all server-side languages have functions for this. Things to watch out for are character sequences that look like executable code (such as JavaScript or SQL commands).
Limit the incoming amount of data to allow only what's necessary.
Sandbox uploaded files. Store them on a different server and allow access to the file only through a different subdomain or even better through a completely different domain.
