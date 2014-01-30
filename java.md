### Install JDK 7

    $ sudo apt-get install python-software-properties
    $ sudo add-apt-repository ppa:webupd8team/java
    $ sudo apt-get update
    $ sudo apt-get install oracle-jdk7-installer

### Install Open JDK patched with font fix

    $ sudo add-apt-repository ppa:no1wantdthisname/openjdk-fontfix
    $ sudo apt-get update
    $ sudo apt-get install openjdk-7-jdk

When new version of openjdk-7-jdk will be available in Ubuntu repositories, this patched
OpenJDK will be replaced by non patched from Ubuntu. To prevent this, disable upgrades
of openjdk-7-jdk package:

    echo “openjdk-7-jdk hold” | dpkg --set-selections

View status of this package:

    dpkg --get-selections | grep openjdk-7-jdk

### View and set alternatives for java

    $ update-alternatives --config java

### Improve fonts of IDEA

Edit `idea/bin/idea64.vmoptions` file:

    -Dawt.useSystemAAFontSettings=lcd
    -Dsun.java2d.xrender=true
    -Dswing.aatext=true

You should install Infinality patches before (see `fonts.md`) to get the best result.
