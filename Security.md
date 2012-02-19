## File encryption <a id="encryption" /> ##

## ![][img-gnome-terminal] SSH ##

Secure shell lets you log in remotely through the terminal.  Install the server to accept incoming connections.

`apt install ssh`

You can use your username and password, but it's better to generate a keypair with `ssh-keygen` to identify each client computer you plan to log in with.  Each client can then provide its identity (public key) with `ssh-copy-id`.  The public keys are written to **~/.ssh/authorized_keys** on the remote system, and its identity is written to the local client's **~/.ssh/known_hosts** to prevent spoofing.

Once all clients can connect, disable password login on the server via **/etc/ssh/sshd_config**.

```text
RSAAuthentication yes
PubkeyAuthentication yes
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```

## IP blacklist ##

### ![][img-mintnanny] /etc/hosts ###

`mintNanny` provides a graphical interface to this file.

The **hosts** file maps domain names to IP addresses.  Malicious websites can be redirected to the current machine, resulting in a harmless "file not found" error.  A detailed explanation is available [here][link-mvps].

Linux is not vulnerable to Windows malware, but you may still want to blacklist malicious websites.  Append [this list][link-mvps-hosts] to **/etc/hosts**.  Remove the first two entries: _localhost_ is already correctly defined for IPv4 and IPv6.

### ![][img-pgl] [PeerGuardian][homepage-pgl] <a id="peerguardian"/> ###

Firewall manager.  Uses blacklists to prevent incoming and outgoing connections by IP or port number.

You will probably find the lists too aggressive: when you seem to have network problems, the reason is usually that PeerGuardian has blocked some traffic you don't want it to.  This will improve over time as you customize the whitelist.  _(right-click --> Allow permanently)_

## HTTPS (SSL) ##



[homepage-pgl]: http://moblock-deb.sourceforge.net/

[img-gnome-terminal]: gnome-terminal.png "SSH"
[img-pgl]: pgl-gui.png "PeerGuardian"
[img-mintnanny]: mintnanny.png "Domain Blocker"

[link-mvps]: http://winhelp2002.mvps.org/hosts.htm
[link-mvps-hosts]: http://winhelp2002.mvps.org/hosts.txt