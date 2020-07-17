# Raspberripi-cfs

This guide is for 64-bit raspbian, and is very much a work in progress! DO NOT USE!

When running Docker Swarm, I get this error with Raspberry PI's:

> NanoCPUs can not be set, as your kernel does not support CPU cfs period/quota or the cgroup is not mounted

CFS / Control Groups isn't 100% supported in the default kernel. You'll need to build your own.

I followed the guide [here](https://www.tal.org/tutorials/raspberry-pi3-build-64-bit-kernel)

On the initial step, where you install packages - you need to add the package 'textinfo', or binutils will not compile.

At the "make menuconfig" step, you need to enable cfs in addition to setting a local version

* Select "General setup"
* Select "Control Group Support"
* Select every item in this menu, and any submenus (currently only "CPU controller")
* Exit

Follow the guide from there.

Please send pull requests for any modifications!
