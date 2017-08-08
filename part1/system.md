# Install the Base System

## Grab an image
Download an image from [https://www.freebsd.org/where.html](). Always choose the newest snapshot of the current development branch (12-CURRENT as of Aug 2017) as it is required for your development. You will get a file similar to:
```
FreeBSD-12.0-CURRENT-amd64-20170717-r321072-memstick.img.xz
```

## Flash image to USB stick

Insert a USB stick and flash the image using [dd](https://www.freebsd.org/cgi/man.cgi?dd(1):
```
unxz FreeBSD-12.0-CURRENT-amd64-20170717-r321072-memstick.img.xz
dd if=FreeBSD-12.0-CURRENT-amd64-20170717-r321072-memstick.img of=/dev/[usually da5, but may differ] bs=8m
```

## Install the system

Restart the system with the USB stick inserted. Boot from it and follow the installer.  
After installing the base system, install your favorite desktop, tools, configurations, and start developing.
