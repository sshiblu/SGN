alt and f2 = new terminal
pwd = what folder we are in
ls = all the folders in the directory
cd = change directory
/ is root
~ (tilda) = homefolder 
unix is case sensitive

ls (-)l= flag used to modify the way a command works

-l= shows more information on the files using the flag 

ls -a = a flag stands for all means show everything in the folder including hidden files

combine flags like -al = show more information of folders hidden and unhidden

man = manual on command, its an independent program not a command or google man page

absolute or relative path long or short

cd .. = next folder up

. = current folder

cp = copy file, first bit you want to copy then new name, copy and paste
if you dont provide a new name but new location with new name,
if new location which doesnt exist renames it to the new location name, make sure location exists

mv = moves folder to new location, cut and paste 

rm = removes file
rm -r = recurse over stuff inside and delete all of them, delete directive and its child directives
rm -fr= recurse and force deletion of stuff inside

touch = after command space then creates file with name you give
mkdir = creates a new directory in the folder you are in

stdin (standard input), information input into the terminal through keyboard or input device
stdout (standard output), information outputted after a process is run
stderr (standard error), is an error message outputted by a failed process

echo = spits string it back at you
(redirect) > = it takes the output of whatever you put before and then stores it in a file at that location
echo "hello" > my file = stores string in that file
>> = takes stdout of the command on left and adds to the file on the right. So it has two files worth of information 
< = means stdin of file on the right goes to whatever command on the left. 
wc = outputs the number of lines, words and characters.
| (piped) = takes the stdin of the command on the left and pipes as stdin to the command on the right, like command to command redirection 
sort = takes the stdin orders it alphabetically for stdout
cat = outputs the contents of a file to the terminal
uniq (unique) = filters out duplicate and adjacent (one line below or above) lines in a file
better way to use uniq would be to use sort beforehand

grep (global regular expression print) = searches files for lines that match a pattern and returns the result, it is case sensitive
so grep Mount mountains.txt returns lines that have Mount in it
grep -i Mount mountains.txt, makes the grep command case insensitive
grep -R, searches all files in a directory and outputs file names and the line that have a matched result
grep -Rl, (-l being used to find 'files with matches') searches directory for the string and outputs the file names only   

sed (stream editor), accepts stdin and modifies it based it on an expression before displaying it as output data, similar to 'find and replace'
sed s, 's' stand for substition and is always used with sed for substitution
sed 's/snow/rain/', searces for the string snow and replaces it with rain, only replaces the first instance of snow on a line
sed 's/snow/rain/g', searches for the string snow globally and replaces all instants of it with rain 

File extensions dont mean shizzle to unix!
Dont learn vim now but do it later
cd "heelo i" = creates folders with spaces
cd heelo\ i = changes to the folder need to slash because of folder
touch one two three = creates 3 files
mv folder2/my_pathtxct folder2/my_path.txt use mv to rename


Globbing basically using wildcards
ls -l *.txt = looks for anything .txt
ls f*f= looks for stuff starting and ending with an f
mv folder2/*.txt ~ = move all text files in folder 2 and store in root

Soft keys equal shortcuts
ln -s project/folder2/my_path.txt . = link symbols so creates link to current directory

whoami = tells you which user you are currently logged in as 
groups = the groups you are in
chown = change ownership
r = read
w = write
x = execute
-rw- ,so cant be executed as x is not there


Simple file permissions
chmod o-r three , takes away the right to read on file three
chmod u+x three, enables the user to execute the file
chmod uog+rwx three, enables everything
chmod 777 four, enables everything

u = user
g = group

su = puts you into a new shell as a root user, dont do it
exit = to log out

Sudo, executes as root

sudo touch /fooo = creates file in root using roots permission

ssh 'host name or ip address' = puts you in a remote secure server
putty for windows

.files, hidden files ussually live in your home directory also are configuration files
pink colour files means links or shortcuts

Use nano
ctrl + o = save
ctrl + x = exit
clear = move the ish up so the terminal is clear
source = activates changes in the file, makes the changes available right away in the session we are in
put in echo "The changes have been made"
alias pd="pwd"
alias hy="history"
alias ll="ls -la"
alias rm="rm-1" = asks you are you sure you want to delete it using flag

Enviornment variables
export USER="Shorof", set environment variable USER to a name, 
export makes the variable be available to all child sessions initated from the session you are in. Its a way to make the variable persist across programs.
echo $user, returns the value  of the variable
export PS1=">> ", PS1 is a variable that defines the makeup and style of the command prompt, so changes from $ to >>
echo $HOME = Displays the path of the home directory, dont really need to change HOME
echo $PATH = stores a list of directories seperated by a colon, each directory contains scripts for the command line to execute, 
the PATH variable simply lists which directories contain scripts
most of the command are kept in bin so (bin/pwd = pwd)
env (environment) = returns a list of the enviroment variables for the current user
By using env | grep PATH, displays the value of a single enviroment variable which is PATH and outputs it to the terminal

-----------------------------------------------------------------------------------

Commiting is a two stage process

git add
git commit

Configure git:

Use this command: $ git config --global user.name "Shorof Shiblu"

Set email $ git config --global user.email shorof.uddin22@gmail.com

color ui = true 
make the color log come true

git init , makes my folder into a git repository, only need to use it once
dont make it in a stupid place. Make sure its in the correct depository. 
Delete .git file is you dont want to make it a repository. 

git add . , add everything in the current directory can add only one folder
git status, tells us where we are at
git commit -m "created hello text file", why we changed it 

git diff, can only show the difference between the previous commit and 
the files that is knows about

git status (use), the changes to be commited

git diff --staged, shows the difference and its stages

git log, shows you the log with a commit like a barcode

git log --oneline, shows the reason and part of the commit

git log --online --graph, shows branches

git log --online --graph --decorate, shows branches and decorates

git checkout . (ctrl z), discard change in working directory back to our last
commit

git remote add origin https://github.com/sshiblu/myproject, after making 
new repository make sure it has the same name

git push -u origin master, -u, sets the remote as origin and branch as 
master as standard
git reset --hard HEAD^, rolls us back to the previous commit 
and all the changes are lost
git reset --soft HEAD^, rolls us back to the previous commit, all the changes
are kept because of the soft
or git reset --soft HEAD~4, rolls us back to the fourth commit back
touch

git commit --ammend -m "Added new files 1 and 2", it will overwrite the message

All local for now

--------------------------------------------------------------------------------

shift + ins , in windows to paste
clone . . . go to git hub find the url of the project then
git clone https://github.com/dannysmith/guard-shopifythem.gitls
clone, brings down the files
git diff f7757fd b734eaa, find the difference using the char # 

#, in bash is comments

git push, push stuff up to some sort of remote

git remote -v, first bit is the name of the remote, second bit is the server
the end point

its just convention to say origin

git push origin master, push up to the remote origin and the branch is master

SHA key, so dont have to log in often

------------------------------------------------------------------------------

Git, markdown 

Print Git Cheat Sheet
Fork, making your own copy of someone elses work, only on GitHub
Pull requests are also only a GitHub invention
Bit Bucket

git commit --ammend "new note"

Branching allows us to manage conflicts, branching then merging
Allowing us to work collaboratively

git branch new-branch, creates a new branch
git branch, list of branches,* the branch we are on
git checkout new-branch, switch to new branch
git log --pretty=oneline --all --graph --decorate
git log --oneline --all --graph --decorate, all = all the branches

[]master shows us which branch we are on
When the colour changes from green to red, it means there are changes in the
working directory

git checkout master, go back to master branch
Changes may not be seen becuase they are in another branch

Merging

Fast-forward merge, copies commits across from branch to branch, 
cant do if commits clash from the branch to the master,
the head point the commit to the master

Recursive merge

git merge "new-branch" master -m "initial merge"
If you delete branch, the commits that have been combined and merged will 
not have the history

git reset will delete commit if you want it to
git reset --hard Head^, undo last merge
git branch -d new-branch, deletes new branch

Run merges locally to solve manual conflicts!, this is what sets GitHub apart

1) Git Rebase,
Move any commits in the current branch to a temporary area
Run all commits from the other branch against the current branch
Run all of the commits from the temp area on top of those from previous branch

2) Recursive rebase h/w, git interactive rebase
allow you to squish commit, such as typos with comments

Git Pull Requests

Can make a pull request within 2 forks, can use pull requests to get someone to
check your code.

Pull Request is a Github thing that tracks the branch, so the commits, so see the 
development work happen as its going on.

Hound, searches for error and inconsistencies 

Codeship, tracks the pull request, continous integration platform, 
runs regression tests tells you if you have broken stuff.

Maybe look into git stash when you need it. 

How git works (optional):
https://youtu.be/SiokK8Q1wo0

Turn them all into collaborators, so they can fork or merge to fix up my notes 

-----------------------------------------------------------------------------------

clear = clear the terminal

when you turn the pc on, use vagrant up again
vagrant halt to turn off the VM

Tasharns help on aliases 
When writing aliases to go somewhere its a good idea to start from home directory
