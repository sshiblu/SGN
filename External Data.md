External data (Ruby)

File method
---------
Simplest way to read a file in

file = File.open('names.txt')

file.each do |line|
	puts line
end

---------

File.open('names.txt','w'), write some stuff to a file

file.write"some text"
end

File.write('write','Hello this is some more text')

---------

Look at the spec for the file method

------------------------------------------------------------------------------------

YAML, Yet Another Markup Language

Holds key and value pairs

'-' represent items in a list, kind of like an array and is really important

It is white space sensitive, cares about spaces and tabs
It doesnt care if you use tabs and spaces but make you sure stick to one

create a file for phonebook.yml

-------
To load the file in

write irb on the command line

then . . .
f = File.open('people.yml')

YAML.load(f), opening up the file in YAML, turns the file object into a ruby hash

or . . .

YAML.load(File.open('people.yml'))
, remember you get strings as the keys

a["people"][1]["phones"][0], to get something specifically within the file
a[]
