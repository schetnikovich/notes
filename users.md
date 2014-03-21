## Passwordless sudo for user

Open `/etc/sudoers` file with `sudo visudo` command, and add the following line at the end of file:

    username ALL=(ALL) NOPASSWD:ALL

Set `username` to the name of your user.

It turns our that the order of lines in sudoers is significant. When placed the line under 
"User privilege specification" which sounded like the right place, but the line for 
the %admin group that comes later was overriding the setting.

Putting the same line at the end of the sudoers file fixed the issue.

You are not required to reboot the system but you have to log out and log in again. 
Group membership is evaluated at login time only.
