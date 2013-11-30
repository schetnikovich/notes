## Install supervisord

    sudo apt-get install supervisor

This will automatically start `supervisord` and will run it on boot.

## Add program

Create `myapp.conf` file with this similar content:

```
[program:myapp]
command=/usr/bin/node /home/dmitry/robo-site/src/app.js
directory=/home/dmitry/robo-site/src
user=dmitry
stdout_logfile=/home/dmitry/robo-site/logs/supervisor/robo-site.log
stderr_logfile=/home/dmitry/robo-site/logs/supervisor/robo-site.errors.log
```    

Copy this file to `/etc/supervisor/conf.d/`

## Supervisor control tool

To see status about all apps:

    sudo supervisorctl status

To see status only about `myapp`:

    sudo supervisorctl status myapp

To start app:

    sudo supervisorctl start myapp

To see all available commands:

    sudo supervisorctl help 

Output:

```
default commands (type help <topic>):
=====================================
add    clear  fg        open  quit    remove  restart   start   stop  update 
avail  exit   maintail  pid   reload  reread  shutdown  status  tail  version
```

To read help about every command:

    sudo supervisorctl help <command>

## Configure Supervisor Web Console

Add the following configuration to supervisord.conf file:

```
[inet_http_server]
port = 127.0.0.1:9001
username = user
password = 123
```

This will start web console. Restart or update supervisord: `sudo service supervisor restart`.
