CSS Cascading Style Sheets

<p style= "color:red;" > Hello this </p>

<style>, inside the head
	p, selector {
	color:yellow;
	background-color: #a1a1a1;, hexidecimal value of a color
	font-size: 12px;
	margin-top: 10px;
	padding:
	text-decoration: underline;
	text-transform: uppercase;
	}
</style>

selecter{
property:value;
} 

can create a css doc for styles, styles.css
then put a link tag 

<link rel "stylesheet" href="styles.css">

h1{
	color:red;
}

Selectors

Elements

h2{
	color:red
}

li{
	color:red
}

p{
	color:red
}

DOM, document object model

section p, get me all the paragraphs that are a descendent of the section, 
this is nesting {
	color:red
}

#sect1, refers to ids{
	color:red
}


#sect1 h2, refers to ids with nesting{
	color:red
}


.highlight, get me all the elements that have the class highlight {
	color:red
}

ul.highlight, {
	color:red
}

body > p, get me all the paragraphs that are a direct child of body {
	color:red
}

#sect2 > h2, ht direct child of id sect2 {
	color:red
}

p.highlight, get me all the paragraphs that have class highlight {
	color.red
}

p(*).highlight, get me any element that has class highlight in p, the space means descendent {
	color.red
}

Specificity

CSS is executed in order
The last selector is done
So it matters in the order you put in the stylesheets
Mores ids the more specific it is

Units of measure

width: 10px;
width: 50%;
width: 3em;
width: 3rem;

CSS properties

List style none
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

qassimhassan.co.uk

text-align:center;,

If its an external link dont make it a navigation tag.

body
margin:0;
font-family:
font-size: 16px;, do this in the body then can use em anywhere else

for page header
background-color:
paddin: 0 16px, no padding on top and bottom but 16 pixels on the left and the right

page header h1
font-size: 5em;

page header 2
font-weight: lighter?
margin-top:0.7em;
margin-left:

page-header address
font-style:normal

page-header 
font-size:
color:
list-style-type:none
padding:
float:right
margin-top:

page-header 
display:inline

page-header li:after{
content: "|";
color:white;
}

line-height:1.5, space between lines
letter-spacing: 1px:, spacing between letters space of 1

section
padding:1 em;

section header h2
border-bottom:2px solid #coloryouwant; 

to get rid of padding write padding = 0; 1em; your choice

border-radius: 5px, to be used on the form.

input, textarea {}

text-transform: uppercase;

cursor: pointer,
for submit on the form changes the mouse to a hand.

have to create popups in css or html
use 3 or 4 colors 

Flex box

The structure
display:inline-block;
width:110px;
text-align:center;
padding:5px;
margin-bottom:100px;


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Advanced CSS

Floats

www.youtube.com/watch?v=qhiQGPtD1PQ

Positioning

