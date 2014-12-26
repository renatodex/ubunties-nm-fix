ubunties-nm-fix
===============

There is an annoying bug at Ubuntu which affect a few installations. Happens
most on Notebook and portable machines, which can be put into a Sleep state
by capping the screen.

When it does, the network connections enter in a Sleep mode and cannot be restored
via GUI. (by interacting with the top bar menu)

To solve this issue, there is a simple command that force the Wakeup of
Network Manager driver, which is:

```
sudo nmcli nm sleep false
```

The connection is also restored restarting the NM driver:

```
sudo service network-manager restart
```

I've being doing that for several days, but then i startet to get annoyed,
so i created this simple script that automatically AWAKE the NM driver
after a Sleep.

## How to install this script?

The installation is simple:

1. Go to **/etc/pm/sleep.d/** folder.
2. Paste the file **nm-never-sleep** there.
3. Make it executable by running **chmod +x nm-never-sleep** .

Restart your Ubuntu, and try sleep your machine to see if the Network is
restored!

## Author

Renato Alves - renatodex@gmail.com
