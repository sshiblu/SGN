##Ruby Object Oriented Programming

####What is Object Oriented Programming (OOP)?

It gives us a way of **representing a person or thing as an object.**
An **object** is an **instance of a class** and is made up of **attributes/variables and methods.**
It also follows the **3 key concepts:**  

1. *Encapsulation*
2. *Inheritance*
3. *Polymorphism*  

Change the state only affects the object, when you change the methods they affect all the objects in the class.

Creating instances of a class are called an object. Class is a template and
the objects are created. When we define a class have attributes/variables and
methods. Methods allow it to do stuff and variables/attributes hold its state.

Object = state(Described by Variables) + behaviour(Defined by Methods)

Every object of the same type will have it's own state
and we can change the state.

All object of the same state will share the same behaviour.
Behaviour is shared between instances while state changes across instances.

Core OOP Concepts

Encapsulation

Is that we are never allow to access instance variables(change the state)
from the outside.
The only way to do this is to create methods which allow us to do this.

nil = null in ruby

bob.inspect, returns a string saying whats what
bob.class, tells us where the object bob is from
bob = Person.new
bob.set_hair_color('black')

irb -r ./foo.rb

-------

class Person

  def initialize #when wwe create a new instance of this class, it will run it in here
    @height = 0.0 #by putting @ in front we know it is an instance variable
    @hair_color = nil
    @top_color = nil
  end

#setters

  def set_height(height) #this is a setter or setter method
    @height = height
  end

  def set_hair_color(color)
    @hair_color = color
  end

  def set_top_color(color)
    @top_color = color
  end

#getters

  def get_height # we have methods to access the instance variables
    @height
  end

  def get_hair_color
    @hair_color
  end

  def get_top_color
    @top_color
  end

  #instance methods

  def dance
    return 'I am Dancing'
  end

  def sleep
    return "Zzzzzzzzzzzz"
  end

  def description
    return "He is a good looking man with a good sense of humour. He loves life, is pensive a lot but really humble. The colour of his hair is #{@hair_color} and has a height of #{@height} cm "
  end

end

--------

class Person

  attr_reader :height, :hair_color, :top_color #creates the getter methods
  attr_writer :height, :hair_color, :top_color #creates the setter methods

  def initialize #when wwe create a new instance of this class, it will run it in here
    @height = 0.0 #by putting @ in front we know it is an instance variable
    @hair_color = nil
    @top_color = nills

  end

  #instance methods

  def dance
    return 'I am Dancing'
  end

  def sleep
    return "Zzzzzzzzzzzz"
  end

  def description
    return "He is a good looking man with a good sense of humour. He loves life, is pensive a lot but really humble.
    The colour of his hair is #{@hair_color} and has a height of #{@height} cm "
  end

end

---------

class Person

  attr_accessor :height, :hair_color,:top_color #creates both the setter and getter methods

  def initialize #when wwe create a new instance of this class, it will run it in here
    @height = 0.0 #by putting @ in front we know it is an instance variable
    @hair_color = nil
    @top_color = nil
  end

  #instance methods

  def dance
    return 'I am Dancing'
  end

  def sleep
    return "Zzzzzzzzzzzz"
  end

  def description
    return "He is a good looking man with a good sense of humour. He loves life, is pensive a lot but really humble. The colour of his hair is #{@hair_color} and has a height of #{@height} cm "
  end

end

---------

Making the initialise method readable

class Person

  attr_accessor :height, :hair_color,:top_color #creates both the setter and getter methods

  def initialize (a = 0,b = nil,c = nil) #when wwe create a new instance of this class, it will run it in here
    @height = a #by putting @ in front we know it is an instance variable
    @hair_color = b
    @top_color = c
  end

  def initialize #when wwe create a new instance of this class, it will run it in here
    @height = 0.0 #by putting @ in front we know it is an instance variable
    @hair_color = nil
    @top_color = nil
  end
  #instance methods

  def dance
    return 'I am Dancing'
  end

  def sleep
    return "Zzzzzzzzzzzz"
  end

  def description
    return "He is a good looking man with a good sense of humour. He loves life, is pensive a lot but really humble. The colour of his hair is #{@hair_color} and has a height of #{@height} cm "
  end

end

--------

Inheritance

Inheriting the methods and attributes from its predeccosors while leaving it
open for adding more attributes and methods.

Abstract classes are classes we never abstantiate.

raise "Babies don't cry", raises an error

 * args, argument for the family member
super args
--------

class Person

  attr_accessor :height, :hair_color,:top_color #creates both the setter and getter methods

  def initialize (a = 0,b = nil,c = nil) #when wwe create a new instance of this class, it will run it in here
    @height = a #by putting @ in front we know it is an instance variable
    @hair_color = b
    @top_color = c
  end

  #instance methods

  def dance
    return 'I am Dancing'
  end

  def sleep
    return "Zzzzzzzzzzzz"
  end

  def description
    return "He is a good looking man with a good sense of humour. He loves life, is pensive a lot but really humble. The colour of his hair is #{@hair_color} and has a height of #{@height} cm "
  end
end

class Baby < Person # create baby and make it a subclass for person, the superclass is the parent
  def initialize (height, hair_col=nil, top_col = nil)
    @smell=smells
    super(height, hair_color)
  end

  def cry # method only available for babies
    "Waaaaaaaaaahh"
  end

  def dance #we are overriding the parents class
    "I dont dance"
  end
end

---------


Polymorphism

Diffrent classes who appear to work in the same way from the outside, but from the inside are different.
Using .to_s on different children classes give you the same thing

private methods makes a method within a class private so you can only use it in the class
and cant be called outside the class.  

protected method, slightly different than private look it up

-----------------------------------------------------------------------------------

Modules

You can wrap classes in modules
Really really good practice when creating an application
Keeps things separate
allows you to have same class names in different modules
a way of sharing methods across classes
includes . . .

name spacing classes so they are unique and make sense . . .

p = ModuleOne::Person.new

using pry to screw about the objects

--------

Using attribute accessor the getter and setter methods are created so . . .
A getter method created
Shorof.f_name

A setter method created
Shorof.f_name = 'Barry'

.is_a?, will check if the class instance has been created
--------

class Person
  require 'date'
  attr_accessor :f_name, :s_name,:dob #creates both the setter and getter methods
  attr_reader :email, :phone

  def initialize (f_name,s_name,dob = nil)#nil so dob is optional
#when we create a new instance of this class, it will run it in here
    @f_name = f_name.capitalize #by putting @ in front we know it is an instance variable
    @s_name = s_name.capitalize
    @dob = Date.parse(dob) if dob #if dob contains anything it will come true, only time be false if variable dob contains nill or is false
    @email = []
    @phone = []
  end

  #instance methods

  def full_name
    return "#{@f_name} #{@s_name}"
  end

  def add_email(email)
    @email.push(email)
    return "Your email address #{@email} has been stored"
  end

  def remove_email(email)
    @email.delete_at(email)
    return "Your email address #{@email} has been removed"
  end

  def add_phone(phone)
    @phone.push(phone)
    return "Your phone number #{@phone} has been stored"
  end

  def remove_phone(phone)
    @email.delete(phone)
    return "Your email address #{@email} has been removed"
  end

  def to_s
   puts "#{full_name} was born on #{@dob}.\n"
   puts "Their email addresses are: #{@email}. Their phone numbers are #{@phone} "
  end

  def print_details
    puts "#{full_name}"
    puts "-" * full_name.length + "\n"
    puts "Date of Birth: #{@dob.strftime("%d %B %Y")}\n\n"
    puts 'Email Addresses:'
    @email.each do |email|
      puts "- #{email}"
    end
    puts "\nPhone Numbers:"
    @phone.each do |phone|
      puts "- #{phone}"
    end
  end
end

class FamilyMember < Person
   attr_accessor: relationship
   def initialize (relationship = "Someone", *args)
     @relationship = relationship
     super(*args)
   end
end

---

#### Class

When altering a class make sure in the method you write self:

```ruby
@@todos = [] # it is a class variable, it can be accessed by any of these instances.

def self.all
  @@todos
end
```
