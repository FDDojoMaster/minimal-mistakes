---
title: 'Lesson 1: Getting Started with HTML, CSS and Javascript'
date: 2018-08-12 00:00:00 Z
categories:
- HTML/CSS/JS
- Basics
- Lesson
tags:
- HTML/CSS/JS
- Introduction
- Programming
- Web Development
search: true
toc: true
---

# What is HTML?

## An Introduction into HTML

In this post, we will dicuss briefly what HTML, CSS and Javascript are. In short, HTML is the language of the web and is used to create websites like this one. HTML is a programming language but takes its form in tags that are used to define various elements such as buttons, text input fields and labels. Alongside this, we can use CSS which abbreviates to Cascading Style Sheets in order to style our web pages. By “styling” we mean adding colour and resizing elements to make them look nice. The final piece of the puzzle is Javascript. This is the brains of your site which makes your site dynamic and interactive. With Javascript you can create a myriad of different apps using it’s easy to pick up syntax.

## HTML Code

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Page Title</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" type="text/css" media="screen" href="main.css" />
    <script src="main.js"></script>
</head>
<body>
    
</body>
</html>
```

Above, you can see the basic template for an HTML page. As you can see, the code works by using a series of tags which define certain elements. For example, the <code> </html> </code> tag defines the root of the document and the <code> </head> </code> tag defines the top of the page where the title of the document and the configuration scripts are placed. The <code> </body> </code> tag is where the main page content goes forming the "body" of the page. These main tags follow what is called the Document Object Model, also known as the DOM. Take a look at Fig 1.0 to see how the DOM structure works. 


![DOM-Tree](/assets/img/diagrams/domtree.png/ "DOM Tree")
Fig 1.0

As you can see in Fig 1.0 above, the Document Object Model occupies a hierarchical structure with the <code> </html> </code> tag being the root of the document and the <code> </head> </code> and <code> </body> </code> tags following on. At the bottom of the tree, we have low level components such as the <code> </title> </code>,<code> </h1> (header) </code>, <code> </p> (paragraph) </code> and <code> </button> </code> tags. We will look at these tags more in detail later on in the course, this serves as a small introduction into HTML programming.


# CSS

## An Introduction into CSS


Now, let us look at CSS. CSS, which is also known as Cascading style sheets is a language that uses pre-defined parameters in order to style HTML elements in a document. They can add various stylings such as colour, sizing and positioning. We will dicuss these more in detail in future lessons. The structure of the code is block-like where the element you want to style is written and then followed by the parameters that you want to style. Take a look at the code example below:

## CSS Code

```css
.box {
    background-color: red;
    padding: 12 14px;
    margin-left: 20px;
    font-size: 10;
    font-family: 'Courier New', Courier, monospace;
}
```

The <code> .box </code> line defines a class which is present in the HTML document. This is what we want to style. The parameters are held in a pair of curly braces. Many of the parameters are low level meaning that they are self-explanatory such as the background colour and the <code>font-size</code> and <code>font-family</code>. The <code>padding</code> parameter defines the space around the element. The <code>margin</code> parameter defines the spacing between (in this case) the left side of the page and the element. 


# Javascript

## An Introduction into JS

The third and final piece of the puzzle in web development is Javascript. Javascript is the brains of your website and is the place where the main logic of the website takes place. It is a versatile language that can easily be integrated with HTML and CSS. Javascript gives your website or web app the capability to think for itself and process user interactions on the site. Take a look at the code example below:

## JS Code




```html
<!DOCTYPE html>
<html>
<head>
<button onclick="click();"> Click Me! </button>
<script>
  function click() {
    alert("Hello World!");
  }
</script>
</head>
<body>
</body>
</html>
```
As you can see in the code example above, Javascript can be easily embedded into an HTML page using <code> </script> </code> tags. A function called "click" is defined which will cause an alert to pop up on the screen displaying "Hello World". An HTML button is created in which when the button is clicked, will execute the function. The <code>onclick</code> element tells the code to display the alert when the button is clicked.

# Finally....

Do not worry at all if you do not understand the examples above as we have not actually looked at the languages in detail. This is just here to give you a flavour of the sorts of code that we will be working with in our projects. In the next post, we will dive into the HTML language, looking at the file structure and the DOM (Document Object Model).