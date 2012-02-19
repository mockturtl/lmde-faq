## ![Firefox][img-firefox] Firefox ##

### Latest ###
* [32-bit][firefox-x86-latest]
* [64-bit][firefox-amd64-latest]

#### Setup ####

Download the package and extract it.

`tar xjf path/to/downloaded/file.tar.bz2`

Move the extracted files to **/opt** (note: **/opt/firefox** is the mint package).

`sudo mv firefox /opt/firefox-moz`

Replace the symlink:

`sudo ln -sf /opt/firefox-moz/firefox /usr/bin/firefox`

Firefox can update itself via the menu (_Help --> About Firefox_).

## ![Chromium][img-chromium] Chromium ##

### [Latest][chromium-pts] ###

#### Setup ####

`apt install chromium`

Chromium is available in the debian repositories.

## ![Google Chrome][img-chrome] Google Chrome ##

### [Latest][chrome-landing] ###

* [stable][chrome-stable]
* beta
    * [32-bit][chrome-x86-beta]
    * [64-bit][chrome-amd64-beta]
* dev
    * [32-bit][chrome-x86-dev]
    * [64-bit][chrome-amd64-dev]

#### Setup ####

`sudo dpkg -i path/to/downloaded/file.deb`

Chrome creates an entry in **/etc/apt/sources.list.d/** and uses APT to keep itself updated from google's repository.

## ![Opera][img-opera] Opera <a id="opera" name="opera"/>##

### [Latest][opera-pts] ###

#### Setup ####

`apt install opera`

Opera is available in the linuxmint repositories.


[firefox-x86-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-i686/en-US/
[firefox-amd64-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-x86_64/en-US/
[chromium-pts]: http://packages.qa.debian.org/c/chromium-browser.html
[opera-pts]: http://packages.linuxmint.com/list.php?release=Debian
[chrome-landing]: http://dev.chromium.org/getting-involved/dev-channel 
[chrome-stable]: https://www.google.com/chrome?platform=linux
[chrome-x86-beta]: http://www.google.com/chrome/intl/en/eula_beta.html?dl=beta_i386_deb
[chrome-amd64-beta]: http://www.google.com/chrome/intl/en/eula_beta.html?dl=beta_amd64_deb
[chrome-x86-dev]: http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_i386_deb
[chrome-amd64-dev]: http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_amd64_deb

[img-firefox]: firefox.png "Mozilla Firefox"
[img-chrome]: google-chrome.png "Google Chrome"
[img-chromium]: chromium-browser.png "Chromium"
[img-opera]: opera.png "Opera"