# GroupProject-Invictus-McClure
##Intro
This document will detail all the steps needed to set up your beaglebone black for use. By the end of these steps your development environment will be identical to mine. Please add a comment if you have any questions.

- http://www.adafruit.com/datasheets/BBB_SRM.pdf
- http://exploringbeaglebone.com/chapter1/

The exploring beaglebone site is a great reference to using it made by an ECE professor in ireland (derek molloy). There is a book but everything in the book is also on his website.

----------------------------------------------------------------------------------------------------------------------------
## Step 1: Initial setup
	http://beagleboard.org/getting-started - More details are here if desired. 

Nothing plugged into beaglebone before starting these steps
Install network over usb drivers (see getting-started link) on desired PC.
Download image writer for Windows (see link) (or if you have a tool you prefer to use use that)
Use that to write the latest debian image (2015-03-01) that you have downloaded from http://beagleboard.org/latest-images to the blank SD card.
Eject the SD card once the writing is finished
Put the SD card into the SD card slot on the (powered down) beaglebone black
Hold down the user boot button on the beaglebone black and plug in the USB cable for power. See figure 17 in the BBB_SRM pdf for the location of this button (called â€œboot switchâ€� in that document).
After a few seconds you should be able to release the switch. Check (either via HDMI on a monitor or over the network over usb) that the beaglebone is now running. 
The default IP for the beaglebone black on network over USB is 192.168.7.2 and the default login is debian (password is temppwd)

## Step 2: Expand memory to fill space
http://elinux.org/Beagleboard:Expanding_File_System_Partition_On_A_microSD
They explain it much better than I could. Following their steps exactly should do everything needed.

The beaglebone black is now ready to go. Only thing remaining are libraries and programs

##Step 3: Install debian jessie (debian 8) virtual box on desired development computer.

https://www.virtualbox.org/wiki/Linux_Downloads - for the debian image
https://www.virtualbox.org/wiki/Downloads - for virtualbox itself

Be sure to match whatever architecture cpu your computer uses for both the virtualbox and the debian image


## Step 4: Downloading eclipse and setting up that workspace. 
### Also connecting to the beaglebone black through eclipse (eclipse installed on the debian jessie virtualbox image that was just created). 
Use whatever version of Eclipse you want, but I use Mars (luna is the one in the video since it is a little old).
	https://youtu.be/T9yFyWsyyGk?t=15m25s

The video is a great walkthrough of setting up cross compilation, installing eclipse, and connecting to the beaglebone. We will not be cross compiling so no need to watch the first part of the video. The code will live on the beaglebone and we will access/edit/compile it remotely through eclipse


After this the only things left are to install specific libraries (like OpenCV and such) which is easy with sudo apt-get install. 

If you notice that your debian jessie virtualbox is a fixed resolution (and want to make it fullscreen bordered/borderless) you need to install the addons. 
http://virtualboxes.org/doc/installing-guest-additions-on-debian/
step 6 is referring to the debian image you downloaded (that menu is a virtualbox, not debian, menu).
