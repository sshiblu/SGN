## Selenium Webdriver

**Selenium** is a testing tool, used for running ruby scripts. Used for testing web applications. When possible look into **Calabash** which is a testing tool for Mobile Phones.

#### It can drive . . .

A bunch of browsers such as:

* Android
* Google Chrome
* Firefox
* IE
* Safari
* PhantomJS, a headless browser?

#### It can be scripted with . . .

A bunch of different browsers such as:

* Java
* C#
* Python
* Ruby
* PHP
* Pearl
* Javascript

## Selenium with ruby

You have to first install the Selenium gel. To do so write the following line on the command line:

      gem install selenium-webdriver

Its worth looking up the [Selenium Webdriver documentation](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/Driver) on rubydoc.

[Selenium/Ruby Cheatsheet](https://gist.github.com/huangzhichong/3284966).

 `show-source driver.first` # to find the spec for a method

Fire up Pry or IRB.

Then type the following lines on the command line:

*  pry
* `require 'selenium-webdriver'` # it should return true

---
#### Selenium Challeneges

* `d = Selenium::Webdriver.for :firefox` # this will create a new driver object for firesox
* `d.get "http://google.com"` # to visit a webpage using the new driver object

**.methods - Object.new.methods # tells you the methods available for an object**

**Use inspect on the webpage in order to find the element names, id or class**

####### 1 - Basics

1) `d.find_element(:id,"hplogo")` # find the logo element by id and stores in the driver object
2) `inputElement = d.find_element(:id,"lst-ib")` # find the searchbar and store it inside the variable inputElement
 `inputElement.send_keys('Cheese!')` # send the string to the searchbar
`button = d.find_element(:name,"btnG")`=>` button.click` #steps to clicking the searchbar
3) `puts "Page title is #{d.title}"` #print out the pagetitle is a string
4) `d.close` #close the browser  

###### 2.1 - The driver

1) `puts d.page_source` #to get the page source
2) `source = d.page_source` => `source =~ /Hello/` #this returns nil so there is no matches with the string hello.
3) `d.execute_script("alert('Hello')")` # executing the Javascript `alert('Hello')` need the speech marks. And if you want it to execute on the page obviously you have to run it the driver. The line of code produces an alert box saying 'Hello'.
4) `d.manage.window.resize_to(10,10)` # resize the window. `d.manage.window.maximize` # to maximise the window. `d.manage.window.move_to(44,44)` # to resize a window.

###### 2.2 - Finding elements

1)
* `d.find_element(:id,"lst-ib")` # finding by id
* `d.find_element(:class,"ctr-p")` # searching by class
* `d.find_element(:name,"btnI")` # searching by name
2)
* `d.find_element(:tag_name,"div")`
* `d.find_elements(:tag_name,"div")` # to find all the elements with the tag name div
* `s=d.find_element(:tag_name,"div")` => `s.class`# this tells us that it stores it all in an array object
3)
* A css selector really help at specifically choosing an element. By checking for elements within an element using css selectors.
---
###### Useful methods

* `c.text` # to see if an element has text in it

* `s.selected` # to see if an element has been selected

* `.send_keys` # to send characters on it.

###### Waiting

* wait = Selenium::WebDriver::Wait.new timeout: 51 # a waitobject which will wait for 51

wait.until do
  browser.find_element(tag_name: "h1")
end

# wait.until returns the last line in the block.
