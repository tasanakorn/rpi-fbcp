Raspberry Pi Framebuffer Copy
=============================
This program used for copy primary framebuffer to secondary framebuffer (eg. FBTFT). It require lastest raspberry pi firmware (> 2013-07-11) to working properly.

#### Tested on Raspberry Pi B 1,2,3,Z,ZW

  - 2020-02-13-raspbian-buster
  - 2017-11-29-raspbian-stretch


#### Requirement

~~~bash
  sudo apt update
  sudo apt upgrade -y
  sudo apt install -y git cmake
~~~


#### Build

~~~bash
  cd /tmp
  git clone https://github.com/tasanakorn/rpi-fbcp.git
  mkdir -p /tmp/rpi-fbcp/build
  cd /tmp/rpi-fbcp/build
  cmake ..
  make -j $( nproc --all )
  sudo install fbcp /usr/local/bin/fbcp
~~~


#### How To Use

~~~bash
  fbcp &
~~~


#### Wanna run automatically at startup

~~~bash
  sudo cp ./service /etc/init.d/fbcp
  sudo chmod +x /etc/init.d/fbcp
  sudo update-rc.d fbcp defaults
  sudo service fbcp start


# control service


  sudo service fbcp start   # run fbcp
  sudo service fbcp stop    # kill fbcp
  sudo service fbcp status  # check status
~~~


#### Disable / Enable run automatically at startup

~~~bash
  # Disable
  sudo service fbcp stop
  sudo update-rc.d fbcp disable

  # Enable
  sudo update-rc.d fbcp enable
  sudo service fbcp start

~~~

#### Cancel run automatically at startup

~~~bash
  sudo service fbcp stop
  sudo update-rc.d fbcp disable
  sudo update-rc.d fbcp remove
  sudo rm -rf /etc/init.d/fbcp
~~~


License
-------


Copyright (c) 2013 Tasanakorn Phaipool

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
