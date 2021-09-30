---
layout: post
tag: hyper threading 
tags: Ubuntu Debian
title:  "Disable hyper threading on ubuntu or Debian"
---

{% include note.html content="I tested a few different ways and to disable hyper threading and this is what I landed on" %}

{% include warning.html content="Tested on ubuntu 18.04 and debain 9" %}

**Non persistent**

`echo off > /sys/devices/system/cpu/smt/control`

**To make it presistant**

* make a `/etc/rc.local` file
* make it executable `chmod +x /etc/rc.local`
* add the following `echo off > /sys/devices/system/cpu/smt/control`


**Here is the Copy Pasta Verson**

This copy pasta verson disables hyper threading while running and after roboot 
```bash
if [[ ! -e /etc/rc.local ]]
then
 touch /etc/rc.local
 chmod +x /etc/rc.local
 cat <<'EOF' > /etc/rc.local
#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.
 
# added to disable hyper threading
echo off > /sys/devices/system/cpu/smt/control
exit 0
EOF
else
 echo "Looks like you already have an rc.local file add the following before exit 0"
 echo "echo "echo off > /sys/devices/system/cpu/smt/control"
fi

echo off > /sys/devices/system/cpu/smt/control
```
