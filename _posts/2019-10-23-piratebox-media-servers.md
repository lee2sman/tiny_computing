---
layout: post
title: "Using Piratebox infrastructure - Creating our own Networks"
---

# How to set up Raspberry Pi PirateBox without ssh

* These steps are intended to be followed after creating a Piratebox disk image and starting it up in the Raspberry Pi.

## change password of alarm user

```
> passwd
```

## enable fake-timeservice

### set date and time

```
> sudo timedatectl set-ntp false
> sudo date -s "20170904 1603"
> cd /opt/piratebox && sudo ./bin/timesave.sh ./conf/piratebox.conf install
```


### optional: enable the imageboard and discussionboard

```
> sudo /opt/piratebox/bin/board-autoconf.sh
```

### enable usb thumb drive share OR extend SDcard

USB: ```> sudo /opt/piratebox/rpi/bin/usb_share.sh```

SDCard: ```> sudo /opt/piratebox/rpi/bin/sdcard_share.sh```

### optinoal: enable UPnP media server

```
> sudo cp /etc/minidlna.conf /etc/minidlna.conf.bkp
> sudo cp /opt/piratebox/src/linux.example.minidlna.conf /etc/minidlna.conf
> sudo systemctl start minidlna
> sudo systemctl enable minidlna
```

### enable realtimeclock timekeeping
```
> sudo systemctl enable rpi_hwclock
```

# To turn on the Piratebox server

```
sudo systemctl enable minidlna
sudo systemctl start minidlna
```

# To stop the Piratebox server

```
sudo systemctl stop minidlna
```


## Modifications

### Use a USB drive on your Pi

1. Plug in a USB. Wait for your command line to come back.
2. ```sudo /opt/piratebox/rpi/bin/usb_share.sh```
3. You can access your files at ```/mnt/usbshare```
4. For example, to move a file from your usb to your Pi's web content folder:
```
cp /mnt/usbshare/index.html /opt/piratebox/share/content
```
*Note: this will overwrite any index.html file that is already in that folder*

### Change the SSID / Network name

By default, your piratebox network will be called **PirateBox - Share Files Freely**. You can change this!

Your file ```/opt/piratebox/conf/hostapd.conf``` contains configuration to name the SSID network name.

For example, type 

```
nano /opt/piratebox/conf/hostapd.conf
```

In the line that starts ```ssid``` change the network name to a name of your choice.

Save. (```Control-O``` and then hit enter.)

Quit (```Control-X```)

Then reboot your system.


### Change the display URL

The default displayed url is: **piratebox.lan**.

To change this, run:

```
sudo /opt/piratebox/bin/install_piratebox.sh /opt/piratebox/conf/piratebox.conf hostname new_name
```

replace *new_name* with whatever url name you like.


### To change the landing page

Your piratebox's landing page index, css, images and js files are located at: ```/opt/piratebox/share/content```

You'll see index.html, stylesheet and javascript files there. You can edit these to serve any content. 

### To see changes, restart the Piratebox server

```
sudo systemctl start minidlna
sudo systemctl enable minidlna
```

### Shutting down the pi

```sudo shutdown now```

# To get the piratebox to login automatically and start the Piratebox server

Your ```.bashrc``` file runs on startup.

The file is in your home folder. Edit the file.

```nano .bashrc```

At the end of the file add in:

```
systemctl piratebox enable minidlna
systemctl piratebox start minidlna
```

NOTE: This will autorun at startup. To quit out of it, you'll need to do Control-C several times.


### Resources

Additional Raspberry Pi Piratebox [tutorials](https://piratebox.cc/raspberry_pi:diy).

[Info on how to modify the base Piratebox website](https://piratebox.cc/generic:mods:theming) including where files are located on the Pi, and customization hints.

Piratebox [Forums](https://forum.piratebox.cc/)


## Readings


[The Radical Tactics of the Offline Library](https://vimeo.com/95351775), video based on the book *Radical Tactics: Reversalism and Personal Portable Libraries*

[Radical Tactics of the Offline Library](http://networkcultures.org/blog/publication/no-07-radical-tactics-of-the-offline-library-henry-warwick/) as PDF book, by Henry Warwick

Online Reading Group's [COLLABORATIVE LIBRARIES](http://consortium.github.io/Collaborative-Libraries/collaborative-libraries.html),
Images and notes on collaborative libraries…

[A Public Library](http://www.apubliclibrary.org/), a space for conversations, presentations, the sharing of resources, and for collective reading, viewing, and learning.

[The Library of Babel](https://archive.org/details/TheLibraryOfBabel) by Jorge Luis Borges

[Librarian is my Occupation](https://librarianshipwreck.wordpress.com/2014/04/16/librarian-is-my-occupation-a-history-of-the-peoples-library-of-occupy-wall-street/), a history of the People's Library of Occupy Wall Street


## Homework

Pick and read 2+ manifestos from [Manifestos For the Digital Age](https://greyscalepress.com/books/manifestos-for-the-internet-age/).

The manifestos are available free to read [in a GitHub repo](https://github.com/greyscalepress/manifestos/tree/master/content/manifestos).

Get your Piratebox to work. Develop a concept for your Piratebox server. Customize the landing page and network name. Add any additional functionality. When complete, consider moving the SD card to a dedicated [Raspberry Pi Zero W](https://www.adafruit.com/product/3400), a $10 Pi.

1. create a README.txt file.
2. Include:
- What is the title of your **box?
- Who made it? (it's perfectly fine to create a collective pseudonym name)
- What is the title and concept of your **box?
- Who does it serve?
- How did you build it?
- Any additional notes, images, manifesto, etc.

**When finished:**
1. Upload your readme file to Moodle! 
2. And place it on your piratebox server in some way that is accessible to the public. Images, ascii art, etc are optional.

**Note: Everyone in your group/collective must upload the README.txt file** to their own moodle space!
