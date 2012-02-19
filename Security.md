## Encryption ##

## SSH ##

## IP blacklist ##

### ![][img-mintnanny] /etc/hosts ###

`mintNanny` provides a graphical interface to this file.

The **hosts** file maps domain names to IP addresses.  Malicious websites can be redirected to the current machine, resulting in a harmless "file not found" error.  A detailed explanation is available [here][link-mvps].

Linux is not vulnerable to Windows malware, but you may still want to blacklist malicious websites.  Append [this list][link-mvps-hosts] to **/etc/hosts**.  Remove the first two entries: _localhost_ is already correctly defined for IPv4 and IPv6.


### ![][img-pgl] [PeerGuardian][homepage-pgl] <a id="peerguardian"/> ###

Firewall manager.  Uses blacklists to prevent incoming and outgoing connections by IP or port number.

You will probably find the lists too aggressive: when you seem to have network problems, the reason is usually that PeerGuardian has blocked some traffic you don't want it to.  This will improve over time as you customize the whitelist.  _(right-click --> Allow permanently)_

[homepage-pgl]: http://moblock-deb.sourceforge.net/

[img-pgl]: pgl-gui.png "PeerGuardian"
[img-mintnanny]: mintnanny.png "Domain Blocker"

[link-mvps]: http://winhelp2002.mvps.org/hosts.htm
[link-mvps-hosts]: http://winhelp2002.mvps.org/hosts.txt