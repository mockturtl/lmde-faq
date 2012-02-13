## ![Thunderbird][img-thunderbird-logo] Thunderbird ##

### Latest ###
* [32-bit][thunderbird-x86-latest]
* [64-bit][thunderbird-amd64-latest]

#### Setup ####

Download the package and extract it: `tar xjf path/to/downloaded/file.tar.bz2`.

Move the extracted files to `/opt`:  (note: `/opt/thunderbird` is the mint package)

`sudo mv thunderbird /opt/thunderbird-moz`.

Replace the symlink:

`sudo ln -sf /opt/thunderbird-moz/thunderbird /usr/bin/thunderbird`

Thunderbird can update itself via the menu (_Help --> About Thunderbird_).

###### Add-ons ######

Add-ons are installed through the menu (_Tools --> Add-ons_).

 **TODO**

* Lightning: calendar & events
* Enigmail: PGP encryption

[img-thunderbird-logo]: https://static-ssl-cdn.addons.mozilla.net/media/img/app-icons/med/thunderbird.png "Mozilla Thunderbird"
[thunderbird-x86-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-i686/en-US/
[thunderbird-amd64-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-x86_64/en-US/