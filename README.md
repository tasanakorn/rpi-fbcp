Raspberry Pi Framebuffer Copy
=============================
This program used for copy primary framebuffer to secondary framebuffer (eg. FBTFT). It require lastest raspberry pi firmware (> 2013-07-11) to working properly.

Tested on Raspberry Pi
======================
2017-11-29-raspbian-stretch

Build
-----

    $ mkdir build
    
    $ cd build
    
    $ cmake ..
    
    $ make 


How To Use
----------
$ ./fbcopy

Wanna to run from booting
-------------------------
$ sudo cp fbcopy /usr/bin
$ sudo chmod +x /usr/bin/fbcopy
$ sudo nano /etc/rc.local -> add new line before "exit 0" with "/usr/bin/fbcp &" without quote
$ sudo reboot

