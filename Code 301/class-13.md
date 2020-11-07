# Read: 13 - Update/Delete

## Sending Form Data

Source: https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data

Client/server architecture
At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server, using the HTTP protocol. The server answers the request using the same protocol.

> Common servers used for HTTP request:
> - Apache
> - Nginx
> - IIS
> - Tomcat


## On the client side: defining how to send the data

-  `<form>` element defines how the data will be sent.
- `action` attribute defines where the data gets sent.
> Its value must be a valid relative or absolute URL. If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page.

Example Absolute URL:
```
<form action="https://example.com">
```

Example Relative URL:
```
<form action="/somewhere_else">
```

When specified with no attributes, as below, the <form> data is sent to the same page that the form is present on:

```
<form>
```

## The method attribute

- `method` attribute defines how data is sent. 

- Form data can be transmitted via a number of different methods, the most common being the `GET` and `POST` method.

- `GET` method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource.

-  `POST` method is the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." 

> HTTP requests are never displayed to the user (if you want to see them, you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools). As an example, your form data will be shown as follows in the Chrome Network tab. After submitting the form:
>
> - Open the developer tools.
> - Select "Network"
> - Select "All"
> - Select "foo.com" in the "Name" tab
> - Select "Headers"

## On the server side: retrieving the data

- Global PHP objects (`POST`)

```
<?php
  // The global $_POST variable allows you to access the data sent with the POST method by name
  // To access the data sent with the GET method, you can use $_GET
  $say = htmlspecialchars($_POST['say']);
  $to  = htmlspecialchars($_POST['to']);

  echo  $say, ' ', $to;
?>
```

> method of `POST` and an action of `./route`.


```
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
    ```

