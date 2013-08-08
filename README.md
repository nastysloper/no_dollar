no_dollar
=========

Example of AJAX request without using JQuery, hence the name "no dollar"

HERE is the example of AJAX using pure JavaScript:

<script type="text/javascript">
function loadXMLDoc()
{
var xmlhttp;
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }

xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
  }
xmlhttp.open("GET","ajax_info.txt",true);
xmlhttp.send();
}
</script>

Here is the same example using JQuery:

$.ajax({
  url: "test.html",
  context: document.body,
  success: function(){
    $(this).addClass("done");
  }
});

What is the mapping?
It's really not clear. For starters, the URL for each looks different. These do different things
that are not readily apparent.


Things to define:

XML 
extensible markup language
extensible means that the xml document can be extended--that is, information/tags can be added-
and the application will not crash because it can still find the information it needs to find
without tripping over the newly added data.

text-based files, so any text editor can render the contents. 
XML was designed to store and transfer data; HTML was designed to display data.
XML doesn't do anything. With XML, you invent your own tags and then write a program
to handle those tags and the data within.
XML attribute values must be quoted? <note date="12/20/2013">
<book category="children"></book>
names cannot start with XML xml Xml


XMLHttpRequest()
this is obviously a function. It's also an object constructor, based on how it's used:
xmlObj = new XMLHttpRequest()
This is where things start. You can
request data from the server
receive data from the server
send data from the server

The convention is to call it 
xmlhttp = XMLHttpRequest();
// get rid of line 18, the active x object obselescence.
All browsers come with the XMLHttpRequest object available to use.
All browswers have an XML parser

###########################################################################
Let's retrieve some information from the server.


if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }

xmlhttp.open("GET","books.xml",false);
xmlhttp.send();
xmlDoc=xmlhttp.responseXML;

###########################################################################

if window.XMLHttpRequest, then create an XMLHttpRequest Obj? Seems that way...
Yes! That is what's happening on line
loadXMLDoc()
another function. References found on w3schools. maybe this reference isn't so bad...
The function can be stored in the <head> and called by the script in the page.

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


###########################################################################
Do you ever need to parse an XML string?

if (window.DOMParser)
  {
  parser=new DOMParser();
  xmlDoc=parser.parseFromString(txt,"text/xml");
  }
###########################################################################


I do not think I need to do any XML parsing, but i do need to trigger an event. 
I believe that is what the function loadXMLDoc is for
You call the function when something is clicked? Sure, have a button that is tied to a script.
Just give it a shot and see what happens.
