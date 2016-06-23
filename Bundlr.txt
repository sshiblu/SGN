
Bundler

Small tools so are not important to worry about so much

Bundler is a gem which we should have installed, for gem dependency.

Bundler aim to bundle up the gems, all the dependencies for a project. 

gem 'awesome print', makes stuff look pretty.

rubygems.org, where all the gems live

make a Gemfile, then give it a source to look for ruby gems.

---------
In the Gemfile . . . 
source "ht"

ruby '2.3.0'

gem 'rspec','~>3.4.0',the gem we are using, 
and the version we want, if the gem updates or atleast the minumum version we will use
gem 'httparty'
---------
use ruby -v, to find the version of ruby installed

On command line write bundle install, this installs the gems and all its 
dependencies

bundle update, it will update the latest versions of the gems which we did not specify

Gemfile.lock, describes all the dependencies. Never edit it.

Its considered good practice to use versions when using the gem file

rspec -v, gave us the latest version of rspec available on your laptop

bundle exec  ,any command you put after it will be ran in the context of the bundle
,so specific to your project

Look up the bundler documentation. 
bundler.io

--------

source "https://rubygems.org"

ruby '2.3.1'

gem 'rspec'
gem 'httparty'

-------------------------------------------------------------------------------------

Rake

Rake is a task runner

To create the file just write

touch Rakefile 

bundle exec rake tests, to run it specifically for the example in our project
,runs the task test

helps us build more complicated tasks

rake deploy,
rake db migrate,

--------

task :tests do
  exec('rspec')
end

--------