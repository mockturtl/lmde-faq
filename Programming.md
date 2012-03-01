## IDE

### ![][img-geany] [Geany][homepage-geany]

##### Setup

Geany is available in the debian repositories.

`apt install geany`

[community][community-geany]

### ![][img-idea] [IDEA][homepage-idea]

##### Setup

[Download][link-idea] the Community Edition.  Unpack the source and link the executable in your PATH.

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

## Virtualization

### ![][img-virtualbox] [Virtualbox][homepage-virtualbox]

##### Setup

[community][community-virtualbox]

### ![][img-vmware] [VMware Player][homepage-vmware]

##### Setup

## Languanges

### ![][img-java] [Java][homepage-java] <a id="java" />

##### Setup

Java is available in the debian repositories.

`apt install openjdk-7-jdk`

Your `~/.bashrc` should include the following line:

````sh
export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-i386 # Or openjdk-amd64
````

###### Links

* [Play][link-play], a framework for web applications

### ![][img-python] [Python][homepage-python] <a id="python" />

##### Setup

Python is installed by default.  The Python package manager is **pip**.

`apt install python-pip`

###### Links

* [Django][link-django], a framework for web applications

### ![][img-ruby] [Ruby][homepage-ruby]

##### Setup

Ruby is available in the debian repositories, but use [RVM][link-rvm] instead.  The language evolves quickly, and programs may depend on a particular version.  After installation, your `~/.bashrc` should include the following line:

````sh
[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM
````

Ruby modules are called **gems**.  The Ruby package manager is **rubygems**.  Dependencies for a particular ruby app are listed in its `Gemfile` and installed with **bundler**.

###### Links

* [Rails][link-rails], a framework for web applications

## Version / Revision / Source control

### ![][img-git] [Git][homepage-git]

##### Setup

Git is available in the debian repositories.

`apt install git`

The config file is `~/.gitconfig`.

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
[color]
	status = auto
	branch = auto
````

### ![][img-subversion] [Subversion][homepage-subversion] <a id="subversion" />

Subversion is available in the debian repositories.

`apt install subversion`

[anchor-java]: Programming#wiki-java

[community-geany]: http://community.linuxmint.com/software/view/geany
[community-idea]: http://community.linuxmint.com/software/view/idea-ic
[community-netbeans]: http://community.linuxmint.com/software/view/netbeans
[community-vim]: http://community.linuxmint.com/software/view/vim
[community-virtualbox]: http://community.linuxmint.com/software/view/virtualbox-4.1

[homepage-geany]: http://www.geany.org/
[homepage-git]: http://git-scm.com/
[homepage-idea]: http://www.jetbrains.org/
[homepage-java]: http://docs.oracle.com/javase/tutorial/
[homepage-netbeans]: http://www.netbeans.org/
[homepage-python]: http://docs.python.org/tutorial/
[homepage-ruby]: http://www.ruby-lang.org/en/documentation/quickstart/
[homepage-subversion]: http://subversion.apache.org/
[homepage-vim]: http://www.vim.org/
[homepage-virtualbox]: https://www.virtualbox.org/
[homepage-vmware]: http://www.vmware.com/products/player/

[img-geany]: image/geany.png "Geany"
[img-git]: image/git.png "Git"
[img-idea]: image/idea.png "IDEA"
[img-java]: image/java.png "Java"
[img-netbeans]: image/netbeans.png "Netbeans"
[img-python]: image/python.png "Python"
[img-ruby]: image/ruby.png "Ruby"
[img-subversion]: image/subversion.png "Subversion"
[img-vim]: image/vim.png "Vim"
[img-virtualbox]: image/virtualbox.png "Virtualbox"
[img-vmware]: image/vmware.png "VMware"

[link-django]: https://www.djangoproject.com/
[link-idea]: http://www.jetbrains.com/idea/download/index.html
[link-play]: http://www.playframework.org/
[link-rails]: http://rubyonrails.org/
[link-rvm]: http://beginrescueend.com/rvm/install/ "Ruby enVironment Manager"
[link-snipmate]: http://www.vim.org/scripts/script.php?script_id=2540