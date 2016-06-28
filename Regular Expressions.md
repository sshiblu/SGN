##Regular Expressions (regex or regexp)

Regular Expressions are used to match against strings. Fundamentally, Regular Expression are a mathematical thing. They can be either very complex or easy.

An example of regex being used in ruby:

      name.match(/^[\da-z]+\d$/); # (/) means its a regex

When comparing using regex you use:

      =~ #equivalent of == for regex  

* "joe@gmail.com is cool" =~ `/joe@gmail.com is cool/` # We get an integer 0 so it means its a match as its true.

* "joe@gmail.com is cool" =~ `/bob@example.com is cool/` # We get nil, as it doesn't match and is false.

* "joe@gmail.com is cool" =~ `/e/` # We get 2, which means the position where it found the match.

**Use Rubular.com**

####RegExp Syntax

**The following syntax matches character by character**

* `/a/` # matches against the literal character a

* `/\?/` # need backslash when we match the literal (special character)

  * like ^ $ ? . / \ ,


* `/.ob/` # `.` stands for any character so its a wildcard character

* `/[RrBb]ob/` # stuff inside the square brackets mean look for it as one character

* `/[aeiou]/` # character class, so will look for anything inside the square bracket but return only one character

* `/[a-z]ob/` # character class (range), so will match anything between a-z then matching literally with ob

  * `/[A-Fa-f0-9]/` # can put ranges next to each other so will match anything between the ranges. If there is a match a single character will be returned

  * `/[^A-Fa-f0-9]/` # the carrot negates the range

  * `/[0-9]/` # matches against any single digit


* `/\d/` # predefined classes, `d` is a predefined class that matches against any single digit as well, `\` is a escape character

#####Operators

* `/a*/` # so it operates on the character that came before it, for this instance it means 0 or more of the thing that came before it.(a or aa or aaa)

   * `/.*/` # so it matches anything as many times as we want  

   * `/Jon *Doe/` # so Jon Doe with any amount of spaces in between

* `/Jon +Doe/` # + means 1 or more, so 1 or more spaces in between John Doe

* `/a?/` # `?` makes it optional, so it will match 0 or 1 or the thing that came before it

For emails the regex we made in class:

     /[A-Za-z0-9\.]+@spartaglobal\.com?/ #the ? makes the last character optional  

* `/a{3}/` # this operator will match against 3 of what came before it (so it is aaa)

  * `/a{3,7}/` # this will match against 3-7 occurrences of the character a

  * `/a{3,}/` # this will match 3 - infinity occurrences of a

  * `/\d{3,4}/` # this will match against 3-4 occurrences of any digit  

####Lines

* `/^ruby/` # it will match ruby on a line which has a carriage return before it

* `/ruby$/` # it will match ruby on a line which has a carriage return after it

####Brackets

* `/(R|B)ob/` # it will match either Rob or bob

* `/(R|B)+/` # any combination of string R or B

* `(?:R|B)+` # this ignores the capture (being stored) caused by the brackets because of the ?:

* `(?<day>\d{1,2})` # stores the value of what's in the bracket in the group name day

---

####Using regex in ruby

On pry:

        result.methods - Object.new.methods

* By doing the above subtraction we are left with the methods we want

* `result.name` # gives us an array with all the group names
* `result.captures` # gives us an array with all the entered data
* `result[0]` # gives us the actual match

---

#### My Attempt at regex

* `\w+(?:\.\w+)?@(gmail|hotmail|outlook|live|)\.com` # My attempt at a regex email address or can use `\w+(\.\w+)?@[a-z]+\.com`

* `020\d{8}` My attempt at a phone number only in London

---
