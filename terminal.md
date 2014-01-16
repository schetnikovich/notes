### Disabling Terminal Flow Control Keystrokes

If you've ever encountered the situation where you've accidentally typed the <Ctrl-S> keystroke and your 
terminal seems to 'hang', that's because you've typed the 'XOFF' special character which tells the terminal 
not to accept any more key inputs.

The way to restore terminal responsiveness is by typing the <ctrl-q> keystroke ('XON') to restore flow control. 
If you want do disable this feature, use the following command on your shell:

    $ stty -ixon

Add this command to your `.bashrc` file.

### Bash history search

Use Ctrl-R for reverse search, Ctrl-S for forward search and Ctrl-G to go back to command line.

If Ctrl-S doesn't work for you Disable Terminal Flow Control Keystrokes (described above)  
as one possible workaround.
