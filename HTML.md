http://google.com - This is a domain name

http://google.com:8080/search?term=hello#result1

http://       google.com    :8080   /search     ?term=hello     #result1
Scheme     Domain          Port     Path          Query String    Fragment (fragment identifier)

scheme://domain:port/path?querystring#fragment
    
Requests: HTTP, FTP, SMTP, SSH, Telnet and so on.

Verbs: GET will be a request to get information from the server. POST is to send data to the server. PUT update some data on the server. PATCH partially modify some data. DELETE will remove data on the server.

CRUD:

Create - POST
Read - GET
Update/Replace - PUT
Update/Modify - PATCH
Delete - DELETE

How to create a file in the folder "Todo" ?

POST /todo 
title: "Buy something" due: 2014-04-01

title: is a tag that is used to add a title.

due: is a tag used for dates

? is always used before the querystring. 
+ is used for a space in the URL
# is used before a fragment is inserted. (A fragment is a pointer to some content on a webpage)

So to create in using POST in I'm Only Resting

http://lacedeamon.spartaglobal.com/todos?tite=haridas&due=2014-12-2

To update an entry using PUT

http://lacedeamon.spartaglobal.com/todos/6755?title=haridas nykiel&due=2014-12-3

The syntax is not always the same for each server.

REST

Scalability
Created to accommodate for future growth

Performance
Stress testing: is how much can it handle at the maximum.
Load testing:


HTTP Status Codes

    * 200 OK (successful)
    * 201 Created
    * 204 No Content
    * 300 (moved resource)
    * 301 redirect
    * 400 (Client error)
    * 404 bad request
    * 403 forbidden
    * 405 method not allowed
    * 500 (server errors)
 
This is also a markup language. You cannot invent your own tags.

Look for a logical and coherent structure.

<!doctype>
<html> (this is to explain that it is a HTML doc)
    <head> 
         <title>This is a Title</title>
    </head>
    <body>
         <section>
              <h1>Joe</h1> (This a heading, which will have larger text size. There can up to <h6>)
              <p>078977785674</p> (This is a paragraph, by default it will output using normal spaces between words)
              <p><a href="...">joe@hotmail.com</a> (This tag is generally used to produce links/Anchors, inline.)</p>
              <img src=>
         </section>
    </body>
</html>

<strong>BOLD TEXT</strong> (This is to make the text bold, inline tag)
<b></b>(This will make text bold for keywords)

<em>Emphasized text</em> (This will be used for text you are trying to emphasize, inline.)

<div></div> (can be used to structure and group elements)

<ul></ul> (is an unordered list, only children you can have is <li>.)
<li></li>(is a list item, it is an ordered list. )
<ol></ol>(is an ordered list Order does matter.)
<img src="image.jpg"> (this is an inline tag which will output an image.)

---------------------------------------------------------------------------------------------

<header>, this tag is generally used at the top of the page and gives a semantic structure, 
this is for the header section of the webpage, outputs the same way as a div

<main>, 
the main element represents the main content section of the body of a document or application 
The main content section consists of content that is directly related to or expands upon the central topic of a document or central functionality of an application

<aside>, The aside element represents the additional information on the side of the page, for non-critical information
<article>, 

represents the complete or self contained, composition a document, page, application, or site
<footer>, this tag is used at the bottom, a disclaimer or other links such as, links to Facebook page, twitter and so on

<nav>, generally used for a nav bar

<link>, can be used to add links to your page
A good example of this tag is:

<link rel=“stylesheet” type=“text/css” href=”main.css”>
, this link will make the HTML page look at a CSS stylesheet named ‘main.css’ to style the page
’type’ specifies the type file linked to, ‘rel’ specifies the relationship between the current file and the file being linked to, 
in this case the relationship is ’stylesheet’, does not need a closing tag

<br>, breaks will cause text to move to the next line, not good practice

<div></div>, can be used to structure and group elements 
<div id = "">, must be unique, usually use camel case when entering names can be visited
<div class=“container”>, the ‘class’ is the name of the container to use by CSS, to style the elements within the <div>.

	<figure>, this tag will allow you to associate a caption with an image.

		<img src=“img.jpg">

			<figurecaption> (wrap the caption with this tag. )
				
<p>
Text that is associated to the image.
</p>
		
	</figurecaption>

	</figure>


<script>, can be used to add JavaScript to your page 

	<video width=“320” height=“240” controls>, this tag is used to add a video to your web page 'width' and 'height' is setting the size of the video and ‘controls' is adding video controls such as play, pause and stop

		<source src=“video-url.mp4” type=“video/mp4”>, 
sets the url of the video to play, ’type’ sets the video format 

	</video>

<meta charset=“utf-8”/>, Tells the web browser which character set to use. In this case the character set is ‘utf-8'

Create a form in HTML.

<form method = "" action "">
<input type = "text" name = "title" id = "title">, is to create a text to type information self closing
<label for = title> Todo item: </label>, good practice to have this when creating input elements such as text box
Always have a label tag for an input tag
<input type=“submit” value=“Save”>, creates a button, with a value of save to submit the information

<input type=“file”>, to upload files

<input type=“radio”> to create a multiple choice menu

<select name=“select-choice” id=“select-choice”>, this is for drop down menus 

<option value=“value1”>

<textarea></textarea>, outputs a box for entering text

<input type=“button”>, will create a button can be used with JS 

<input type=“hidden">, just 

<input type=“email”>, will change the keyboard so that it would easier to add information

<style>, can use css in the original html file in the head, dont use if your using a spreadsheet

lacedeamon.spartaglobal.com/example_forms
microformats

<address>, use for twitter links and contact information
<time datetime="2014-4-30"> last tuesday </time>
use div for images makes it easier to use css on

W-CAG
BS 8878:2010
WAI-ARIA
could use <main role="main">, use Aria roles for accessibilty when needed

------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<hr>, horizontal line

The element i want then however many childs i want:

	ul>li*17

Inside the anchor tag, target="_blank", opens a new tab for a link from Qasim