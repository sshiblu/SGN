## Watir and Capybara

Are used for web automation. Watir Webdriver uses the underlying Selenium Webdriver but provide a nicer interface, allows us to do more. Selenium Webdriver is really low-level. Capybara is a higher level has been specifically built in ruby to build forms. Capybara is brilliant when building a ruby project.

## Watir

* Browser API for Selenium
* Nice DSL

install watir so:

          gem install watir

After opening up Pry run the following lines:

* require 'watir'
* browser = Watir::Browser.new
* b = browser
* b.goto "https://google.com"
* b.url # the
* b.title # returns all the text in the element, the current browser better than using page source which gets everything
* b.back # takes you back in the browser
* b.forward # takes you forward in the browser
* b.status # gives you back whatevers in the status bar at tha  t time
* b.html # brings you back all the html in the page
* b.text.match /hello/ # return nil so no hello, when inserted ussualy returned a matchdata object so there is a match
* b.text.include? "ussualy", checks if it contains the word "ussualy", the command returned true.
* **Every HTML tag has an associated method attached to it**
* b.p #gets back a paragraph object
* b.ps #gets back a collection of paragraphs
* col = b.ps
* col.to_A #makes it the collection of paragraphs in an array
* col[1].text # returns the text in the certain paragraph in an array
* .flash # flashes a paragraph on the browser
* col[2].input # searches elements of type input on the page
* col[2].input.send_keys"hello" # sends hello to the input type
* b.inputs.size # tells you have many inputs you have
* b.text_field name: "username" # find the text_field with the following attributes
* b.elements css: ".p" # returns html collection of type p

###### Methods Chaining

* b.section(id: "foo").ps
* b.element css: "#section1 p" (will return element collection) same thing as* b.section(id: "section1").ps (will return paragraph collection)

*Dannys website*

* b.nav.html # returns html
* b.nav.lis[-1].html
* b.nav.lis[-1].a.href

###### Waiting

We can do waiting in Watir as well so:
* b.driver # get back a Selenium Webdriver object
* b.driver.manage.timeout.implicit_wait = 5
* b.select_list(id: 'entry_1000001').wait_until_present
* b.text_field(id: "entry_1000000").when_present.set "Hello"

**Look up the Watir documentation**
