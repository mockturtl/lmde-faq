[Terminal][anchor-terminal] | [File permissions][anchor-filesystem-permissions] | [Users and groups][anchor-users-and-groups] | [Updates][anchor-updates] | [Tools][anchor-tools] | [Network][anchor-network]

[anchor-filesystem-permissions]: #wiki-filesystem-permissions
[anchor-network]: #wiki-network
[anchor-terminal]: #wiki-terminal
[anchor-tools]: #wiki-tools
[anchor-updates]: #wiki-updates
[anchor-users-and-groups]: #wiki-users-and-groups

<a name="terminal"/>
## ![][img-terminal] Terminal

###### `IN THE BEGINNING... WAS THE COMMAND LINE`

Adapted from the [The 5-Minute Essential Shell Tutorial][link-five-minute-essential-shell-tutorial].

> _EXTREMELY SERIOUS WARNING (printed on a separate page, in red letters on a yellow background): Unless you are as smart as Johann Karl Friedrich Gauss, savvy as a half-blind Calcutta bootblack, tough as General William Tecumseh Sherman, rich as the Queen of England, emotionally resilient as a Red Sox fan, and as generally able to take care of yourself as the average nuclear missile submarine commander, you should never have been allowed near this document. Please dispose of it as you would any piece of high-level radioactive waste and then arrange with a qualified surgeon to amputate your arms at the elbows and gouge your eyes from their sockets. This warning is necessary because once, a hundred years ago, a little old lady in Kentucky put a hundred dollars into a dry goods company which went belly-up and only returned her ninety-nine dollars. Ever since then the government has been on our asses. If you ignore this warning, read on at your peril—you are dead certain to lose everything you’ve got and live out your final decades beating back waves of termites in a Mississippi Delta leper colony._

> _Still reading? Great. Now that we’ve scared off the lightweights, let’s get down to business._

Neal Stephenson, _Cryptonomicon_. 1999.

<a name="filesystem"/>
### Filesystem

* Your home directory is `~`, short for `/home/username/`
* The current directory is `.`
    * paths are **relative** to the current directory: `some/nested/folder/` is `./some/nested/folder/`
* a filename with a trailing slash is a `directory/`
    * it is not required
    * some commands behave differently when you use `directory` and `directory/`
* The current directory's parent is `..`
* The top directory is `/` _(filesystem root)_
    * a path with a leading slash is **absolute** (i.e., relative to the filesystem root): `/home/username/some/nested/folder/somefile`
* Hidden files and directories begin with a dot: `.filename`

<a name="filesystem-commands"/>
### Filesystem commands

###### Options
A command _option_ (_flag_, _switch_) is specified by a short `-o` or long `--option` name.

Short options can be combined: `-abc`.  

For some commands, options take arguments: `-i inputfile` or `--input inputfile` or `--prefix=/home/username`.

###### Tab completion
When you press the `tab` key, the shell tries to guess how to complete the statement you're typing.  In case of ambiguity, pressing the `tab` key twice shows all possible completions.

###### Basic commands
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
* `df -h`: show **d**isk space available on the **f**ilesystem (file sizes converted to **h**uman-readable format)
* `du -hcs`: show **d**isk space **u**sed by a directory (**s**ummarized; file sizes converted to **h**uman-readable format)
* `uptime`: display system statistics since last reboot

###### Program execution

* `ctrl+c`: abort the program
* `ctrl+d`: send `EOF` to a program waiting on input
* `ctrl+z`: send a program to the background, to provide input elsewhere
    * `fg` to resume the program
    * `commandname &` starts a program in the background

###### Text commands

* `echo`: print a string to the screen, followed by newline character `\n`
* `cat`: print (con**cat**enate) file contents to the screen
* `head -n 1`: print the first line of a file to the screen
* `tail -n 5`: print the last 5 lines of a file to the screen
    * `tail -f logfile`: stream `logfile` to the screen as it is written (**f**ollow the tail)
    * _use `ctrl+c` to abort_
* `more`: read contents page by page
    * `spacebar` forward, `q` to quit
* `less`: read contents page by page
    * `spacebar` forward, `b` backward, `q` to quit
* `wc`: **w**ord **c**ount; print number of newlines, words, bytes, and characters
* `tr '[a-z]' '[A-Z]'`: **tr**anslate a string to upper case

###### Manpages and help
When you have questions about a command, use `man commandname` to read its documentation  (**man**ual).  Some commands use `commandname --help` or `commandname -h`.

### Advanced commands
* `find`: recursively search in a directory
    * `find path/to/directory -name filename`: recursively search a directory for a file
    * _the options for `find` have one hyphen `-`_
* `chmod`: **ch**ange **mod**e ([permissions][anchor-filesystem-permissions]) of a file
* `chown user:group`: **ch**ange [user and group][anchor-users-and-groups] **own**ership of a file
* `chgrp`: **ch**ange **gr**ou**p** ownership of a file

###### System

* `ps`: list programs running (**p**rocess **s**tatus)
    * `ps aux`: list **a**ll programs running, with details
    * _some options for `ps` have no hyphen `-`_
* `kill`: end a program, by its process id (**pid**)
* `which`: locate a command
* `whereis`: locate a command, and related files

###### Compression  

Zip, gzip and bzip2 are compression formats.  

* `unzip path/to/file.zip` extract the zip archive to the current directory
* `zip output file1 file2 ...` create an archive named `output.zip`

Historically, cassette tapes were used for backups.  _Hyphens `-` are optional for `tar` options._  

* `tar`: **t**ape **ar**chive
    * `tar xvzf path/to/downloaded/file.tar.gz` e**x**tract the g**z**ipped **f**ile to the current directory with **v**erbose output
    * `tar xjf path/to/downloaded/file.tar.bz2` e**x**tract the bzipped **f**ile to the current directory
        * _why `j` for bzip2 compression? `b` is for block size_
   * `tar czf output.tar.gz directory/` **c**reate and g**z**ip an archive named `output.tar.gz` from `directory/`


<a name="filesystem-permissions"/>
## File permissions

###### See also 
* [Users and groups][anchor-users-and-groups]  

###### User classes: ugo

* **u**ser: user who owns the file
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
chmod 764 foo  # -rwxrw-r--
````





<a name="users-and-groups"/>
## Users and groups

### User commands

* `whoami`: print my username
* `id`: show my user information and group memberships
* `cat /etc/passwd`: show all users
* `cat /etc/group`: show all groups

<a name="updates"/>
## ![][img-updates] Updates

### Repositories

Adapted from the [LMDE FAQ][link-lmde-faq].

TODO

### ![][img-mint-update] Update Manager

Graphical front-end for `apt`.  An icon in the system tray notifies you when updates are available.  

[community][community-mintupdate]

###### apt

Wrapper script for `apt-get`, `aptitude`, `apt-cache` and `dpkg`, providing cleaner syntax.  See `/usr/local/bin/apt` for details.

_Tab completion does not work with the `apt` script._

* `apt policy` prints the installed and available versions of a package
* `apt show` prints package details
* `apt search` finds a matching package by name
* `apt build` compiles a source package to a `.deb` file
* `apt update`, `apt upgrade`, `apt dist-upgrade`: see below

### ![][img-synaptic] [Synaptic][homepage-synaptic]

Graphical interface for APT.  See below.

[community][community-synaptic]

### apt-get, aptitude

Command-line interfaces for debian's Advanced Packaging Tool (APT), which manages package installation by retrieving dependencies and resolving conflicts.

* `apt-get update` or `aptitude update` refreshes the list of available packages

If newer packages are available,  

* `apt-get upgrade` installs available packages that do not require other packages to be added or removed from the system
* `aptitude safe-upgrade` installs available packages that do not require other packages be removed from the system
    * adds new packages as necessary
* `apt-get dist-upgrade` or `aptitude full-upgrade` installs all available packages
    * prompts for confirmation if packages will be removed

_With large updates, you may find `aptitude` too slow._

###### gdebi

Graphical installer for `.deb` files.

###### dkpg

Command-line tool for installing `.deb` files.


<a name="tools"/>
## ![][img-tools] Tools

### Pipes 

Use `|`  _(pipe)_ to pass the output of `command1` to the input of `command2`.

###### example

Count the words in _hello world_:

````sh
echo -n 'hello world' | wc  # 0 newlines      2 words      11 bytes
````

### [grep][link-grep] _(global regex print)_

Powerful text search.

* `grep -nr expression directory/`: **r**ecursively search for any line containing `expression`, printing line **n**umbers
    * `expression` can be a string, or a pattern _([regular expression][link-regex])_

###### examples

````sh
ps aux | grep firefox  # is firefox running?
````

###### see also

[ack][link-ack] is configured for source code directories, with whitelist filtering.  See `--help-types`.
 
`apt install ack-grep`

The config file is `~/.ackrc`.  To search [this repository][anchor-source], add the lines below.

````sh
--type-add=svg=.svg  # scalable vector graphics
--type-add=markup=.md,.markdown,.mkdn,.textile,.rst  # rich text formats
--nosvg  # disable SVG to avoid false positives with numeric strings
````

### [sed][link-sed]  _(**s**tream **ed**itor)_

Powerful find and replace. 

* `sed -i 's/exp1/exp2/g' file1 file2 ...`: reading each `file`, line by line, 
    * `exp1, exp2` are [regular expressions][link-regex]
    * **s**ubstitute `exp2` for `exp1`
    * **g**lobally (otherwise, only the first match)
    * `-i`: edit **i**n-place, rather than printing the output


### [Redirection][link-redirection]

Typing on the keyboard writes to a _filestream_ called `stdin` (**st**an**d**ard **in**put), `0<`.

Printing to the display is called `stdout` (**out**put), `1>`.

Any **err**or messages are sent to a separate stream called `stderr`, `2>`.

###### output

* `command > file` _redirects_ `stdout`: output is logged to `file` instead of printed to the display
    * `>` is short for `1>`
    * if `file` exists, it is **overwritten**

The error stream is still printed to the screen.  To log errors also,  

* `command &> file`
    * short for `command > file 2>&1` 
        * _`stderr` is redirected to `stdout`, which you sent to `file`_

A variation:  

* `command >> file` redirects `stdout`
    * if `file` exists, output is **appended**

As above, `command &>> file` appends output and errors.

###### input

* `command < file` redirects `stdin`: input is taken from `file` instead of the keyboard
    * `<` is short for `0<`
    * `command < input.text > output.log` takes input from the first file and writes output to the second file

###### example 

Display file contents in upper case.

````sh
echo 'one two three' 1> numbers
cat numbers  # one two three
tr '[a-z]' '[A-Z]' 0< numbers  # ONE TWO THREE
````

###### Here documents

* `command <<HERE` reads input line by line, terminating when it finds `HERE`
    * `<<-HERE` with a hyphen `-` discards indentation
    * _the delimiter `HERE` can be any word: `EOF`, `END`, ..._

````sh
tr '[a-z]' '[A-Z]' <<stop
> first
> second
> third
> stop  # FIRST SECOND THIRD
````

<a name="network"/>
## ![][img-network] Network

### Network commands

Configure [SSH][anchor-ssh].  You should have an account on each computer.

* `ssh hostname`: **s**ecure login in a remote terminal _(**sh**ell)_

###### copying files

* `scp`: transfer files over the network _(**s**ecure **c**o**p**y)_
    * encrypted `rcp` _(**r**emote **c**o**p**y)_
    * `scp hostname1:/path/to/file hostname2:/path/to/destination`
    * copies `file` from one computer to another
    * local filesystem is used if either `hostname:` is omitted
        * `scp -r hostname:~/blog/drafts .`: copy the `drafts` directory and its contents (**r**ecursively) to the current directory
* `rsync`: backup (**r**emotely **sync**hronize) a directory
    * local filesystem is used if either `hostname:` is omitted
        * `rsync -a ~/Pictures /media/mountname`: backup `Pictures` to another hard drive
        * in **a**rchive mode _(**r**ecursive, copy sym**l**inks, preserving **p**ermissions, **t**imestamp, **o**wner and **g**roup)_
        * _ignore warnings if `mountname` is an NTFS partition (no notion of file permissions, etc.)_

Between computers:

* `rsync -av hostname1:/path/to/source hostname2:/path/to/destination`
    * if folder does not exist, copy it
        * otherwise, update contents of `destination`
    * with **v**erbose output
    * if `source/` has a trailing slash, its _contents_ are placed into `destination`
    
###### tcp / ip  

**I**nternet **P**rotocol finds a [route][link-ccna-ip] to deliver messages.  **T**ransmission **C**ontrol **P**rotocol guarantees their integrity.

* `nc`
* `wget`
* `curl`
* [httpie][link-httpie]
    * `sudo pip install -U httpie`  ([setup python][anchor-python])
* `whois`


[anchor-python]: Programming#wiki-python
[anchor-source]: Home#wiki-source
[anchor-ssh]: Security#wiki-ssh


[community-mintupdate]: http://community.linuxmint.com/software/view/mintupdate
[community-synaptic]: http://community.linuxmint.com/software/view/synaptic

[homepage-synaptic]: http://www.nongnu.org/synaptic/

[img-mint-update]: image/mint-update.png "mintUpdate"
[img-network]: image/folder-remote.png "Network"
[img-synaptic]: image/synaptic.png "Synaptic"
[img-terminal]: image/gnome-terminal.png "Terminal"
[img-tools]: image/gconfeditor.png "Tools"
[img-updates]: image/system-software-update.png "Updates"


[link-ack]: http://betterthangrep.com/
[link-ccna-ip]: http://www.youtube.com/watch?v=UXN5XrmsaV8
[link-five-minute-essential-shell-tutorial]: http://community.linuxmint.com/tutorial/view/100
[link-grep]: http://en.wikipedia.org/wiki/Grep
[link-sed]: http://www.grymoire.com/Unix/Sed.html
[link-httpie]: https://github.com/jkbr/httpie
[link-lmde-faq]: http://forums.linuxmint.com/viewtopic.php?f=197&t=91405#p525343
[link-redirection]: http://www.gnu.org/software/bash/manual/bashref.html#Redirections
[link-regex]: http://www.zytrax.com/tech/web/regex.htm