## ![Pidgin][img-pidgin] Pidgin

Pidgin is a GTK+ interface for **libpurple**, a front-end for instant messaging services.  

#### Setup

Some services may require tweaking the default configuration.

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

* <a id="otr-messaging"/> 
[Off-the-Record][plugin-otr]  
`apt install pidgin-otr`

[community][community-pidgin]

### ![Skype][img-skype] Skype <a id="skype" />

Skype is a chat, conferencing, and VOIP client.

#### Setup

Skype is available from the linuxmint repositories.

`apt install skype pidgin-skype`

[community][community-skype]

### ![][img-twitter] Twitter, identi.ca

Twitter and identi.ca are microblogging services.

#### Setup

`apt install pidgin-microblog`

Enable _Tools -> Plugins -> Twitgen_.

Add the account (_Accounts -> Manage accounts -> Add_) and follow the instructions to authorize.

## ![XChat][img-xchat] XChat

XChat is an IRC client.

#### Setup

In _XChat -> Network list -> Linux Mint Server -> Edit_:

Server: `irc.spotchat.org`  
Favorite channels: `#mintcast,#linuxmint-chat,#linuxmint-help,#linuxmint-debian`

[community][community-xchat]

[community-xchat]: http://community.linuxmint.com/software/view/xchat
[community-pidgin]: http://community.linuxmint.com/software/view/pidgin
[community-skype]: http://community.linuxmint.com/software/view/skype

[plugin-otr]: http://www.cypherpunks.ca/otr/debian-install/otr-setup.html

[img-pidgin]: image/pidgin.png "Pidgin"
[img-skype]: image/skype.png "Skype"
[img-twitter]: image/twitter.png "Twitter"
[img-xchat]: image/xchat.png "XChat"
