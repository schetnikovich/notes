### Get description of package

This will list all packages that contain `packagename`:

    $ apt-cache search packagename

This will limit search for the exact match with `packagename`:

    $ apt-cache search ^packagename$

### List all installed packages

This will list all installed packages:

    $ dpkg --get-selections

Limit it with grep:

    $ dpkg --get-selections | grep git

### View all installed files of package:

    $ dpkg -L ruby



