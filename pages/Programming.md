[IDE][anchor-ide] | [Virtualization][anchor-virtualization] | [Languages][anchor-languages] | [Source control][anchor-source-control] | [Databases][anchor-databases]

[anchor-databases]: #wiki-databases
[anchor-ide]: #wiki-ide
[anchor-languages]: #wiki-languages
[anchor-virtualization]: #wiki-virtualization
[anchor-source-control]: #wiki-source-control


<a name="ide"/>
## IDE _(Integrated Development Environment)_

### ![][img-geany] [Geany][homepage-geany]

##### Setup

Geany is available in the debian repositories.

`apt install geany`

[community][community-geany]

### ![][img-idea] [IDEA][homepage-idea]

##### Setup

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

[Download][link-idea] the Community Edition.  Unpack the source and symlink the executable.

````sh
sudo tar xvzf path/to/downloaded/file.tar.gz /opt/
sudo ln -s /opt/idea-IC-x.y/bin/idea.sh /usr/local/bin
````

See [this note][anchor-java] on defining the `$JAVA_HOME` environment variable.

[community][community-idea]

### ![][img-netbeans] [Netbeans][homepage-netbeans]

##### Setup

Netbeans is available in the debian repositories.

`apt install netbeans`

[community][community-netbeans]

### ![][img-vim] [Vim][homepage-vim]

##### Setup

Vim is available in the debian repositories.

`apt install vim`

The config file is `~/.vimrc`.

````vim
syntax on               # syntax highlighting
set background=dark     # bright colors for a black terminal background
:set expandtab          # tab size
:set tabstop=2
:filetype plugin on     # snipMate plugin, see below
````

###### Plugins

* [snipMate][link-snipmate]: tab-completed snippets

[community][community-vim]

###### See also

* [gmate][link-gmate]

<a name="virtualization"/>  
## Virtualization

### ![][img-virtualbox] [Virtualbox][homepage-virtualbox]

##### Setup

[community][community-virtualbox]

### ![][img-vmware] [VMware Player][homepage-vmware]

##### Setup

<a name="languages" />
## Languanges

<a name="java" />
### ![][img-java] [Java][homepage-java] 

##### Setup

Java is available in the debian repositories.

`apt install openjdk-7-jdk`

Your `~/.bashrc` should include the following line:

````sh
export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-i386 # Or openjdk-amd64
````

###### Links

* [Play][link-play], a framework for web applications

<a name="python" />
### ![][img-python] [Python][homepage-python] 

##### Setup

Python is installed by default.  The Python package manager is **pip**.

`apt install python-pip`

###### Links

* [Django][link-django], a framework for web applications

<a name="ruby"/>
### ![][img-ruby] [Ruby][homepage-ruby]

Ruby modules are called **gems**.  The Ruby package manager is [**rubygems**][link-rubygems].  

##### Setup

Ruby is available in the debian repositories, but use [RVM][link-rvm] instead.  The language evolves quickly, and programs may depend on a particular [interpreter][link-ruby-interpreters] version.

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

After installation, your `~/.bashrc` should include the following line:

````sh
[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM
````

###### Links

* [Rails][link-rails], a framework for web applications

<a name="source-control"/>
## Version / Revision / Source control

### ![][img-git] [Git][homepage-git]

If you're familiar with version control systems, see [Why Git is Better than X][link-whygitisbetterthanx].  Otherwise, you may find Tom Preston-Werner's [Git Parable][link-git-parable] helpful.

To learn how git works, watch Scott Chacon's [talk][link-schacon-git-talk] from RailsConf 2008, and Tom Preston-Werner's "[Mastering Git Basics][link-tpw-git-talk]."  

For tutorials, see [github bootcamp][link-github-help], [gitcasts][link-gitcasts], [Carl Worth's tour][link-cworth-tour], and [git ready][link-git-ready].  Mind best practices for [commits][link-git-commit-messages], [branching][link-git-branching], [rebasing][link-git-rebasing], and [tagging][link-git-tags].



Free repository hosting and project management are available from [github][link-github] and [bitbucket][link-bitbucket].

##### Setup

Git is available in the debian repositories.

`apt install git`

Set options and aliases with `git config --global` (for all projects), or edit `~/.gitconfig` directly.

````text
[user]
	name = Your Name
	email = somebody@somewhere.com
[alias]
	co = checkout
	st = status
	lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
	ci = commit
	br = branch
	ri = rebase --interactive
	av = add --verbose
[color]
	status = auto
	branch = auto
[rebase]
	autosquash = true
````

Download the [tab completion][link-git-completion] script to your home directory, and add this line to `~/.bashrc`:

````sh
source ~/git-completion.bash  # Git tab completion
````

###### [Syntax note][link-git-revisions]

There are two commit history operators: the which-parent selector `^` _(caret)_ defaults to `^1`, for the ordinary case a commit has only one parent.  In case of a merge, `^N` indicates which branch to follow.

_The ordering of a commit's parents is taken from the arguments to `merge`.  View them with `show`._

The go-back operator `~` _(tilde)_ is read "first parent," or "grassy knoll," and acts like a power function: `A~~~` or `A~3` describes the (leftmost) great-grandparent of `A`.  

Operators compose left-to-right by walking the tree.

````text
G   H   I   J
 \ /     \ /
  D   E   F
   \  |  / \
    \ | /   |
     \|/    |
      B     C
       \   /
        \ /
         A
A =      = A^0
B = A^   = A^1     = A~1
C = A^2  = A^2
D = A^^  = A^1^1   = A~2
E = B^2  = A^^2
F = B^3  = A^^3
G = A^^^ = A^1^1^1 = A~3
H = D^2  = B^^2    = A^^^2  = A~2^2
I = F^   = B^3^    = A^^3^
J = F^2  = B^3^2   = A^^3^2
````

<a name="subversion" />
### ![][img-subversion] [Subversion][homepage-subversion] 

Subversion is available in the debian repositories.

`apt install subversion`




<a name="databases"/>
## Databases

### ![][img-mysql] [MySQL][homepage-mysql]

#### Setup

MySQL is available in the debian repositories.

`apt install mysql-server`

### ![][img-postgresql] [PostgreSQL][homepage-postgresql]

#### Setup

PostgreSQL is available in the debian repositories.

`apt install postgresql`

### ![][img-sqlite] [SQLite][homepage-sqlite]

#### Setup

SQLite is available in the debian repositories.

`apt install sqlite3`


[anchor-java]: #wiki-java
[anchor-python]: #wiki-python

[community-geany]: http://community.linuxmint.com/software/view/geany
[community-idea]: http://community.linuxmint.com/software/view/idea-ic
[community-netbeans]: http://community.linuxmint.com/software/view/netbeans
[community-vim]: http://community.linuxmint.com/software/view/vim
[community-virtualbox]: http://community.linuxmint.com/software/view/virtualbox-4.1

[emblem-warn]: image/emblem-warn.png "Warning!"

[homepage-geany]: http://www.geany.org/
[homepage-git]: http://git-scm.com/
[homepage-idea]: http://www.jetbrains.org/
[homepage-java]: http://docs.oracle.com/javase/tutorial/
[homepage-mysql]: http://www.mysql.com/
[homepage-netbeans]: http://www.netbeans.org/
[homepage-postgresql]: http://www.postgresql.org/
[homepage-python]: http://docs.python.org/tutorial/
[homepage-ruby]: http://www.ruby-lang.org/en/documentation/quickstart/
[homepage-sqlite]: http://www.sqlite.org/
[homepage-subversion]: http://subversion.apache.org/
[homepage-vim]: http://www.vim.org/
[homepage-virtualbox]: https://www.virtualbox.org/
[homepage-vmware]: http://www.vmware.com/products/player/

[img-geany]: image/geany.png "Geany"
[img-git]: image/git.png "Git"
[img-idea]: image/idea.png "IDEA"
[img-java]: image/java.png "Java"
[img-mysql]: image/mysql.png "MySQL"
[img-netbeans]: image/netbeans.png "Netbeans"
[img-postgresql]: image/postgresql.png "PostgreSQL"
[img-python]: image/python.png "Python"
[img-ruby]: image/ruby.png "Ruby"
[img-sqlite]: image/sqlite.png "SQLite"
[img-subversion]: image/subversion.png "Subversion"
[img-vim]: image/vim.png "Vim"
[img-virtualbox]: image/virtualbox.png "Virtualbox"
[img-vmware]: image/vmware.png "VMware"

[link-bitbucket]: https://bitbucket.org/
[link-cworth-tour]: http://cworth.org/hgbook-git/tour/
[link-django]: https://www.djangoproject.com/
[link-git-branching]: http://blog.hasmanythrough.com/2008/12/18/agile-git-and-the-story-branch-pattern
[link-git-commit-messages]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[link-git-completion]: https://raw.github.com/git/git/master/contrib/completion/git-completion.bash
[link-git-parable]: http://tom.preston-werner.com/2009/05/19/the-git-parable.html
[link-git-ready]: http://gitready.com/
[link-git-rebasing]: http://reinh.com/blog/2009/03/02/a-git-workflow-for-agile-teams.html
[link-git-revisions]: http://schacon.github.com/git/git-rev-parse.html#_specifying_revisions
[link-git-tags]: http://gitref.org/branching/#tag
[link-gitcasts]: http://gitcasts.com/
[link-github]: https://github.com
[link-github-help]: http://help.github.com/
[link-gmate]: https://github.com/gmate/gmate
[link-idea]: http://www.jetbrains.com/idea/download/index.html
[link-play]: http://www.playframework.org/
[link-rails]: http://rubyonrails.org/
[link-ruby-interpreters]: https://rvm.beginrescueend.com/rubies/installing/
[link-rubygems]: http://rubygems.org/
[link-rvm]: http://beginrescueend.com/rvm/install/ "Ruby enVironment Manager"
[link-schacon-git-talk]: https://encrypted.google.com/search?q=scott+chacon+git+talk
[link-snipmate]: http://www.vim.org/scripts/script.php?script_id=2540
[link-tpw-git-talk]: http://vimeo.com/17118008
[link-whygitisbetterthanx]: http://whygitisbetterthanx.com/