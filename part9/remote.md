# Working from home

## SSH

Dynamic DNS is already set up in our Kitchener office and is reachable at `noblerock.zapto.org`, and machines are assigned with different ports. Thus, a connection can be established by:
```
ssh -p [port] [username]@noblerock.zapto.org
```

## SSH with tmux(1)

Consider using [tmux(1)](https://www.freebsd.org/cgi/man.cgi?query=tmux), so that you can resume the previous working environment instantly. First, before SSH'ing to your machine, you must have tmux already running. After you've established SSH connection run the following:
```
tmux attach
```

## VNC

Consider using VNC if you need a graphical interface (for QEMU, etc.). First you will need a VNC server:
```
pkg install x11vnc
```

Then, after you've established SSH connection, run the server:
```
x11vnc
```
In another terminal, start another connection:
```
ssh -L 5900:localhost:5900 -N -f -l [username] -p [port] noblerock.zapto.org
```
Point your favorite VNC viewer to localhost:5900 and watch. I personally use [RealVNC](https://www.realvnc.com/en/connect/download/vnc/).
