## Cucumber

Edge case something the user would not necessary do, but check if it breaks.

#### What Cucumber is for

* Customer collaboration
* Shared Understanding
* An open-source tool for creating Executable Specifications
* Merges specification and test documentation into a cohesive whole
* Bridges the gap between technical and business language
* Main purpose not to be only meant for developers should be in a language the whole business speaks.   

#### What Cucumber is not

* A testing tool, its a specification tool(provides a structure).
* A language for writing tests
* The solution to all automation problems!, not really, well depends.  

#### Brilliant things about Cucumber

* Executable
* Human-readable
* Specification
* Living example

Specification by example is the stakeholder providing bill board examples of what they want.

#### Gherkin

Cucumber uses a language called Gherkin to describe a series of scenarios.
The scenarios have to be relevant to the feature. Made of features and scenarios.
Also has verification points.

#### Writing tests in Cucumber

1) Describe behaviour in plain text.
2) Write a step definition in Ruby (It has to be readable to the user).
3) Run and watch it fail.
4) Write code to make the step pass.
5) Run again and see the step pass.
6) Repeat 2-5 until green like a cuke.

#### Cucumber in Relation to the Agile Testing Quadrants

1) Your Project
2) Features, **2-4 is business facing**
3) Scenarios
4) Steps
5) Step Definitions, **5-7 are more technical for devs**
6) Support Code
7) Automation Library
8) Your System

**Only time a scenario or step definition will fail is if we raise an error/an exception**

---

#### Role play exercise

*Desktop requirements*

* Websites where people can buy puppies
* Returns not accepted
* Not intended for mobile viewing (Focus on Desktop)
* A dashboard to list all the available puppies
  * Have a little button (vdetails) so they can view extra detail on a puppy, redirects for extra detail like how to rent it.
* Want a list view not a grid view
* Want four puppies shown per page, page numbered.
* In dashboard see text Home for the Happy Puppy.
* Search field to search by puppy name or breed.

*Requirements for puppy info page*

* image of puppy
* name and breed
* Extra details
* link 'return to list' which will take you back to the dashboard.
* A history of the puppy, the price of the puppy.
* Button 'Adopt Me!' which will send you to the puppy adoption page

*Puppy adoption page*

* 3 buttons, to 'Complete the Adoption', 'Adopt another Puppy' and 'Change your Mind'.
* Clicking 'Change your Mind' should send you back to the 'Dashboard'.

---

#### Gherkin

Its a langauage to write features and it is domain specific.

#### Gherkin Keywords

* Feature
* Background
* Scenario
* Given
* When
* Then
* And
* But
* Scenario Outline
* Examples
* *

**Each Scenario must make sense and be able to be executed independenty of any scenario.**

#### Doc String

For string not for data. It is deemed at bad practice.

```gherkin

When i choose to show my list
Then the following should be returned:
  """
  You have three items in your list
  - One
  - Two
  - Three
  """

```

---

## Advanced Cucumber

#### Tags and What they are used for

* Running specific sets of scenarios
* Mapping scenarios to Jira (Virtual represenatation of a taskboard) tickets etc.
* Handling setup and teardown
* Aiding devolopment

** To run a yaml file creates profiles in there, then to run a profile use `cucumber -p 'The profile'`**

* `cucumber -t 'The tags you want'`

---

#### Bad Cucumber

* Flaky/Flickering Scenarios
* Brittle Scenarios
* Slow Scenarios
* Bored Scenarios

#### Leaky Scenarios

Each scenario **must** make sense and be able to be executed independently of any other scenario.

* Scenarios are system states
* Ideally, the system should be in a clean sate prior and after running a scenario

#### Race Conditions

It happens when two components run parallel with each other and do the same thing. So you have to wait until it finishes. Is a condition that gives an error because of two things happening at once.

**Imperative Scenario vs Declaritive Scenario**

#### Ubiquitous Language

**Shared Understanding**

* Shared Ownership of code
* Good code comments
* Coding Standard
* Collaboration
* Code for other to read
* System Metaphor
* Consitent

---

## Page and Data Models

#### Page Objects

An instance of a class which represents pages in a system as an object.

#### MGF Pattern

**Model, Glue, Feature Pattern.**

1) Model is the page Objects.

2) Glue are the step definitions.

3) Feature are the features files.

###### Some Rules

* Never call steps from steps
* Never pollute test code with page internals

---

#### Ruby Singleton Pattern

A simple singleton class link:

The class can only have one instance of it.

* http://dalibornasevic.com/posts/9-ruby-singleton-pattern-again
