### Install JDK 7

    $ sudo apt-get install python-software-properties
    $ sudo add-apt-repository ppa:webupd8team/java
    $ sudo apt-get update
    $ sudo apt-get install oracle-jdk7-installer

### View and set alternatives for java

    $ update-alternatives --config java

### Improve fonts of IDEA

Edit `idea/bin/idea64.vmoptions` file:

    -Dawt.useSystemAAFontSettings=on
    -Dsun.java2d.xrender=true
    -Dswing.aatext=true

