[Terminal][anchor-terminal] | [Tools][anchor-tools] | [Network][anchor-network]

[anchor-terminal]: #wiki-terminal
[anchor-tools]: #wiki-tools
[anchor-network]: #wiki-network

<a id="terminal"/>
## ![][img-terminal] Terminal

###### `IN THE BEGINNING... WAS THE COMMAND LINE`

Adapted from the [The 5-Minute Essential Shell Tutorial][link-five-minute-essential-shell-tutorial].

> _EXTREMELY SERIOUS WARNING (printed on a separate page, in red letters on a yellow background): Unless you are as smart as Johann Karl Friedrich Gauss, savvy as a half-blind Calcutta bootblack, tough as General William Tecumseh Sherman, rich as the Queen of England, emotionally resilient as a Red Sox fan, and as generally able to take care of yourself as the average nuclear missile submarine commander, you should never have been allowed near this document. Please dispose of it as you would any piece of high-level radioactive waste and then arrange with a qualified surgeon to amputate your arms at the elbows and gouge your eyes from their sockets. This warning is necessary because once, a hundred years ago, a little old lady in Kentucky put a hundred dollars into a dry goods company which went belly-up and only returned her ninety-nine dollars. Ever since then the government has been on our asses. If you ignore this warning, read on at your peril—you are dead certain to lose everything you’ve got and live out your final decades beating back waves of termites in a Mississippi Delta leper colony._

> _Still reading? Great. Now that we’ve scared off the lightweights, let’s get down to business._

Neal Stephenson, _Cryptonomicon_. 1999.

<a id="filesystem"/>
### Filesystem

* Your home directory is `~`, short for `/home/username/`
* The current directory is `.`
    * paths are relative to the current directory: `some/nested/folder/` is `./some/nested/folder/`
* a filename with a trailing slash is a `directory/`
    * it is not required
    * some commands behave differently when you use `directory` and `directory/`
* The current directory's parent is `..`
* The top directory is `/` _(filesystem root)_
    * a path with a leading slash is relative to the filesystem root: `/home/username/some/nested/folder/somefile`
* Hidden files and directories begin with a dot: `.filename`

<a id="filesystem-commands"/>
### Filesystem commands

###### Options
A command _option_ (_flag_, _switch_) is specified by a short `-o` or long `--option` name.

Short options can be combined: `-abc`.  

For some commands, options take arguments: `-i inputfile` or `--input inputfile` or `--prefix=/home/username`.

###### Tab completion
When you press the tab key, the shell tries to guess how to complete the statement you're typing.  In case of ambiguity, pressing the tab key twice shows all possible completions.

* `ls`: list contents of the current directory
    * `ls -alh`: **l**ong (detailed) list of **a**ll (including hidden) contents; file sizes converted to **h**uman-readable format
* `pwd`: **p**rint **w**orking (current) **d**irectory
* `cd`: **c**hange current **d**irectory to `~` (default)
    * `cd path/to/directory`: change current directory
* `mkdir`: **m**a**k**e (create) **dir**ectory
* `rmdir`: **r**e**m**ove (delete) **dir**ectory
* `mv`: **m**o**v**e or rename
* `cp`: **c**o**p**y file
    * `cp -r`: copy **r**ecursively (all contents of a directory)
* `rm`: **r**e**m**ove (delete)
    * `rm -r`: delete **r**ecursively (all contents of a directory)
* `touch`: create an empty file
    * if file exists, update its timestamp

### Text commands

* `cat`: print (con**cat**enate) contents to the screen
* `more`: read contents page by page
    * `spacebar` forward, `q` to quit
* `less`: read contents page by page
    * `spacebar` forward, `b` backward, `q` to quit
* `man`: read instructions (**man**ual)

###### Manpages and help
When you have questions about a command, use `man commandname` to read its documentation.  Some commands use `commandname -h` or `commandname --help`.

### System commands

* `ps`: list programs running (**p**rocess **s**tatus)
    * `ps aux`: list **a**ll programs running, with details
    * _the options for `ps` have no hyphen `-`_
* `kill`: end a program, by its process id (**pid**)
* `which`: locate a command
* `whereis`: locate a command, and related files
* `find`: recursively search files in a directory
    * `find path/to/directory -name filename`: recursively search a directory for a file
    * _the options for `find` have one hyphen `-`_
* `df -h`: show **d**isk space available on the **f**ilesystem (file sizes converted to **h**uman-readable format)
* `du -hcs`: show **d**isk space **u**sed by a directory (**s**ummarized; file sizes converted to **h**uman-readable format)
* `chmod`: **ch**ange **mod**e ([permissions][anchor-filesystem-permissions]) of a file
* `chown user:group`: **ch**ange [user and group][anchor-users-and-groups] **own**ership of a file
* `chgrp`: **ch**ange **gr**ou**p** ownership of a file

<a id="filesystem-permissions"/>
### Filesystem permissions

See also [users and groups][anchor-users-and-groups].  

###### User classes: ugo

* **u**ser: user who owns of the file
* **g**roup: group of users who may need the file
* **o**ther: any user  

###### File permissions: rwx (octal)

Each user class may be permitted to:

* **r**ead the file (4)
* **w**rite to the file (2) 
* e**x**ecute the file (1)
    * for a directory, open it  

These permissions are represented as a binary sequence of three characters: `r`, `w`, `x` for true, `-` for false.

Equivalently, use base 8:

````text
--- 0
--x 1
-w- 2
-wx 3
r-- 4
r-x 5
rw- 6
rwx 7
````

###### Setting permissions

File permissions are specified for all three user classes.

A new file has read and write (6) permission by the owner, but only read (4) permission by group and others.

````sh
touch foo
ls -l foo  # -rw-r--r-- username groupname  (644)
````

The first character `-` describes the file type (`d` for directory, `l` for link).

To add permissions, use `chmod` with `+r`, `+w`, or `+x`.  Specify user classes first (default is all, `ugo`).

````sh
chmod +x foo  # means ugo+x
ls -l foo  # -rwxr-xr-x username groupname  (755)
````

Or use octal:

````sh
chmod 764 foo  # rwxrw-r--
````





<a id="users-and-groups"/>
### Users and groups

* `whoami`: print my username
* `id`: show my user information and group memberships
* `cat /etc/passwd`: show all users
* `cat /etc/group`: show all groups

<a id="tools"/>
## ![][img-tools] Tools

### grep

###### See also
[ack][link-ack]

### sed

<a id="network"/>
## ![][img-network] Network

### Network commands

Configure [SSH][anchor-ssh].

* `ssh`
* `scp`
* `rsync`


[anchor-filesystem-permissions]: #wiki-filesystem-permissions
[anchor-ssh]: Security#wiki-ssh
[anchor-users-and-groups]: #wiki-users-and-groups

[img-terminal]: image/gnome-terminal.png "Terminal"
[img-tools]: image/gconfeditor.png "Tools"
[img-network]: image/folder-remote.png "Network"

[link-ack]: http://betterthangrep.com/
[link-epiphyte-corp]: http://www.euskalnet.net/larraorma/crypto/slide28.html
[link-five-minute-essential-shell-tutorial]: http://community.linuxmint.com/tutorial/view/100
[link-in-the-beginning]: http://en.wikipedia.org/wiki/In_the_Beginning..._Was_the_Command_Line