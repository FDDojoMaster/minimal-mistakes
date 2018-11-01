---
title:  "HTML Lesson 3: Basics 1: HTML Tags (Continued) + Your First Website"
categories:
  - HTML/CSS/JS
  - Basics
  - Lesson
tags:
  - HTML/CSS/JS
  - Introduction
  - Programming
  - Web Development

toc: true

---
# More on HTML tags and building our First Website!

## An Introduction....

In the previous article, we looked at some basic HTML tags and discussed each of their capabilities. In this article, we will look at them in context and introduce some new tags. In order to craft a website successfully,it is of paramount importance to use the correct tags and structure your code in a way that is legible and easy to access. As you may be able to recall, the tags we looked at previously are some of the most common tags that are used in HTML code. In order to strenghten your ability to use these tags, let us put some of them into context. Take a look at the code example below and click "Result" to see the output of the code. To see the code, click "HTML".
<p data-height="512" data-theme-id="0" data-slug-hash="WgRqyK" data-default-tab="result" data-user="FuseDojo" data-pen-title="WgRqyK" class="codepen">See the Pen <a href="https://codepen.io/FuseDojo/pen/WgRqyK/">WgRqyK</a> by DojoMaster (<a href="https://codepen.io/FuseDojo">@FuseDojo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>


# More Tags: UI Elements

Now that we have familiarised ourselves with some basic tags in HTML, let us look at some more. It is not possible to go through every single tag, however w3Schools has a great resource which describes many tags which is great for reference. A lot of developers use this as reference. [Click here](https://www.w3schools.com/tags/){:target="_blank"}. The great thing about HTML is that it has a whole lot of built-in UI (User Interface) elements which makes programming a breeze. The most common UI elements include buttons, Inputs and Option pickers. Inputs are used to obtain information from the user, such as their email address, or their password. Buttons are used to either submit information or navigate somewhere either locally on the site, or externally. Options pickers give you options to pick from a menu which has the choices predefined by you. 

## How to Create Inputs

Let us begin with the Input tag. The input tag is defined like so: <code></input></code>. However we cannot just place an input tag in our code and hope for the best, we must define some parameters first. Take a look at the code example below:

```html
<input id="myInput" type="email"
 placeholder="Enter Email Address">
```

The <b>"id"</b> attribute assigns an id to the input which makes it easier to retrieve and identify when writing more advanced code. The <b>"type"</b> attribute defines the type of input. The <b>"placeholder"</b> attribute defines the prompt text to inform the user of what to enter inside the input field.

The above code will render the following (Try it yourself, and enter your email address into the field:

<input id="myInput" type="email" placeholder="Enter Email Address">

## How to Create Buttons

Another important UI tag that we must cover in HTML is the <code></button></code> tag. As mentioned before, a button has many different uses including navigation or submitting information. To create our button, there are two different ways of creating buttons take a look at the code examples below:

The first way is to use the <code></button></code> tag like so:
```html
<button id="myButton" type="button">My Button </button>
```
The button tag predefines the button as an element. We also declare it's ID and type to ensure that it is a button. We then add a closing tag to close the element.


The second way is to use the  <code></input></code> tag like so:

```html
<input type="button" name="Click Me!" value="Click Me" />
```
The input tag is the tag we used to make text input fields. The "type" attribute is important here as it defines what type of element we are going to make. The "value" and "name" attributes are important as they give the element a name.

Here is a live demo of a button, try it out:

<button id="myButton" type="button">My Button </button>

Here is a styled button:

<button style="background-color:red; border-radius:8px; width:200px; height:70px; border-color: red;" id="myButton" type="button">My Button </button>

Try to create your own buttons and like the example above, in the next lesson, we will look at styling our elements to make them look nice, and appealing.

