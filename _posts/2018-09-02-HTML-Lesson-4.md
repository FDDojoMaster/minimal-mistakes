---
title: 'HTML Lesson 4: Styling elements using basic CSS.'
date: 2018-09-02 00:00:00 Z
categories:
- HTML/CSS/JS
- Basics
- Lesson
- CSS
- Styling
tags:
- HTML/CSS/JS
- Introduction
- Programming
- Web Development
- CSS
- Styling
toc: true
---

# Using CSS to style HTML Elements

In the previous lessons, we looked at more HTML elements, especially the UI elements. However, the default elements look very bland and boring. Using CSS, we are able to add custom sizing, and colours to make them look nice and appealing. There are three different ways of adding styles to an element using CSS and we will look at all of them in this article.

## Method 1- External Files

When you create an HTML document inside your custom directory (or folder) you can create a free-standing CSS file in the <b>same</b> directory. In order to connect the two files together, to have the CSS code take effect on the HTML file, you must reference the CSS file inside the HTML file like so:

```html
<link rel="stylesheet" type="text/css" href="style.css">
```

As you can see in the code example above, we use the <code></link></code> tag. The <b> "rel" </b> attribute defines what the purpose of this file is which is "stylesheet" which is pretty self-explanatory (styles the elements). The next attribute, which is familiar (also seen in inputs) defines the file type which is CSS. The final attribute which is "href" (also seen in links) defines the name/directory that the file is in, so that when the HTML file is compiled, it can locate the CSS file and apply the CSS styling to the HTML file. <b> Remember! </b> In order for the CSS file to work with your HTML document, they must be in the correct directory together, and if the file is within another file, make use of <b>"/"</b> in order to navigate through the files. We will look at this more in detail in future lessons.


## Method 2- Using the <code></style></code> tag

Alongside external files, which on a large scale can become messy, HTML has the capability to integrate CSS files in the same document with the use of the <code></style></code> tag. Take a look at the code example below, to see how to style a button using CSS:

```html
<button type="button" id="myButton">My Button </button>
<style>
#myButton {
    background-color:red; 
    border-radius:8px;   /* Radius of the border of the button which determines how round the button's edges are are.*/
    width:200px;
    height:70px;
    border-color: red;
}
</style>
```

As you can see above, we use the same syntax as we use in a normal standalone CSS file, but just encased in the style tags inside an HTML document. The first line defines the id of the element that we are styling which is "myButton". THe "#" symbol is appended to the start of the id name to show that we are dealing with an ID. We will deal with styling with class identifiers later on in the course. We then use 2 curly braces in order to add styles to the button. Also, it is essential to remember that the use of ";" (semicolon) after each line is important to indicate the closing of each line. If these semicolons are not added to the end of the lines of code, it will not render properly and will damage your code. Here is a live demo of the button that will be rendered using the above code. 

<button type="button" id="myButton">My Button </button>
<style>
#myButton {
    background-color:red; 
    border-radius:8px; 
    width:200px;
    height:70px;
    border-color: red;
}

</style>

## Method 3- CSS code within the element tag

The final method to integrate CSS code to style HTML elements is the inline method in which CSS code is added to the element tag directly. Please note, that this method should only be used to style small elements on a small scale without the need of creating a CSS file or using <code></style></code> tags. Take a look at the code example below to see it in context. Let us take the button example into account again:


```html
<button style=" background-color:red; border-radius:8px;
 width:200px; height:70px; border-color: red;" 
 type="button" id="myButton">My Button </button>
```

As you can see above, we use the "style" attribute with quotation marks to add the CSS code in the same format as above within the tag.

# Conclusion

In this lesson, we looked at some basic CSS styling and some basic CSS syntax. As you can see, the fact that this language is low-level, means that the syntax we use in CSS is understandable and self-explanatory unlike languages such as C, C++ and Java. In the next lesson, we will look more at HTML coding and integrating more CSS and even some Javascript into our pages.



