no_dollar
=========

Example of AJAX request without using JQuery, hence the name "no dollar"

Things to define:



XMLHttpRequest()
this is obviously a function. It's also an object constructor, based on how it's used:
xmlObj = new XMLHttpRequest()

loadXMLDoc()
another function.

onreadystatechange = function()
is a function called on an XMLHttpRequest object. Which is what again?

.readyState == 4
function called on our xmlObj declared earlier

.status == 200

.getElementById

.responseText
function also called on xmlObj

xml.open
xml.send

