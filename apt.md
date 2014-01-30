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

### Hold package (prevent it from upgrade)

    $ echo "packagename hold" | dpkg --set-selections

### View all installed files of package:

    $ dpkg -L ruby

### Find package this file belongs to

    $ dpkg -S /path/to/file

### View apt log

    $ vim /var/log/apt/history.log

### Repositories of package

List repositories package belongs to:

    $ apt-cache policy openjdk-7-jdk
