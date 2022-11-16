Xterm, and likely many other X11 programs, do not set themselves window icons, which window managers typically use to represent that program window in switcher lists, taskbars, and so on. This program can set the X11 window icon for any given window, to that of a given image file.

Usage
=====
    usage: xseticon [options] path/to/icon.{png,jpg,svg}
    options:
      -name     : apply icon to the window of the name supplied
      -id   : apply icon to the window id supplied
    
    Sets the window icon to the specified image, in any of the formats supported by imlib2.
    Depending on the version and the compiled features, it can handle additional formats
    like SVG. The image is loaded from
    the file at runtime and sent to the X server; thereafter the file does not
    need to exist, and can be deleted/renamed/modified without the X server or
    window manager noticing.
    If no window selection option is specified, the window can be interactively
    selected using the cursor.
    
    Hints:
      xseticon -id "$WINDOWID" path/to/icon.png
    Will set the icon for an xterm.xseticon from Paul Evans (http://www.leonerd.org.uk/).

Build and install instructions
==============================

On Ubuntu / Debian:

``` bash
# Install dependencies
sudo apt install libxmu-headers libimlib2-ev libxmu-dev libglib2.0-dev
# Build
make
# Install
sudo cp xseticon /usr/local/bin
```
On EL7:

```bash
# Install dependencies
sudo yum install libXmu-devel imlib2 imlib2-devel glib2-devel
# Build
make
# Install
sudo cp xseticon /usr/local/bin
```

Author
======
This is xseticon from José Mª Fernández (https://orcid.org/0000-0002-4806-5140) and originally from Paul Evans (http://www.leonerd.org.uk/).

Note that there is another xseticon from Rustem Valeev on Sourceforge (https://sourceforge.net/projects/xseticon/).

License
=======

See LICENSE file.

