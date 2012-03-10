<a id="thunderbird"/>
## ![][img-thunderbird-logo]  [Thunderbird][homepage-thunderbird] 

### Latest
* [32-bit][link-thunderbird-x86-latest]
* [64-bit][link-thunderbird-amd64-latest]
* Beta (these links will go out of date quickly; compare to the highest [version number][link-thunderbird-nightly] available)
    * [32-bit][link-thunderbird-x86-beta]
    * [64-bit][link-thunderbird-amd64-beta] 
* [Earlybird][link-thunderbird-alpha] (alpha)

#### Setup

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

Download the package and extract it.

`tar xjf path/to/downloaded/file.tar.bz2`

Move the extracted files to **/opt/**:  (note: **/opt/thunderbird/** contains the mint package)

`sudo mv thunderbird /opt/thunderbird-moz`

Replace the symlink:

`sudo ln -sf /opt/thunderbird-moz/thunderbird /usr/bin/thunderbird`

Thunderbird can update itself via the menu. (_Help -> About Thunderbird_)

###### Add-ons

Add-ons are installed through the menu. (_Tools -> Add-ons_)

 **TODO**

* Lightning: calendar & events
<a id="enigmail"/>
* Enigmail: PGP encryption ([also here][anchor-encryption])

[community][community-thunderbird]


[anchor-encryption]: Security#wiki-encryption

[community-thunderbird]: http://community.linuxmint.com/software/view/thunderbird

[emblem-warn]: image/emblem-warn.png "Warning!"

[homepage-thunderbird]: http://www.mozilla.org/thunderbird "Mozilla Thunderbird"

[img-thunderbird-logo]: image/thunderbird.png "Mozilla Thunderbird"

[link-thunderbird-alpha]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/latest-earlybird/
[link-thunderbird-x86-beta]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/11.0b5-candidates/build1/linux-i686/en-US/
[link-thunderbird-amd64-beta]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/11.0b5-candidates/build1/linux-x86_64/en-US/
[link-thunderbird-x86-latest]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-i686/en-US/
[link-thunderbird-amd64-latest]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-x86_64/en-US/
[link-thunderbird-nightly]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/