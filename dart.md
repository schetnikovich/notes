### Unable to start Dartium on Ubuntu 13.10

Error:

    ./chrome: error while loading shared libraries: libudev.so.0: cannot open shared object file: No such file or directory

Chrome looks for libudev.so.0 library, but Ubuntu has libudev.so.1

Solution (make symbolic link):

    ln -s /lib/x86_64-linux-gnu/libudev.so.1.3.5 /lib/x86_64-linux-gnu/libudev.so.0

   
