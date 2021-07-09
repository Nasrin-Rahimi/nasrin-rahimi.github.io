---
layout: post
title:      "What Is DOM"
date:       2021-07-09 08:26:55 -0400
permalink:  what-is-dom
---

One definition is: The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

Let's view an html document in the browser(chrome is the best)
    
    open index.html  

To see the HTML code of a page, add view-source: in the front of the URL.

    view-source:https://www.google.com/

The browser reads the HTML, along with CSS and JavaScript defined in <script> or <link> tags, to create the DOM inside the browser. At this point, nothing is displayed on the screen. The browser then uses the DOM object to create the rendered page. 

To see DOM, open dev tools in Chrome and click on Elements tab (cmd + shift + c on Mac)

Wait a minute, what you see as a DOM is like to the HTML you see with view-source! Are they the same? Not Really. The HTML is parsed by the browser and turned into the DOM.

When is the DOM different than the HTML?
One possibility is: there are mistakes in your HTML and the browser has fixed them for you. For example if you have a <table> element in your HTML and leave out the required <tbody> element. The browser will just insert that <tbody> for you. It will be there in the DOM, so you’ll be able to find it with JavaScript and style it with CSS, even though it’s not in your HTML.

To read more about DOM:
    
   https://css-tricks.com/dom/

Thanks for reading!



