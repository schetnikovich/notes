## Passwordless sudo for user

Open `/etc/sudoers` file with `sudo visudo` command, and add the following line:

    username ALL=(ALL) NOPASSWD:ALL

Set `username` to the name of your user.

You are not required to reboot the system but you have to log out and log in again. 
Group membership is evaluated at login time only
