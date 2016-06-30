## External Data

#### File Method

The simplest way to read a file in use the code:

```ruby
file = File.open('names.txt')

file.each do |line|
	puts line
end
```

To open up a file and edit, it use the following code:

```ruby
File.open('names.txt','w') # write some stuff to a file

File.write('write','Hello this is some more text')

#Code might need citation
```

**Look at the specification for the File Method**

---

## YAML (Yet Another Markup Language)

* Holds key and value pairs.

* `-` # represents items in a list, kind of like an array and is really important.

* It is white space sensitive, so cares about spaces and tabs. However, it doesn't care if you use tabs and spaces but make you sure stick to one.

---

###### Task: Create a file for phonebook.yml

* To load a YAML file in on the command line use the ruby gem **irb**. The syntax used when applying the gem are the following:

    `irb -r 'Your_file.yml'`

* To open up a YAML file/ create a file object use:

  `f = File.open('people.yml')`

* Then loading the created file in YAML use:

  `YAML.load(f)`

 **A thing to note down, is that `YAML.load` turns the file object into a ruby hash.**

Or you could just as well do:

* `YAML.load(File.open('people.yml'))` # remember that you get strings as the keys

To get something specifically with the file you have to use syntax similar to this:

* `f["people"][1]["phones"][0]`

---

###### My YAML file for people:

```yaml
people:
  - f_name: Shorof
    s_name: Shiblu
    dob: 2 Feb 1993
    email: shorof.uddin22@gmail.com
    telephone: 07946662131

  - f_name: Barry
    s_name: Hawkins
    dob: 1 July 1980
    email:
      - barry@gmail.com
      - barry@outlook.com
    telephone:
      - 02077902582
      - 02075783839

  - f_name: Qasim
    s_name: Hassan
    dob: 2 April 1994
    email:
      - qasim_daone@live.com
      - qasim@gmail.com
      - qasimwashere@real.com
    telephone:
      - 07947484848
      - 07839393930
      - 07845959393

  - f_name: Haridas
    s_name: Nyquiel
    dob: 10 Jan 2008
    email: h@live.com
    telephone:
      - 08928328489
      - 02723838383

```

---

###### The RSpec test to check the YAML file has been loaded for the Phone/Address Book:

```ruby
#The test was made in the AddressBook_spec.rb file
require 'spec_helper'

describe "AddressBook class" do

  it "should load from a YAML file" do
    book = AddressBook.new
    book.loadyaml('./people.yml')
    expect(book.address.size).to eq 4
  end

end
```

---

###### The Implementation of the RSpec test:

```ruby
#the Implementation was carried out in the AddressBook.rb file
class AddressBook
  attr_accessor :address
  def initialize
    @address = []
  end

  def loadyaml(file)
    a = YAML.load(File.open(file))
    a["people"].each do |p|
    person = Person.new(p['f_name'],p['s_name'])
    @address << person
    end
  end
end
```

---
