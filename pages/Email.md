[Thunderbird][anchor-thunderbird] | [Evolution][anchor-evolution] | [Kontact][anchor-kontact]

[anchor-thunderbird]: #wiki-thunderbird
[anchor-evolution]: #wiki-evolution
[anchor-kontact]: #wiki-kontact

An email program typically includes components to manage an address book (contacts) and calendar (notes, tasks).

<a name="thunderbird"/>
## ![][img-thunderbird-logo]  [Thunderbird][homepage-thunderbird] 

### Latest
* [32-bit][link-thunderbird-x86-latest]
* [64-bit][link-thunderbird-amd64-latest]
* Beta (these links will go out of date quickly; compare to the highest [version number][link-thunderbird-tracking] available)
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
<a name="enigmail"/>
* Enigmail: PGP encryption ([also here][anchor-encryption])

[community][community-thunderbird]


<a name="evolution"/>
## ![][img-evolution] [Evolution][homepage-evolution]

[community][community-evolution]

<a name="kontact"/>
## ![][img-kontact] ![][emblem-kde] [Kontact][homepage-kontact]

[community][community-kontact]


[anchor-encryption]: Security#wiki-encryption
[community-evolution]: http://community.linuxmint.com/software/view/evolution
[community-kontact]: http://community.linuxmint.com/software/view/kontact
[community-thunderbird]: http://community.linuxmint.com/software/view/thunderbird

[emblem-kde]: image/boston.png "KDE"
[emblem-warn]: image/emblem-warn.png "Warning!"

[homepage-evolution]: http://projects.gnome.org/evolution/ "Evolution"
[homepage-kontact]: http://userbase.kde.org/Kontact "Kontact"
[homepage-thunderbird]: http://www.mozilla.org/thunderbird "Mozilla Thunderbird"

[img-evolution]: image/evolution.png "Evolution"
[img-kontact]: image/kontact.png "Kontact"
[img-thunderbird-logo]: image/thunderbird.png "Mozilla Thunderbird"

[link-thunderbird-alpha]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/latest-earlybird/
[link-thunderbird-x86-beta]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/11.0b5-candidates/build1/linux-i686/en-US/
[link-thunderbird-amd64-beta]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/11.0b5-candidates/build1/linux-x86_64/en-US/
[link-thunderbird-x86-latest]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-i686/en-US/
[link-thunderbird-amd64-latest]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/releases/latest/linux-x86_64/en-US/
[link-thunderbird-nightly]: http://ftp.mozilla.org/pub/mozilla.org/thunderbird/nightly/
[link-thunderbird-tracking]: https://wiki.mozilla.org/Features/Thunderbird_Release_Tracking
