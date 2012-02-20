## File encryption <a id="encryption" />

### ![][img-gpg] [GnuPG][homepage-gnupg]

An implementation of OpenPGP ("Pretty Good Privacy").  Sign, verify, encrypt, and decrypt individual files and email.

#### Setup

GnuPG is [available][pts-gnupg2] in the debian repositories.  It will be installed with the graphical interface.

![][img-gpa] Gnu Privacy Assistant `apt install gpa`

![][img-kleopatra]![][emblem-kde] Kleopatra `apt install kleopatra`  

## ![][img-gnome-terminal] SSH

Secure shell lets you log in remotely through the terminal.  Install the server to accept incoming connections.

`apt install ssh`

You can use your username and password, but it's better to generate a keypair with `ssh-keygen` to identify each client computer you plan to log in with.  Protect your private key (**~/.ssh/id_rsa**).

Each client can then provide its identity (public key, **~/.ssh/id_rsa.pub**) with `ssh-copy-id`.  The public keys are written to **~/.ssh/authorized_keys** on the remote system, and its identity is written to the local client's **~/.ssh/known_hosts** to prevent spoofing.

Once all clients can connect, disable password login on the server via **/etc/ssh/sshd_config**.

```text
RSAAuthentication yes
PubkeyAuthentication yes
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```

Your public key also identifies your computer to services built on SSH, like [github][link-github-ssh] (see "Set Up SSH Keys").

## IP blacklist

### ![][img-mintnanny] /etc/hosts

`mintNanny` provides a graphical interface to this file.

The **hosts** file maps domain names to IP addresses.  Links can be redirected to the machine's own address, resulting in a harmless "file not found" error.  A detailed explanation is available [here][link-mvps].

Linux is not vulnerable to Windows malware, but you may still want to blacklist malicious websites.  Append [this list][link-mvps-hosts] to **/etc/hosts**.  Remove the first two entries: _localhost_ is already correctly defined for IPv4 and IPv6.

### ![][img-pgl] [PeerGuardian][homepage-pgl] <a id="peerguardian"/>

Firewall manager.  Uses blacklists to prevent incoming and outgoing connections by IP or port number.

You will probably find the lists too aggressive: when you seem to have network problems, the reason is usually that PeerGuardian has blocked some traffic you don't want it to.  This will improve over time as you customize the whitelist.  _(right-click --> Allow permanently)_

## HTTPS (SSL)


[emblem-kde]: boston.png

[homepage-gnupg]: http://www.gnupg.org/
[homepage-pgl]: http://moblock-deb.sourceforge.net/

[img-gnome-terminal]: gnome-terminal.png "SSH"
[img-gpa]: gpa.png "Gnu Privacy Assistant"
[img-gpg]: gpg.png "GPG"
[img-kleopatra]: kleopatra.png "Kleopatra"
[img-pgl]: pgl-gui.png "PeerGuardian"
[img-mintnanny]: mintnanny.png "Domain Blocker"

[link-github-ssh]: http://help.github.com/linux-set-up-git/
[link-mvps]: http://winhelp2002.mvps.org/hosts.htm
[link-mvps-hosts]: http://winhelp2002.mvps.org/hosts.txt

[pts-gnupg2]: http://packages.qa.debian.org/g/gnupg2.html "PTS"