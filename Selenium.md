## Selenium Webdriver

**Selenium** is a testing tool, used for running ruby scripts. Used for testing web UI. When possible look into **Calabash** which is a testing tool for Mobile Phones.

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

Fire up Pry or IRB.

Then type the following lines on the command line:

1) pry
2) require 'selenium-webdriver' # It should return true
3) Selenium
4) d = Selenium::Webdriver.for :firefox
