Raspberry Pi Framebuffer Copy
=============================
This program used for copy primary framebuffer to secondary framebuffer (eg. FBTFT). It require lastest raspberry pi firmware (> 2013-07-11) to working properly.

Tested on Raspberry Pi 3
========================
2017-11-29-raspbian-stretch


Requirement
-----------
cmake
libatlas-base-dev

$ sudo apt-get install cmake libatlas-base-dev -y

Build
-----

    $ mkdir build
    
    $ cd build
    
    $ cmake ..
    
    $ make 


How To Use
----------
$ ./fbcp

Wanna to run from booting
-------------------------
$ sudo cp fbcp /usr/bin
$ sudo chmod +x /usr/bin/fbcp
$ sudo nano /etc/rc.local -> add new line before "exit 0" with "/usr/bin/fbcp &" without quote
$ sudo reboot

