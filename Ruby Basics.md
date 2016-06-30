In Ruby the code is read from left to right

Whats a rubygem?
Its a library or a tool

ruby -v, will show what version of ruby is installedgem
gem list, see what gems you have
json, read and spit out json
minitest, unit testing framework
rdoc, allows us to look at documentation for certain libraries
test-unit, is a unit testing framework

gem update --system, updates the gems
gem update json,
gem update, updates gems

vagrant provision, fix the error i was having with the provision system

Make a file called foo.rb

Using Atom as the text editor

#this is a ruby file

put "Hello World" #prints of the words Hello World

to run it, be in the folder then type 'ruby foo.rb'

--------------------------------------------------------------------------------

Basic arithmetic

puts 1 + 3, spits the arithmetic on the screen when you run it

puts 1 - 3, gives -2 on the screen

puts 1.0 + 3.0, gives floating point number 4.0, can even make one number a float

puts 9.0 / 2.0, give 4.5

put 9 / 2, integer mathematics
so returns as 4 a there is no rounding so always goes lower

How many hours are there in a year?

puts 24*7*52,
8736

What's your age in seconds?
puts (60*60*24*7*52*23) + (60*60*24*17),
724809600

---------------------------------------------------------------------------------

Strings

puts 'Hello', spits out Hello

puts 'Hello' + 'World', spits out HelloWorld

puts '12' + 12, diffrent types so gives as error

puts 12 + '12', different error, the + is a method

puts 'hello' * 12, spits out hello 12 times

puts 'hello,that's nice', glitches out
puts "'hello,that's nice'", put in the quotation marks to solve it and print it off
double quotes lets us use escape characters and allows for string interpolation

puts "hello,that's \"nice\"", using a literal

\n, a new line so can chuch it after

puts 'hello,that\'s nice', can use single escape on a single quote

in ruby we use snake case so . . .

my_string = "Hello there,"
puts my_string

name ='Bob'
puts 'my name is' + name + '!'
or
puts "my name is #{name}!", using string interpolation

name ='Bob'
puts "my name is #{name}!"
name ='Vicki'
puts "my name is #{name}!"

name ='Bob'
puts 'my name is' + name + '!'
name = 6
puts 'my name is' + name + '!',
glitches out because of different types like before

var1=8
var2=var1
puts var1
puts var2
puts ''
var2 = 'eight'
puts var1
puts var2, exercise just to see the logic and whats going on

In all programming languages shizzle dont get deleted, for instance for var2
it doesnt get deleted or overwritten it just point at the content of var1

Conversions

puts '25' + 6.to_s, so converting 6 to string
puts '25'.to_i + 6, so converting 25 to an integer

number = '25'
puts number.to_f + 6, turns it to floating point number, so you get 31.0

puts 'Hello'.to_i, gives 0 which is unexpected, as it Ruby cant find a way
to convert the string to an integer

puts 1 + 6, puts adds an .to_s to everything so does the calculation or shizzle
first then makes it into a string

puts gets, allows you to type in the terminal and then print it out

It will be more effective to write . . .

puts "What's you name?"

name = gets

puts "Hello #{name}", how are you?, then prints off the name
,but goes to new line because of the characters you entered
so there is a carriage return on the command line

so use chomp to solve to get rid of carriage return . . .

puts "What's you name?"

name = gets.chomp

puts "Hello #{name}", how are you?, call the chomp method on that
stuff so no carriage return

Apply root-cause analysis!

puts, gets and chomp are kinds of methods

----------------------------------------------------------------------------------

Lunch Homework

Task 1

puts "\nHi, How are you?"
puts "Thats very interesting.\n\n"

puts "Please enter your first name:\n\n"
first_name = gets.chomp

puts "\nPlease enter your second name:\n\n"
second_name = gets.chomp

puts "\nThank you for you information and have a nice day.\n\n"
puts "You will be contacted by a car insurance company very shortly.\n\n"

Task 2  

puts "\nHi, My name is Barry"
puts "Please enter the first number:\n\n"

first_num = gets.chomp.to_i

puts "\nPlease enter the second number:\n\n"

second_num = gets.chomp.to_i

puts "\nHere is the addition of the two numbers:\n\n"
puts first_num + second_num
puts "\n"

Task 3

Write a program that asks for a users name and age in years,
then roughly calculates the number of seconds they have been alive for,
printing it in a message, with their name.

---------------------------------------------------------------------------------

Methods are the Ruby equivalent for functions
For Ruby for spacing we use spaces not tabs!

def print_my_message(fname, sname, age), the stuff in the brackets are the method definitions, arguments
	full_name = fname + '' + sname
	puts full_name + ' is ' + age.to_s + ' years old', by making the age
	a string we can initially have it as an integer or float also string
	can only be added to a string
end

call the method by:

print_my_message("Joe", "Bloggs", 28)

def calculate(first, second)
	answer = (first + second) * second * 10
	return answer, so gives back the answer for the method calculate
	,what does the method return
	,only time we use it is in conditional and we want something to run higher up
	,a method will always return something but will always return the last line
end

thing = calculate(5, 4)

puts thing * 100


puts rand(100), existing method which spits out random numbers upto 100


def my_rand
	return rand(1000).to_s
end

puts "This is a number:" + my_rand

	http://ruby-doc.org/, Ruby documentation sheet

puts "fooo".reverse, returns the character in reverse
puts "fooo".captilize, caps the first letter so Fooo
puts "fooo".upcase, turns all the letter to uppercase
puts "fooo".swapcase, turns eveything which is uppercase to lowercase and vice versa
puts "fooo".length, returns the length of the string in integer format so 4.re

def mess(strng)
   strng2 = strng.reverse.upcase
   return strng2
end

puts mess("Barry")

way better solution

def reverse_caps(string)
	return string.reverse.upcase
end

puts "Hello there. This is Weird:"

Flow Control

Using if statements

puts 'Enter your name'
name = gets.chomp

if name == name.uppercase
	#SHOUTING
else
	#NOTSHOUTING
end

puts 'Enter your name:'
name = gets.chomp
puts 'Hello ' + name + '.'

if name == 'Danny'
	puts "That's a good name"
elsif name == 'Vicky'
	puts "Also a good name"
elsif name == 'Harold'
	puts "maybe a good name"
end

!, is a bang so it changes whatever is before it and then stores it that location.

so:
        a = "jsjsjs"
        a.uppercase!

In an if statement, the statement that comes first has a higher priority.
-------

if (name == 'Danny' || name == 'Harold'), can use and/or operators
	#Do something
else
	#Do something else
end

------
if !(name == 'Danny' && age >25)
	#Do something
else
	#Do something else
end

or . . .

unless (name == 'Danny' && age >25)
	#Do something
else
	#Do something else
end

------
My Attempt, Try and come back and fix it

  require 'date'

  puts "\nHi, Please enter your name:\n\n"
  name= gets.chomp

  puts "\nPlease enter the month you were born in:\n\n"
  month=gets.chomp.to_i

  puts "\nPlease enter the year you were born in:\n\n"
  year=gets.chomp.to_i

  age = Date.today.year - year
  puts "\nYour age is:\n\n" + age.to_s + "\n\n"


  if (age < 6 || age > 70)
    puts 'Well done on being able to use a computer'
  elsif (age < 16)
    puts "Do you have permission to use the program please enter y/n"
    permission = gets.chomp
    if permission == 'y'
      puts age
    elsif permission == 'n'
      puts 'You should probably ask your parents for permission'
      puts age
    end
  end

------
  puts "\nHi, Please enter your name\n\n"
  name= gets.chomp
  puts "\nPlease enter the month you were born in\n\n"
  month=gets.chomp.to_i
  puts "\nPlease enter the year you were born in\n\n"
  year=gets.chomp.to_i
  permission = true

  age = 2016 - year

  if (age < 6 || age > 70)
    puts 'Well done on being able to use a computer'
  end
  if (age < 16)
    puts "Do you have permission to use the program please enter y/n"
    response = gets.chomp.downcase
    if response == 'n'
      permission = false
      puts 'You should probably ask your parents for permission'
    end
  end

  if permission == true
   puts name.capitilise + ', you are bout ' + age.to_s + ' years old'
  end

-------

  require 'date'

  puts "\nHi, Please enter your name\n\n"
  name= gets.chomp
  puts "\nPlease enter the month you were born in\n\n"
  month=gets.chomp.to_i
  puts "\nPlease enter the year you were born in\n\n"
  year=gets.chomp.to_i
  permission = true

  age = Date.today.year - year

  if (age < 6 || age > 70)
    puts 'Well done on being able to use a computer'
  end
  if (age < 16)
    puts "Do you have permission to use the program please enter y/n"
    response = gets.chomp.downcase
    if response == 'n'
      permission = false
      puts 'You should probably ask your parents for permission'
    end
  end

  if permission
   puts name.capitilise + ', you are bout ' + age.to_s + ' years old'
  end

-------

puts 'Well done on being able to use a computer!' if age < 5 || age > 70, inline if statement
, can do with unless statements as well

----------------------------------------------------------------------------------

Arrays []
,Very powerful we can hold whatever we want in there

Example of a Ruby array:

	my_array = ['one','two','three','four']

then to print it say for the second one . . .

	puts my_array[2]

Can do an array within an array

	my_array = ['one','two','three',[1,2]]

to print the interger 2 do . . .

	put my array[3][1]


languages = ['English','French', 'Norwegian','Ruby']
puts languages.size, tells us how much stuff is the array languages

-------

In Ruby we dont use loops we use iterators, methods

languages.each do |lang|, for strings do each
, .each is an array method which takes the block of code as an argument
	puts lang
end

languages.each do |lang|
	puts "I love #{lang}!"
end

12.times do, another method, for numbers use times
	put "Hello"
end

puts languages.reverse
,will reverse and print also due to puts will be printed off in separate lines

puts languages.reverse!, will affect the array and print

You can stick an array with an array
foo = languages + ['foo','bar']
puts foo

You can join each item in an array in a long string format

puts languages.join
puts languages.join(", "), use to add space in between

puts languages.first, gets you the first item in an array
puts languages.last, gets you the last item in an array

or

puts languages[-1]

puts language.sort, sorts the array out in alphabetical or numerical order

puts languages.push("Foobar"), add stuff in an array

or

languages << 'Hello there''

puts languages.pop, delete the last item in an array
puts '---------'
puts languages

print "", prints everything in a line

---------------------------------------------------------------------------------

Hash {}

Sets of key value pairs
Its normal to use string and symbols as the key
A symbol should be used as a placeholder

my_hash = {'one' =>(called a hash rocket) 'Bob', 'two' => 24}
my_hash['one'] # returns 'Bob'
my_hash['two'] # returns 24

An example of a symbol is

foo = :thing

my_hash = {:one =>'Bob', :two => 'Jim'}
my_hash[:two]

We could also do

my_hash = {one: 'Bob', two: 'Jim'}
my_hash[:two], its a bit more readable

my_hash = {
	people:[
	 {name: 'Danny', age:20},
	 {name: 'Bob', age:20},
	]
}

Puts will always return nil when running it, you can see this in a shell
which you run on the command line

When you use the each method
, when using one local |b| it returns a key value pair as an array

With two locals, This will output the key and the value in the Hash

a.each.do|k,v|
puts "This is the k:#{k}"
puts "This is the v: #{v}"
end

irb, to use the ruby tool/gem on the terminal

When you see names parameters, remember it contains a hash.

---------
Dannys solution

require 'date'

details = {}
puts 'Name:'
details[:name] = gets.chomp.capitilise
puts 'Height (cm):'
details[:height] = gets.chomp.to_i
puts 'Age:'
details[:age] = gets.chomp.to_i
puts 'Date of Birth (eg.2 Jul 1992):'
details[:dob] = Date.parse(gets.chomp)
puts 'Relatives (comma-separated list):'
details[:relatives] = gets.chomp.split (',')
#details.each {|k,v| puts "Key: #{k}, Value: #{v} "} #can put blocks in one line

details.each do |k,v|
  puts "Key: #{k}, Value: #{v}"
end

--------
My attempt


my_hash = {}
  puts "\nHi, Please enter your name:\n\n"
  my_hash[:name] = gets.chomp.capitalize
  puts "\nPlease enter your age:\n\n"
  my_hash[:age] = gets.chomp.to_s
  puts "\nPlease enter your DOB:\n\n"
  my_hash[:dob] = gets.chomp.to_s
  puts "\nPlease enter your height in feet:\n\n"
  my_hash[:height] = gets.chomp.to_s

relatives = []
  puts "\nPlease enter your relatives name:\n\n"
  relatives[r_name] = gets.chomp.capitilise

  puts "\n Do you have any more relatives?, Please enter y or n"
  answer = gets.chomp
  if answer == y
    puts "\nHi, Please enter your relatives name:\n\n"
    relatives[r_name] = gets.chomp.capitilise
  elsif answer == n
  end

-------------------------------------------------------------------------------

Pry

pry, another gem/tool which doesnt come with ruby
pry can work in the command line and in the code

using 'binding.pry' in the code, it is like a break point
,you can use it to edit, check, moving up and down in the code.

use whereami, to find where you are in the code

require 'pry', you have to put require 'pry' in the beginning of the code to declare it

write exit, in order to exit pry
-------------------------------------------------------------------------------------

Recursion

This is a concept, allows us to call a method within itself

We need to think about return values, amazing way of reducing if statements
Methods always execute the last line

-------

def ask_recursively(question)
  puts question
  reply = gets.chomp
  if reply == 'yes'
    true
  elsif reply =='no'
    false
  else
    puts 'Please answer yes or no'
    ask_recursively question
  end
end

ask_recursively "Is it rainy outside?"

---------------------------------------------------------------------------------

Homework
Write your own sort method.
It should sort the items in an array alphabetical or numerical order.
Assue that the array will only hold integers and strings.
Cannot use sort method.
Bonus points for finding the efficiency of my code

----------------------------------------------------------------------------------
