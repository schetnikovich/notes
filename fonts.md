### Install infinality patches

    sudo add-apt-repository ppa:no1wantdthisname/ppa
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install fontconfig-infinality

Set infinality style (choose `linux`):

    sudo bash /etc/fonts/infinality/infctl.sh setstyle

Configure styles in `infinality-settings.sh`

    sudo -H gedit /etc/profile.d/infinality-settings.sh

In this file, search for USE_STYLE (it should be USE_STYLE="DEFAULT" by default) 
and change it to "UBUNTU".

Logout to apply this changes.

### Easy access to google fonts

Such fonts like Inconsalata, Droid are part of Google Web Fonts. They are all
easely installable by TypeCatcher

    sudo apt-get install typecatcher
