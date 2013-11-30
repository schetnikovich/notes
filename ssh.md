## Create SSH Keys

    mkdir -p .ssh
    cd .ssh
    ssh-keygen -f filename -t rsa -C "your_email@somedomain.com"

## Copy public key to remote server

    ssh-copy-id -i ~/.ssh/filename.pub user@111.11.111.111

Public key will be appended to /home/user/.ssh/authorised_keys file.


## Install SSH client and server

You can install both `openssh-client` and `openssh-server` packages in one line:

    sudo apt-get install ssh

## Check that SSH server is running

    ps -A | grep sshd

## Start/Stop SSH server

    sudo service sshd start
    sudo service sshd stop

## Setup local SSH from scratch

    sudo apt-get install ssh
    ssh-keygen 
    ssh-copy-id -i ~/.ssh/id_rsa.pub user@localhost
    
`ssh-keygen` will create `id_rsa` and `id_rsa.pub` files in `~/.ssh` folder. You also 
can specify name of the file with `-f` option.
    
## Manage SSH Identities

Start ssh-agent:

    ssh-agent bash
 
List all identities:
   
    ssh-add -l

Remove one identity:
    
    ssh-add -R site.com

Remove all identities:

    ssh-add -D 

## Known Hosts

See entry for some `host`:

    ssh-keygen -F host

Delete entry for some `host`:

    ssh-keygen -R host

Add entry:

    ssh-keyscan -H host > ~/.ssh/known_hosts

## Local port forwarding

Here we are forwarding localhost:9098 → 198.101.246.208:9090

    ssh -L 9098:localhost:9090 root@198.101.246.208

You can specify multiple ports for forwarding:

    ssh -L 9098:localhost:9090 -L 4040:localhost:4040 root@198.101.246.208

## Edit comment of the key

Open *.pub file and edit the last symbols after space sign. For example:

    ...8/j6Zq/su/pSYRHCZKLdlTf3RNlDMgFY6uY1 Here is my new comment. Please contact me@server.com.

## View fingerprint of the key

    ssh-keygen -lf my-key

## SSH config file to save your life :)

Edit  `~/.ssh/config` file (create if it doesn't exists).

```
Host ubuntik
    HostName 194.11.126.171
    Port 22
    User dmitry   

Host comp2
    HostName 191.12.122.145
    User mike 
```

Now you can simply type:

    ssh ubuntik

### Enable agent forwarding

Agent forwarding is a rocket technology that allows you to use your local keys on remote machines, 
without copying them to such remote machines. In fact, you even can open another ssh session from
remote machine and so on - your keys will be used for all SSH authentications in the chain.

Enable it in your `~/.ssh/config` file:

```
Host ubuntik
    HostName 198.61.166.171
    Port 22
    User dmitry
    ForwardAgent yes
```

### Symplify local port forwarding

Again, `~/.ssh/config` to the rescue:

```
Host ubuntik-tunnel
    HostName 198.61.166.171
    LocalForward 9002 127.0.0.1:9001
    LocalForward 3001 127.0.0.1:3000
    User dmitry
```

This will send your `localhost:9002` to `remote:9001` and 
`localhost:3001` to `remote:3000`

Now simply type:

    ssh -fN ubuntik-tunnel

You can setup as many ports (LocalForward) as you need.

### Permanently keep keys in your ssh-agent.

Usually you need to do:

    ssh-agent bash
    ssh-add ~/.ssh/your_key1
    ssh-add ~/.ssh/your_key2

Sometimes daemons such as `gnome-keyring-daemon` automatically adds all keys that are in `~/.ssh` folder. 

If your `ssh-add -l` returns nothing, and you don't like adding keys at the beginning of each session, 
specify your keys in `~/.ssh/config` file.

Add as many `IdentityFile` directives as you want to your `~/.ssh/config` file:

```
IdentityFile ~/.ssh/gitHubKey
IdentityFile ~/.ssh/server1
IdentityFile ~/.ssh/server2
```

