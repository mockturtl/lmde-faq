[Torrents][anchor-torrents] | [Cloud storage][anchor-cloud-storage] | [FTP][anchor-ftp] | [Local network][anchor-local-network] | [See also][anchor-see-also]
[anchor-cloud-storage]: #wiki-cloud-storage
[anchor-ftp]: #wiki-ftp
[anchor-local-network]: #wiki-local-network
[anchor-see-also]: #wiki-see-also
[anchor-torrents]: #wiki-torrents


<a name="torrents"/>
## Torrents

### ![][img-transmission] [Transmission][homepage-transmission]

Transmission is installed by default.

[community][community-transmission]

### ![][img-deluge] [Deluge][homepage-deluge]

#### Setup

Deluge is available in the debian repositories.

`apt install deluge`

[community][community-deluge]

### ![][img-tribler] [Tribler][homepage-tribler]

##### Setup

Tribler is available from the source repositories.  You may need to configure [Python][anchor-python] and [Subversion][anchor-subversion].

![][emblem-warn] **This software is not from a trusted repository.  Use it at your own risk.**

````sh
apt install swig python-apsw python-m2crypto python-wxglade  # dependencies
svn co http://svn.tribler.org/abc/branches/release-5.5.x/  # subversion
cd release-5.5.x/
PYTHONPATH=$PYTHONPATH:. && export PYTHONPATH  # see Tribler/readme.txt
python Tribler/Main/tribler.py
````

###### See also

[Peerguardian][anchor-peerguardian]

<a name="cloud-storage"/>
## Cloud storage

Backup your files on a remote server and access them from anywhere.

### ![][img-dropbox] [Dropbox][homepage-dropbox]

Clients are available for Windows, OS X, Linux, iOS, Android, Blackberry, and the web.

[community][community-dropbox]

#### Setup

Dropbox is available in the linuxmint repositories.

`apt install dropbox nautilus-dropbox`

###### Security

You may wish to [encrypt][anchor-encryption] your files.

### ![][img-meiga] [Meiga][homepage-meiga]

Host your own files from your desktop.  Access or share them with a web browser.

[community][community-meiga]

#### Setup

Meiga is available in the linuxmint repositories.

`apt install meiga`

<a name="ubuntu-one" />
### ![][img-ubuntu-one] [Ubuntu One][homepage-ubuntu-one]

Clients are available for Windows, Ubuntu, Android, iOS, and the web.  

Integrates with desktop apps like [Tomboy][anchor-tomboy] and [Banshee][anchor-banshee] for certain kinds of files (notes, music, contacts).

<a name="ftp"/>
## FTP

### ![][img-filezilla] [Filezilla][homepage-filezilla]

[community][community-filezilla]

<a name="local-network"/>
## ![][img-network] Local network

### [Samba][homepage-samba]

#### Setup

<a name="see-also"/>
## See also
* [Opera Unite][anchor-opera]
* [[Email]]


[anchor-banshee]: Audio-&-Video#wiki-banshee
[anchor-encryption]: Security#wiki-encryption
[anchor-opera]: Browsers#wiki-opera
[anchor-peerguardian]: Security#wiki-peerguardian
[anchor-python]: Programming#wiki-python
[anchor-subversion]: Programming#wiki-subversion
[anchor-tomboy]: Office#wiki-tomboy

[community-deluge]: http://community.linuxmint.com/software/view/deluge
[community-dropbox]: http://community.linuxmint.com/software/view/dropbox
[community-filezilla]: http://community.linuxmint.com/software/view/filezilla
[community-meiga]: http://community.linuxmint.com/software/view/meiga
[community-transmission]: http://community.linuxmint.com/software/view/transmission

[emblem-warn]: image/emblem-warn.png "Warning!"

[homepage-deluge]: http://deluge-torrent.org/
[homepage-dropbox]: https://www.dropbox.com
[homepage-filezilla]: http://filezilla-project.org/
[homepage-meiga]: http://meiga.igalia.com/
[homepage-samba]: http://www.samba.org/
[homepage-transmission]: http://www.transmissionbt.com/
[homepage-tribler]: http://www.tribler.org/
[homepage-ubuntu-one]: https://one.ubuntu.com/

[img-deluge]: image/deluge.png "Deluge"
[img-dropbox]: image/dropbox.png "Dropbox"
[img-filezilla]: image/filezilla.png "Filezilla"
[img-meiga]: image/meiga.png "Meiga"
[img-network]: image/folder-remote.png "Network"
[img-transmission]: image/transmission.png "Transmission"
[img-tribler]: image/tribler.png "Tribler"
[img-ubuntu-one]: image/ubuntu-one.png "Ubuntu One"