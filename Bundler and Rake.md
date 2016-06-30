## Bundler

**Bundler** is a gem which we should have installed, for **gem dependency**. Bundler aims to **bundle up the gems**, all the **dependencies for a project.** Every new project will use Bundler by creating a **Gemfile**.  

* gem `awesome print`, makes stuff look pretty.

* https://rubygems.org, the source url so where all the gems live.

**When making a Gemfile, always give it a source so it can look for ruby gems.**

---
A typical Gemfile will contain:

```ruby
source "https://rubygems.org"

ruby '2.3.1'

gem 'rspec','~>3.4.0'
#the gem we are using, and the version we want.
#If the gem updates this the minumum version we will use.

gem 'httparty'
#gem for Posting and Getting stuff from the web.

```
---

#### Useful Commands

On the command line write:

* `ruby -v` # to find the version of ruby installed.

* `bundle install` # this installs the gems and all its
dependencies specifically for a project.

* `bundle update` # this will update to the latest versions of the gems which we did not specify the versions.

* `rspec -v` # this will give us the latest version of RSpec available on your laptop.

* `bundle exec` # any command you put after it will be ran in the context of the bundle, so specific to your project.

---
#### Bundler Extra

* Its considered **good practice** to use **versions** when using the gem file.

* At the end of a project always **delete the gems you primarily used for testing.**

* The *Gemfile.lock* file describes all the dependencies. **Never edit it!**

* [Look up the bundler documentation](bundler.io).

---

## Rake

Rake is essentially a **task runner.** It runs a culmination of *tasks* in one file. Similar to Bundler you would have one Rakefile for each new project. Rake is useful as it helps us build more complicated tasks.

#### Useful Commands

On the command line write:

* `touch Rakefile` # to create a Rake file.

* `bundle exec rake tests` # to run it specifically for the example in our project, runs the task test.

* `rake deploy` #

* `rake db migrate` #

---

A typical Rakefile will follow this structure:

```ruby
task :tests do
  exec('rspec')
end
```
---
