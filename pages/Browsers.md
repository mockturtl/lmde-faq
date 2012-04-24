[Firefox][anchor-firefox] | [Chromium][anchor-chromium] | [Google Chrome][anchor-google-chrome] | [Opera][anchor-opera]

[anchor-chromium]: #wiki-chromium
[anchor-firefox]: #wiki-firefox
[anchor-google-chrome]: #wiki-google-chrome
[anchor-opera]: #wiki-opera


<a name="Firefox"/>
## ![][img-firefox] [Firefox][homepage-firefox]

Firefox is installed by default.

### Latest

_The Firefox builds available in the linuxmint repositories are customized.  [Custom search engines][link-search-engines] are a critical revenue stream for Linux Mint; please consider installing them.  To see why you might want to use DuckDuckGo, read the [partnership announcement][link-duckduckgo-partnership]._

TODO: instructions for adding Mint CSE's (links are empty php files?)

* [32-bit][link-firefox-x86-latest]
* [64-bit][link-firefox-amd64-latest]
* Beta (these links will go out of date quickly; compare to the highest [version number][link-firefox-tracking] available) 
    * [32-bit][link-firefox-x86-beta]
    * [64-bit][link-firefox-x86-beta]
* [Aurora][link-firefox-aurora] (alpha)

#### Setup

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

Download the package and extract it.

`tar xjf path/to/downloaded/file.tar.bz2`

Move the extracted files to **/opt/** (note: **/opt/firefox/** is the mint package).

`sudo mv firefox /opt/firefox-moz`

Replace the symlink:

`sudo ln -sf /opt/firefox-moz/firefox /usr/bin/firefox`

Firefox can update itself via the menu. (_Help -> About Firefox_)

[community][community-firefox]

<a name="Chromium"/>
## ![][img-chromium] [Chromium][homepage-chromium]

#### Setup

Chromium is available in the debian repositories.

`apt install chromium`

[community][community-chromium]

<a name="google-chrome"/>
## ![][img-chrome] [Google Chrome][homepage-google-chrome]

### [Latest][link-chrome-landing]

* [stable][link-chrome-stable]
* beta
    * [32-bit][link-chrome-x86-beta]
    * [64-bit][link-chrome-amd64-beta]
* dev
    * [32-bit][link-chrome-x86-dev]
    * [64-bit][link-chrome-amd64-dev]

#### Setup

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

`sudo dpkg -i path/to/downloaded/file.deb`

Chrome creates an entry for google's repository in **/etc/apt/sources.list.d/**.

<a name="opera"/>
## ![][img-opera] [Opera][homepage-opera]

#### Setup

Opera is available in the linuxmint repositories.

`apt install opera`

[community][community-opera]

[emblem-warn]: image/emblem-warn.png "Warning!"

[link-chrome-landing]: http://dev.chromium.org/getting-involved/dev-channel "Chromium project"
[link-chrome-stable]: https://www.google.com/chrome?platform=linux "Google Chrome"
[link-chrome-x86-beta]: http://www.google.com/chrome/intl/en/eula_beta.html?dl=beta_i386_deb "Google Chrome beta"
[link-chrome-amd64-beta]: http://www.google.com/chrome/intl/en/eula_beta.html?dl=beta_amd64_deb "Google Chrome beta"
[link-chrome-x86-dev]: http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_i386_deb "Google Chrome dev"
[link-chrome-amd64-dev]: http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_amd64_deb "Google Chrome dev"
[link-firefox-x86-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-i686/en-US/ "Mozilla Firefox"
[link-firefox-amd64-latest]: ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-x86_64/en-US/ "Mozilla Firefox"
[link-firefox-x86-beta]: ftp://ftp.mozilla.org/pub/firefox/releases/11.0b5/linux-i686/en-US/ "Firefox beta"
[link-firefox-amd64-beta]: ftp://ftp.mozilla.org/pub/firefox/releases/11.0b5/linux-x86_64/en-US/ "Firefox beta"
[link-firefox-aurora]: http://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-aurora/ "Firefox Aurora"
[link-firefox-releases]: ftp://ftp.mozilla.org/pub/firefox/releases/
[link-firefox-tracking]: https://wiki.mozilla.org/Features/Release_Tracking

[community-chromium]: http://community.linuxmint.com/software/view/chromium-browser
[community-firefox]: http://community.linuxmint.com/software/view/firefox
[community-opera]: http://community.linuxmint.com/software/view/opera

[homepage-google-chrome]: https://www.google.com/chrome/
[homepage-chromium]: http://www.chromium.org/Home
[homepage-firefox]: http://www.mozilla.org/firefox
[homepage-opera]: http://www.opera.com/

[img-firefox]: image/firefox.png "Mozilla Firefox"
[img-chrome]: image/google-chrome.png "Google Chrome"
[img-chromium]: image/chromium-browser.png "Chromium"
[img-opera]: image/opera.png "Opera"

[link-search-engines]: http://linuxmint.com/searchengines.php
[link-duckduckgo-partnership]: http://blog.linuxmint.com/?p=1884
