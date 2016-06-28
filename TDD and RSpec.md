
##Test Driven Development (TDD)

1) *First thing* to do when writing a test, **is to make sure it fails.**

2) *Second thing,* make the test go **green** with the **smallest amount of code possible.**

3) *Third thing,* **refactoring,** as long as we have a green test, we know we haven't broken anything
so we can be a bit braver with our refactoring decisions

Usually, used for **Unit Tests**. It's where you define the Interface first, so a miniature form of black box.

On a side note, something in curly brackets is a block if not a hash.
---

##RSpec

It's a Tool for doing **TDD**.

Make sure you have the RSpec gem installed. RSpec will look for a folder called spec and expect to find the tests in there so ensure that you create a new spec folder for a project.

Will only identify tests when in the format:

		person_spec.rb

When in the project folder write Rspec and write some specs up.

---

##More RSpec

We use RSpec to make a UI, Using the methods such as Describe and Let. We should use let keyword whenever we can.

####Dependency Injection

Use it wisely as it is not always the right solution.

				DateTime.parse("2016-02-19 19:35:42") # Creating a known time

**Creating a Fake class by which we can use for testing. So we inject the dependency. Remember we should always try and reduce test dependencies.**

PowerPoint Example :
```ruby
class Record
	def initialize(time_gen=DateTime)
	  @created = time_gen.now
	end

	def to_s
	  "Created on #{@created.to_s}"
	end
end

class FakeTime # This is creating a stub, it is polymorphic to the class we are creating it on
  def self.now
	  DateTime.parse("2016-02-19 19:35:42")
	end
end
```
---

####Double

				faketime = double("FakeTime", now: time)

This is meta-programming. Creates the class and method using the double method which is only exclusive to RSpec (can only do that inside an RSpec test), the time variable is a hash and it's an instance of "Faketime". **Allows us to create fake doubles of objects. An object that stands in for another object**

---

####Stubbing

Stub allow us create a fake method and classes instead of overriding. **This is creating a method programmed to return a specific value.** You can stub literally any object, but only works on the object, the instance of the class.

This is considered bad practice:
```ruby
class DateTime # We are overriding a predefined class
  def self.now
      DateTime.parse("2016-02-19 19:35:42")
  end  
end
```

A method stub example:

				Time.stub(:now) {DateTime.parce()}

Another stub example:

				class SomeClass; end
				allow(SomeClass).to recieve(:thisthing).and_return("this string")

---

####Test-specific extensions

Allows us to stub out part of an object. We are extending a class just for using tests.

---

####Message expectations

A method stub that raises an error if it isn't called. A good way of checking certain methods are always called.

Example:
```ruby
Describe Statement do
  it "uses the customer's name in the header" do
    customer = double('customer')
    customer.should_recieve(:name).and_return('Danny')
    statment = Statement.new(customer)

  end
end
```
---

####Let Keyword

let takes a symbol and a block (Lazy loading, loaded when it's needed). Not used on stuff you are testing and can only be used outside of it methods.

				let(:category) {24}
				let(:car) {Car.new('Corsa', true)}

---

####Extra Work

* Look up **Subject** Keyword
* Look **before and after loops** as well in the documentation.
* Look up **map**, incredibly useful method for iterating over stuff.
* [Article 1](http://sparta.global/1QOHvG3)
* [Article 2](http://sparta.global/1SX6Zrd)
* [RSpec Guidlines with Ruby](http://betterspecs.org)
* [Type Matchers](https://www.relishapp.com/rspec/rspec-expectations/docs/built-in-matchers/type-matchers)
