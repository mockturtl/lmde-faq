## Brother ##

### [Printer drivers][brother-drv-lpr] ###

Download the LPR driver and cupswrapper driver .deb files for your model.  Install them.

_Note for 64-bit systems:_ use `apt-get install ia32-libs`, and `dkpg -i --force-all driver.deb` for 32-bit compatibility.

To verify the installation, `dpkg -l | grep Brother`.

#### Setup ####

Open a web browser and visit [http://localhost:631/admin](http://localhost:631/admin).  Click "Add Printer."  Login as "root" and follow the instructions.

_Note: do not permit your browser to store your root password!_

Print a test page, if you like, from the "Maintenance" dropdown.

The printer will now be available on your desktop.  Make it your default and test with `system-config-printer`.

### [Scanner drivers][brother-drv-scan] ###

Download the brscan .deb file for your model and architecture and install it.

To verify the installation, `dpkg -l | grep Brother`.

#### Setup ####

Scroll through the printer's panel menu for Network --> IP to obtain the IP address.

Substitute the correct model name and IP in the setup command, e.g., 

`brsaneconfig4  -a  name=BrotherABC-123YZ  model=ABC-123YZ  ip=xxx.xxx.x.xxx`.

Verify with `brsaneconfig4  -q  |  grep  Brother`.

Your scanner is now ready to use.  Test with `simple-scan`.

* [Optional][brother-faq-scan]: I didn't find this necessary, but the link may be useful.


[brother-drv-lpr]: http://welcome.solutions.brother.com/bsc/public_s/id/linux/en/download_prn.html
[brother-drv-scan]: http://welcome.solutions.brother.com/bsc/public_s/id/linux/en/download_scn.html
[brother-faq-scan]: http://welcome.solutions.brother.com/bsc/public_s/id/linux/en/instruction_scn1c.html

#### References ####
[ref1][mint-forums-brother1], [ref2][mint-forums-brother2], [ref3][debian-forums-brother1]

[mint-forums-brother1]: http://forums.linuxmint.com/viewtopic.php?f=51&t=80363 "Linux Mint forums"
[mint-forums-brother2]: http://forums.linuxmint.com/viewtopic.php?f=42&t=90808 "Linux Mint forums"
[debian-forums-brother1]: http://www.debianuserforums.org/viewtopic.php?f=9&t=1491 "Debian forums"
