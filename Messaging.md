## ![][img-pidgin] [Pidgin][homepage-pidgin]

Pidgin is a GTK+ interface for **libpurple**, a front-end for instant messaging services.  

#### Setup

Pidgin is installed by default.  Some services may require tweaking the default configuration.

_Accounts -> Manage Accounts -> Modify_

* AIM
    * Server: `login.messaging.aol.com`,  Port: `5190`
* Facebook
* identi.ca
    * See below
* ICQ
* Google Talk
    * Connection security: `Use old-style SSL`,  Port: `443`,  Server: `talk.google.com`
* MSN
* Skype
    * See below
* Twitter
    * See below
* Yahoo

###### Plugins

<a id="otr-messaging"/>

* [Off-the-Record][link-plugin-otr]  

`apt install pidgin-otr`

[community][community-pidgin]

<a id="skype" />
### ![Skype][img-skype] Skype 

Skype is a chat, conferencing, and VOIP client.

#### Setup

Skype is available from the linuxmint repositories.

`apt install skype pidgin-skype`

[community][community-skype]

###### See also
[VOIP, conferencing, and webcam][anchor-voip]

### ![][img-twitter] Twitter, identi.ca

Twitter and identi.ca are microblogging services.

#### Setup

`apt install pidgin-microblog`

Enable _Tools -> Plugins -> Twitgen_.

Add the account (_Accounts -> Manage accounts -> Add_) and follow the instructions to authorize.

## ![][img-empathy] [Empathy][homepage-empathy]

GNOME messaging client built on the **Telepathy** framework.

#### Setup

Empathy is available from the debian repositories.

`apt install empathy`

## ![][img-xchat] [XChat][homepage-xchat]

IRC client.

#### Setup

XChat is installed by default.

_XChat -> Network list -> Linux Mint Server -> Edit_:  
Server: `irc.spotchat.org/6667`
Favorite channels: `#mintcast,#linuxmint-chat,#linuxmint-help,#linuxmint-debian`

[community][community-xchat]

[anchor-voip]: Audio-&-Video#wiki-voip

[community-xchat]: http://community.linuxmint.com/software/view/xchat
[community-pidgin]: http://community.linuxmint.com/software/view/pidgin
[community-skype]: http://community.linuxmint.com/software/view/skype

[link-plugin-otr]: http://www.cypherpunks.ca/otr/debian-install/otr-setup.html

[homepage-empathy]: http://live.gnome.org/Empathy
[homepage-pidgin]: http://www.pidgin.im/
[homepage-xchat]: http://xchat.org/

[img-empathy]: image/empathy.png "Empathy"
[img-pidgin]: image/pidgin.png "Pidgin"
[img-skype]: image/skype.png "Skype"
[img-twitter]: image/twitter.png "Twitter"
[img-xchat]: image/xchat.png "XChat"