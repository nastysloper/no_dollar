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
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
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
text-based files, so any text editor can render the contents. 
XML was designed to store and transfer data; HTML was designed to display data.
XML doesn't do anything. With XML, you invent your own tags and then write a program
to handle those tags and the data within.



XMLHttpRequest()
this is obviously a function. It's also an object constructor, based on how it's used:
xmlObj = new XMLHttpRequest()

if window.XMLHttpRequest, then create an XMLHttpRequest Obj? Seems that way...

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

