---
title: How to Build a Custom Contact Form and Submit Real Data
date: 2018-10-23 00:00:00 Z
categories:
- HTML/CSS/JS
- Project
- Forms
- API
- Server Projects
tags:
- HTML/CSS/JS
- Project
- Forms
- Validation
- API
- Programming
- Web Development
toc: true
---

## Learn how to make a custom contact form using the Formspree API.

In this project, we are going to be making our very own custom contact form which handles data submitted in the form and sends an email to the administrator with the details entered in the form using the formspree API. The formspree api is an open-source service which handles form data and sends an email to you, the creator of the form with the data inputted into your form by a user over a secure protocol. We are going to be using some new frameworks such as <b>npm</b> to create our server and <b>bootstrap</b> to craft the UI of the form.

### What is npm? 
<br>
<img src="/assets/img/npm.png" style="width:90px;">
<br>

npm is a package manager for javascript which allows you to install loads of javascript libraries that perform particular functions with the code already written for them instead of you coding them, hence allowing you to focus on the more important parts of your code. [Link to the npm website for more info.](https://npmjs.com){:target="_blank"} We will be using npm to create our server for the form we are going to create. The reason we need a server for this form is because the data we are submitting is through a dynamic html file/site not a static website.

### What is Bootstrap?
<br>
<img src="/assets/img/bootstrap-stack.png" style="width:90px;">
<br>

Bootstrap is an external UI (User Interface) kit which provides many styled html elements without the need of writing extra CSS code. Instead you just declare the style in your html code with one line of code encapsulated in the "class" attribute of your element. [Click here to see more, and refer to the documentation of Bootstrap](https://getbootstrap.com){:target="_blank"}

## Building the Server

To get started with this project, we need to initalise our server in which the form is going to function in. Download node.js [here](https://nodejs.org/en/download){:target="_blank"}. This will automatically install npm for you. To check that you have npm installed correctly, type <code> npm </code> into your terminal and you should get an output like:


```console
Usage: npm <command>

where <command> is one of:
    access, adduser, audit, bin, bugs, c, cache, ci, cit,
    completion, config, create, ddp, dedupe, deprecate,
    dist-tag, docs, doctor, edit, explore, get, help,
    help-search, hook, i, init, install, install-test, it, link,
    list, ln, login, logout, ls, outdated, owner, pack, ping,
    prefix, profile, prune, publish, rb, rebuild, repo, restart,
    root, run, run-script, s, se, search, set, shrinkwrap, star,
    stars, start, stop, t, team, test, token, tst, un,
    uninstall, unpublish, unstar, up, update, v, version, view,
    whoami

npm <command> -h  quick help on <command>
npm -l            display full usage info
npm help <term>   search for help on <term>
npm help npm      involved overview

```
The next step is to intialise a project in your preffered directory. My recommendation is to create a file on the desktop. (Make sure you cd to your project directory before typing in the commands below). Type in the code below: 

```console
DojoMasters-MBP:formproject dojomaster$ npm init
```
Then, follow the wizard that follows. Just hit enter for all of the fields and confirm the project. and a <code>package.json</code> file is created in the root of your project folder. It should look like this:

```json
{
  "name": "formspreetutorial",
  "version": "1.0.0",
  "description": "A tutorial which shows how to submit form data from a custom form using the formspree API",
  "main": "index.js",
  "directories": {
    "test": "test"
  },
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  "author": "YOUR_NAME_HERE",
  "license": "ISC",
  "dependencies": {
    "connect": "^3.6.6",
    "serve-static": "^1.13.2"
  }
}
```

This file is the configuration file for our project in which we define some parameters such as the script that is run when we start the server and other self-explanatory information. 

Install the packages <code>connect and serve-static </code> which allow html files to be served over an http server:

```console
npm i connect
npm i serve-static
```


The next step is to add some javascript code to initalise our server on a dedicated server locally on our machine. Create a file and name it <code>server.js</code>. Then, add the following code:

```javascript
var connect = require('connect');
var serveStatic = require('serve-static');
connect().use(serveStatic(__dirname)).listen(8080, function(){
    console.log('Server running on 8080...');
});
```

Essentially, this code initialises our server and tells it that an HTML file will be served over this server on the local url: <code>http://localhost:8080</code>. 

To run the server run this command:

```console
npm start 
```
Then browse over to <code>http://localhost:8080</code> and a blank page should appear, showing that the server is running.

## Building the Form UI

Now that we have created our server, we can begin to create our form. We will start with the basic html skeleton template from bootstrap which includes links to the CSS and JS files required for bootstrap to work.

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <title>Custom Form Tutorial</title>
  </head>
  <body>
    <center><h1>Custom Form Tutorial</h1></center>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
  </body>
</html>
```
Now, we need to create our UI elements including 3 input fields for name, email and a
larger text field respectivley.




```html
 <div class="container">
    <div class="row">
           <div class="col">
                <form>
                    <div class="form-group">
                        <label for="nameInput">Name</label>
                        <input type="name" class="form-control" id="nameInput" aria-describedby="name" placeholder="Enter Name" name="Name" onchange="validation();">
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" class="form-control" id="emailInput" placeholder="Email" name="Email" onchange="validation();" >
                    </div>
                    <div class="form-group">
                        <label for="message">Your Message</label>
                        <textarea class="form-control" id="message" rows="4" name="Message" onchange="validation();"></textarea>
                    </div>
                    
                    <input type="submit" class="btn btn-outline-primary btn-block" id="submitBtn">                    
                </form>
            </div>   
        </div>
    </div>
```

So far, we have created our text fields and our submit button and you should get something like this:

<img src="/assets/img/formscreenshot.png" style="width=90px;">

## Connecting the form to Formspree


Now, we need to connect the data that our user submits in the form to Formspree which is our form provider. Head over to formspree.io and take a look at the documentation. Then, add this line of code to the top <code> <form> </code> tag:


```html
method="POST" action="https://formspree.io/dojomaster@fusedojo.com"
```
so that it becomes:

```html
<form method="POST" action="https://formspree.io/YOUR_EMAIL@example.com">
```
What the line above does, is that it takes the form data from the user and will send it to the admin's email address. So append your email address to the formspree url above.

## Adding Form Validation

Next, to make our form even more realistic, we will add some form validation. This means that the form will check for any blank spaces or incorrect email formatting and will not allow the user to submit if they haven't met the requirements. The submit button will be disbaled at default until the user fills in all of the required fields. To do this, we will add some javascript code which will be encapsulated directly into the html document using the <code> </script> </code> tags:

```javascript
function validation() {

  var name = document.getElementById('nameInput').value;
  var email = document.getElementById('emailInput').value;
  var message = document.getElementById('message').value;
  var submitBtn = document.getElementById('submitBtn');
            
    if(name === "" || email === "" || message === "") {
      document.getElementById('submitBtn').disabled = true;
            } else {
                submitBtn.disabled = false;
            }    
        }
      validation();
            
```

Above, we declare a function called <code>validation()</code>  and create some variables which take the data from the html form inputs and stores them as a variable. An if statement is called which checks if the inputs are empty. If they are, then the button becomes disabled. If they are all full, and they are in the correct format, then the button is enabled and the user can submit the form. 

Ensure the <code> onchange="validation();" </code> attribute is included in each of the text input tags to ensure that the if statment runs when the user actually enters some text into the text-field. If this is not included in your code, then the if statement will run when the form is reloaded and will not allow the user to submit the form. The <code>onchange</code> attribute detects a change in the user input box, and excecutes the function which we declared.

After doing this, go to <code> http://localhost:8080 </code> and try and submit your form. Remember, on the first submit you will be asked to confirm your email address by formspree.

## Conclusion

If you have been able to follow the steps above succesfully, you should be able to fill in your form and recieve an email from formspree shortly giving you the details of the information inputted onto the form. If not, you can find the full source code on [github here](https://github.com/FDDojoMaster/FormspreeTutorial/tree/master){:target="_blank"}.