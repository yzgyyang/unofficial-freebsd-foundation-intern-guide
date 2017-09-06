# Package (pkg-ng) and Ports Systems

Pkg and Ports systems are one of the most advanced management systems nowadays for source code and binaries and they are (of course) available on FreeBSD. Here introduces some basic usage of these systems. Note that a comprehensive guide is available in the Handbook.

## pkg

Pkg is for managing binaries. It may require sudo to run.

### Basic Usage

Pkg is not included in the base system. However, it can be bootstrapped by simply running `pkg` once with an internet connection.

Most used commands include:
```
pkg {install, remove, search} [name-of-the-package]
```

```
pkg {autoremove, update, upgrade}
```

Note that Charlie found that `pkg autoremove` may have some issues. Use it with caution and always check the list of packages to be removed. (Charlie once removed gnome3 by accident with `autoremove`. Charlie is still trying to reproduce this problem.)

## ports

Ports collection is for managing source code for various programs. It can be used to quickly and automatically get the latest tarball, tweak it with your own options and compile & install.

### Initialize

Portsnap is the tool for managing ports. It may require sudo to run.

During first run, use:
```
portsnap fetch extract
```
This may take a while.

Each time after, when updating ports, use:
```
portsnap fetch update
```

### Install a Port

Ports tree lies in `/usr/ports` and is a set of Makefiles. Ports can be installed by:
```
cd /usr/ports/{kind}/{package-name} && make install clean
```

More comprehensive deinstall/reinstall/search technique can be found in the Handbook.

Siva wrote a guide of installing irssi using ports on the Foundation website.

Tip: https://freshports.org is a useful website for querying information for all ports.
