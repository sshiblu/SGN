#### Installing Ruby on Windows

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

---

#### Installing Ubuntu OS

* Make sure you create a partition large enough for the new OS. So cut some space away from the C Drive (Ballmark figure around 50GB).

* Download Ubuntu on a external hard drive then reboot the computer. Pressing escape then setting it up.

* Open up the terminal then install ruby, git, chrome, atom (or your preferred text editor) and slack.

* Create a SSH by googling it to make your life easier. SSH is an authorisation key.

* Use the command `sudo dpkg -i program setup name in folder`, to install programs on the command line. But make sure you are in the right folder (probably downloads).

* To update ubuntu, `sudo apt-get update; sudo apt-get upgrade`.
