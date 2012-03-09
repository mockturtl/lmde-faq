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

<a id="java" />
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

<a id="python" />
### ![][img-python] [Python][homepage-python] 

##### Setup

Python is installed by default.  The Python package manager is **pip**.

`apt install python-pip`

###### Links

* [Django][link-django], a framework for web applications

### ![][img-ruby] [Ruby][homepage-ruby]

Ruby modules are called **gems**.  The Ruby package manager is **rubygems**.  Dependencies for a particular app are listed in its `Gemfile`, installed with **bundler**, and executed with **rake**.

##### Setup

Ruby is available in the debian repositories, but use [RVM][link-rvm] instead.  The language evolves quickly, and programs may depend on a particular [interpreter][link-ruby-interpreters] version.

After installation, your `~/.bashrc` should include the following line:

````sh
[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM
````

###### Links

* [Rails][link-rails], a framework for web applications

## Version / Revision / Source control

### ![][img-git] [Git][homepage-git]

To learn how git works, watch Scott Chacon's [talk][link-schacon-git-talk] from RailsConf 2008.  If you're familiar with version control systems, see [Why Git is Better than X][link-whygitisbetterthanx].

For tutorials, see [github bootcamp][link-github-help], [gitcasts][link-gitcasts], [Carl Worth's tour][link-cworth-tour], and [git ready][link-git-ready].  Mind best practices for [commits][link-git-commit-messages], [branching][link-git-branching], [rebasing][link-git-rebasing], and [tagging][link-git-tags].



Free repository hosting and project management are available from [github][link-github] and [bitbucket][link-bitbucket].

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

Download the [tab completion][link-git-completion] script to your home directory, and add this line to `~/.bashrc`:

````sh
source ~/git-completion.bash  # Git tab completion
````

###### [Syntax note][link-git-revisions]
The parent-selection operator `^` _(caret)_ defaults to `^1`, and is omitted in the ordinary case a commit has only one parent.  The history operator `~` _(tilde)_ is read "first parent," or "grassy knoll," and acts like a power function: `A~~~` or `A~3` describes the (leftmost) great-grandparent of `A`.  

The ordering of a commit's parents is taken from the arguments to `merge`.  View them with `show`.  

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

<a id="subversion" />
### ![][img-subversion] [Subversion][homepage-subversion] 

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

[link-bitbucket]: https://bitbucket.org/
[link-cworth-tour]: http://cworth.org/hgbook-git/tour/
[link-django]: https://www.djangoproject.com/
[link-git-branching]: http://blog.hasmanythrough.com/2008/12/18/agile-git-and-the-story-branch-pattern
[link-git-commit-messages]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[link-git-completion]: https://raw.github.com/git/git/master/contrib/completion/git-completion.bash
[link-git-ready]: http://gitready.com/
[link-git-rebasing]: http://reinh.com/blog/2009/03/02/a-git-workflow-for-agile-teams.html
[link-git-revisions]: http://schacon.github.com/git/git-rev-parse.html#_specifying_revisions
[link-git-tags]: http://gitref.org/branching/#tag
[link-gitcasts]: http://gitcasts.com/
[link-github]: https://github.com
[link-github-help]: http://help.github.com/
[link-idea]: http://www.jetbrains.com/idea/download/index.html
[link-play]: http://www.playframework.org/
[link-rails]: http://rubyonrails.org/
[link-ruby-interpreters]: https://rvm.beginrescueend.com/rubies/installing/
[link-rvm]: http://beginrescueend.com/rvm/install/ "Ruby enVironment Manager"
[link-schacon-git-talk]: https://encrypted.google.com/search?q=scott+chacon+git+talk
[link-snipmate]: http://www.vim.org/scripts/script.php?script_id=2540
[link-whygitisbetterthanx]: http://whygitisbetterthanx.com/