[File encryption][anchor-encryption] | [SSH][anchor-ssh] | [IP blacklist][anchor-ip-blacklist] | [https://][anchor-https]

[anchor-encryption]: #wiki-encryption
[anchor-ssh]: #wiki-ssh
[anchor-ip-blacklist]: #wiki-ip-blacklist
[anchor-https]: #wiki-https


<a id="encryption" />
## File encryption

### ![][img-gpg] [GnuPG][homepage-gnupg]

OpenPGP ("Pretty Good Privacy") implementation.  Sign, verify, encrypt, and decrypt individual files and email.

#### Setup

GnuPG is [available][pts-gnupg2] in the debian repositories.  It will be installed with the graphical interface.

###### ![][img-gpa] Gnu Privacy Assistant 

`apt install gpa`

###### ![][img-kleopatra]![][emblem-kde] Kleopatra 

`apt install kleopatra`  

A walkthrough is available [here][link-gpg-walkthrough].  The [Enigmail][anchor-enigmail] plugin for Thunderbird also has a nice wizard.

<a id="ssh"/>
## ![][img-gnome-terminal] SSH _(Secure Shell)_

Remote login through the terminal.  

#### Setup

You can use your username and password, but it's better to generate a keypair to identify each client computer you plan to log in with.  

`ssh-keygen -b 4096` 

Choose a [secure passphrase][link-password-generator] different from your system password.  It can contain whitespace and punctuation.  Protect your private key (**~/.ssh/id_rsa**).

Install the server on any machine which should accept incoming connections.

`apt install ssh`

Each client can then provide its identity (_public key_, **~/.ssh/id_rsa.pub**) to the remote server.

`ssh-copy-id my-remote-hostname`

These are written to **~/.ssh/authorized_keys** on the remote system, and its identity is written to the local client's **~/.ssh/known_hosts** to prevent spoofing.

Once all clients can connect, disable password login on the server via **/etc/ssh/sshd_config**.

```text
RSAAuthentication yes
PubkeyAuthentication yes
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```

Your public key also identifies your computer to services built on SSH, like [github][link-github-ssh] (see "Set Up SSH Keys").

<a id="ip-blacklist"/>
## IP blacklist

### ![][img-mintnanny] /etc/hosts _(hosts file)_

Maps domain names _(website.com)_ to [IP addresses][link-whatismyip].

Links can be redirected to the machine's own address, resulting in a harmless "file not found" error.  A detailed explanation is available [here][link-mvps].

`mintNanny` provides a graphical interface to this file.

#### Setup

Linux is not vulnerable to Windows malware, but you may still want to blacklist malicious websites.  Append [this list][link-mvps-hosts] to **/etc/hosts**.  Remove the first two entries: _localhost_ is already correctly defined for IPv4 and IPv6.

<a id="peerguardian"/>
### ![][img-pgl] [PeerGuardian][homepage-pgl] 

Firewall manager.  Uses blacklists to prevent incoming and outgoing connections by IP or port number.

You will probably find the lists too aggressive: when you seem to have network problems, the reason is usually that PeerGuardian has blocked some traffic you don't want it to.  This will improve over time as you customize the whitelist.  _(right-click -> Allow permanently)_

#### Setup

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

PeerGuardian is available from the project homepage.

<a id="https"/>
## ![][img-ssl] [https://][link-tls]

Encrypting your internet traffic helps you maintain privacy.  

Your browser uses SSL _(Secure Sockets Layer)_ certificates from a trusted authority to verify a website's identity when you connect, and ensure messages you send and receive cannot be read by third parties.

Make sure your [default search engine][anchor-search-engines] uses SSL, and use [off-the-record messaging][anchor-otr-messaging].

[anchor-otr-messaging]: Messaging#wiki-otr-messaging
[anchor-enigmail]: Email#wiki-enigmail
[anchor-search-engines]: Browsers

[emblem-kde]: image/boston.png
[emblem-warn]: image/emblem-warn.png

[homepage-gnupg]: http://www.gnupg.org/
[homepage-pgl]: http://moblock-deb.sourceforge.net/

[img-gnome-terminal]: image/gnome-terminal.png "SSH"
[img-gpa]: image/gpa.png "Gnu Privacy Assistant"
[img-gpg]: image/gpg.png "Gnu Privacy Guard"
[img-kleopatra]: image/kleopatra.png "Kleopatra"
[img-pgl]: image/pgl-gui.png "PeerGuardian"
[img-mintnanny]: image/mintnanny.png "Domain Blocker"
[img-ssl]: image/ssl.png "SSL / TLS"

[link-github-ssh]: http://help.github.com/linux-set-up-git/
[link-gpg-walkthrough]: http://arc.apotheon.org/cheats/gpg_quick.html
[link-mvps]: http://winhelp2002.mvps.org/hosts.htm
[link-mvps-hosts]: http://winhelp2002.mvps.org/hosts.txt
[link-password-generator]: http://strongpasswordgenerator.com/
[link-tls]: http://en.wikipedia.org/wiki/Transport_Layer_Security
[link-whatismyip]: http://www.whatismyip.com/

[pts-gnupg2]: http://packages.qa.debian.org/g/gnupg2.html "PTS"