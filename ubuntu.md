### Cannot login, bounces back to login splash

Press CTRL+ALT+F1 and log in.

First, review content of `~/.xsession-errors` there might be a clue there. 
If not, continue with this command:

    $sudo chown -R $USER:$USER $HOME

Then press CTRL+ALT+F7 and try to log in

If you don't use sudo for GUI programs you won't get this issue. Commands lke:

    sudo gedit
    sudo nautilus
    
will CAUSE this as it is not right. To run GUI apps with root access use:

    gksudo gedit
    gksudo nautilus
    
And it won't make an issue.


### Turn your ubuntu to Xubuntu

    sudo apt-get install xubuntu-desktop

### Turn your Xubuntu to Ubuntu

    sudo apt-get install ubuntu-desktop

### Terminal background color and font

I know, this is not very important, but I used to the following background color of terminal: `#300A24`, and white (#FFFFFF) color of text. Font is Monospace 13.


### Install Thunar archive plugin

    sudo apt-get install thunar-archive-plugin

After this close all Thunar instances, and open again.
