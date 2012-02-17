## ![Pidgin][img-pidgin] Pidgin ##

Pidgin is a GTK+ interface for _libpurple_, a front-end for instant messaging services.  

Some services may require tweaking the default configuration (_Accounts --> Manage Accounts --> Modify_).

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

###### Plugins ######

* [Off-the-Record][plugin-otr]

### Skype ###

`apt install skype pidgin-skype`

### Twitter, identi.ca ###

`apt install pidgin-microblog`

Enable _Tools --> Plugins --> Twitgen_

Add the account (_Accounts --> Manage accounts --> Add_) and follow the instructions to authorize.  

TODO: authentication error?

## ![XChat][img-xchat] XChat ##

XChat is an IRC client.
 
_XChat --> Network list --> Linux Mint Server --> Edit_ 
Server: `irc.spotchat.org`  
Favorite channels: `#mintcast,#linuxmint-chat,#linuxmint-help,#linuxmint-debian`

[plugin-otr]: http://www.cypherpunks.ca/otr/debian-install/otr-setup.html

[img-pidgin]: pidgin.png "Pidgin"
[img-xchat]: xchat.png "XChat"