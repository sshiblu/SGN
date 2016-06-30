## Vagrant - VM (Virtual Machine)

Open up a terminal in the virtual machine, use SSH.
This is a way to connect to remote servers in a terminal,
so you can act like your in a remote server.

#### Using Vagrant

* Type `Vagrant SSH` # to get into the VM.
* Type `Vagrant UP` # to get the VM started.
* `WS ->` # prompt that you are in the workstation, the linux box.  
* Go to the **work folder** which is a shared file between the VM and your actual machine, you can check in *.config* to check for the file.
* Type `Exit` # to kill a session.

* To share the file the file between the VM and Worksation you can set it by a **configuration file**.

* **Make sure you everything in the VM from now on!**

---

## Vim

**Vim** is a text editor, a brilliant text editor. Emacs and Vim are  modernised text editors.

As long as you are in a *Unix terminal* you can run Vim. Also, if there are plugins installed you can see highlighting and extra stuff.

      Book for VIM: Practical Vim, Drew Neil

#### Features of VIM

* Vim is available everywhere where you have a shell.
* Available on remote and cloud machines
* Available on local VMs, Docker containers (Which are like VM but smaller) and etc..
* It's extremely powerful.

* It encourages DRY (Dont Repeat Yourself) in your editing/navigation.

#### To get the most out of it VIM
* Learn how to use bash properly.
* Configure it right.
* Practice, practice, practice.
* Learn to [touch type](www.typingclub.com).
* Accept you won't know it all.
* Try to learn something new every week.
* **Don't use it at work**, start by using in the evenings and weekends.
* **Don't use your mouse**, Ever!.
* **There's always a better way**, you just haven't learned it yet

* **Vim is different from everything else you've used.**

---
#### Vim Modes
1) **Normal Mode**, is for navigation so doesn't type characters and every letter has a meaning.
2) **Insert Mode**, is used for typing stuff so when you type a character it inserts it.
3) **Visual Mode**, so like selecting text with a mouse.

#### Using VIM

* `Vim .` # runs the vim command.
* `:x` # to exit.
* `vim myfile.txt` # to create a new blank file in vim.
* Command Pallet, `: ->` # which will let you run a lot of commands.
* Type `i` # to go into Insert Mode.  
* `Escape` # takes you back into Normal Mode.
* *h,j,k,l* = in Insert Mode (Left, Down, Up, Right).
* *c i )* # will get rid of everything in the bracket.
  * *c* = change.
  * *i* = inside.
  * *)* = parenthesis.

  * *}* = braces.
* *d i "*
  * *d* = delete.
  * *i* = inside.

  * *"* = speech marks.
* *u* = undo.
* *y* = cut.
* *p* = paste.
* *w* = jump to the beginning of the next word.
* *e* = jumps you to the end of the word?.
* You can repeat motions with numbers, e.g. *2w*.
* *f* = find in the current line.
* *.* = repeat motions?.
* `:w`, to save.
* `:wq`, to save and quit.

* `vimtutor`, it opens vim and has a vim tutorial in there,
try and do it everyday. It is available on anywhere.

#### Extra VIM Links

1) [Vim Adventures](vim-adventures.com).
2) [Youtube Video 1](http://youtu.be/wlR5gYd6um0).
3) [Youtube Video 2](http://youtu.be/3TX3kV3TICU).

---
