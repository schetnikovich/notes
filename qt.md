### Build QT 5.2.0 on Ubuntu 13.10

    $ sudo apt-get install build-essential perl python git
    $ sudo apt-get install "^libxcb.*" libx11-xcb-dev libglu1-mesa-dev libxrender-dev libgtk2.0-dev
    $ sudo apt-get install g++ libfontconfig1-dev  libfreetype6-dev libx11-dev libxcursor-dev libxext-dev libxfixes-dev libxft-dev libxi-dev libxrandr-dev libxrender-dev

Important libs here are `libgtk2.0-dev`, `libfontconfig1-dev` and `libfreetype6-dev`. Without them qt will not support fontconfig db and GTK style.    

Meta package lists the following dependencies:

    $ sudo apt-get install bash build-essential git-core subversion git-svn apache2 php5 python libx11-dev libfontconfig1-dev ruby flex \
      gperf bison libxslt1-dev libsqlite3-dev libxext-dev libssl-dev libxrender-dev libicu-dev libxv-dev libxrandr-dev libgl1-mesa-dev \
      libglu1-mesa-dev libdbus-1-dev bluez libbluetooth-dev gstreamer0.10-plugins-base gstreamer0.10-ffmpeg gstreamer0.10-plugins-good \
      libgstreamer-plugins-base0.10-dev libxcb-icccm4-dev libxcb-xfixes0-dev libxcb-image0-dev libxcb-keysyms1-dev libxcb-sync0-dev \
      libx11-xcb-dev xvfb libgtk2.0-dev libxcb-randr0-dev libjpeg-dev libpng-dev

From the root source directory of Qt 5.2.0:

    $ ./configure -release -opensource -confirm-license -nomake tests -nomake examples -fontconfig
    $ make -j4 all
   
You should not run `make install`.

Build with `-debug` and `-release` options in two folders (for instance `qt-debug`, `qt-release`) 

### Build Qt 4.8.4 on Ubuntu (13.10)

    $ git clone https://git.gitorious.org/qt/qt.git
    $ git checkout v4.8.4
    $ ./configure -release -opensource -confirm-license -nomake tests -nomake examples -nomake docs -no-webkit -no-declarative -prefix $PWD/qtbase
    $ make -j4
    $ make install

You should run `make install`.

It takes ~18 min on my machine.

To reconfigure, run `make confclean` and `configure` it again.

### Build QtCreator 3.0.0 on Ubuntu (13.10)

    $ git clone https://git.gitorious.org/qt-creator/qt-creator.git
    $ git checkout v3.0.0
    $ /home/dmitry/libs/qt-4.8.4-release/qtbase/bin/qmake -r
    $ make -j4

It takes ~10 min on my machine.
    
Installation (`make install`) is not needed. It is however possible, using:

    $ make install INSTALL_ROOT=$INSTALL_DIRECTORY

After build, run `bin/qtcreator`.
