## Installing Ruby on Windows

* [Ruby website](http://rubyinstaller.org/downloads/).

* Download appropriate version of Ruby.

* Download appropriate version of Development Kit.

* Install Ruby

* Install devkit and extract into the ruby folder, you can give it its own folder if you want.

* Then go to the command line and navigate into the ruby file, then in the devkit file if you have one.

* Then write `ruby dk.rb init`

* Go into your devkit folder manually there should be a new file called *config*. Open it up in a text editor then change `C:/Ruby23-x64` => `C:\Ruby23-x64` and then save.

* Go back to the command line or shell, and write  `ruby dk.rb install`.  

* Check the gems installed, by writing `gem list`

* Then install the gem  `gem install ffi --platform=ruby --verbose`
