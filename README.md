# firewalld-simple-logging

Simple Logging of droped and rejected packets for firewalld. It just
adds a generic logging rule just before the end of the firewalld generated
rules.

## Install

Just do a make install:
```
$ sudo make install
```

This will install firewalld-logging in `/usr/local`.
If you prefer to install it in `/usr`, use:
```
$ sudo make install PREFIX=/usr ETC=/etc
```

## Usage

* Edit the sysconfig file to your needs:
```
vi /usr/local/etc/sysconfig/firewalld-logging
```
* Start the service: `systemctl start firewalld-logging`
* Optionally, enable it so that it starts automatically after starting
  the firewalld daemon itself: `systemctl enable firewalld-logging`
* Enjoy!
