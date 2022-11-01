# Ubuntu 20.04.5 LTS (Focal Fossa)

## Customize Bash Prompt

Focal Fossa default configuration:
```
$ echo $PS0

# PS1 is the primary prompt string. Linux distros have the default value set to: \s-\v$
$ echo $PS1
\[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$

# PS2 is the secondary prompt string
$ echo $PS2
>

# This value is used as the prompt for the select command.
$ echo $PS3

# The value of this parameter is expanded as with PS1 and the value is printed before each command bash displays during an execution trace.
$ echo $PS4
+
```

### My cool PS1 setup

```
export  PS1="\[\033[m\]|\[\033[1;35m\]\t\[\033[m\]|\[\e[1;31m\]\u\[\e[1;36m\]\[\033[m\]@\[\e[1;36m\]\h\[\033[m\]:\[\e[0m\]\[\e[1;32m\][\W]$  \[\e[0m\]"
|13:34:52|lala@lala:[learning]$ 
```
I've added this line in the ~/.bashrc file, so finally the code in that file is:
```
if [ "$color_prompt" = yes ]; then
    PS1='\[\033[m\]|\[\033[1;35m\]\t\[\033[m\]|\[\e[1;31m\]\u\[\e[1;36m\]\[\033[m\]@\[\e[1;36m\]\h\[\033[m\]:\[\e[0m\]\[\e[1;32m\][\W]👾 $  \[\e[0m\]'
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
```


## Adding multitouch trackpad gestures

First, add your user to the input group so you will be allowed to use the input gestures:
```
sudo gpasswd -a $USER input
```

Now, install necessary packages: 
```
sudo apt install wmcctrl python3 python3-setuptools xdotool python3-gi libinput-tools python-gobject
```

Download libinput-gestures from github page and unzip it: https://github.com/bulletmark/libinput-gestures
```
cd Descargas/
unzip libinput-gestures-master.zip
cd libinput-gestures-master
sudo make install
```

Make sure that libinput-gestures is started and that libinput-gestures is going to initialize when booting the system:
```
libinput-gestures-setup autostart
libinput-gestures-setup start
```

In some cases, you will have an error here: libinput-gestures failed to start as a desktop application. Solution in my case:
```
#In order to use libinput gestures, the current user must added into the input group, but it won't take effect until you run the following command to join the group you've just added yourself to:
newgrp input
# The newgrp command is used to change the current group ID during a login session. The official docs suggested reboot after adding user to input group.
```

After that, run again:
```
libinput-gestures-setup autostart
libinput-gestures-setup start
```

Download gestures from github page and unzip it: https://gitlab.com/cunidev/gestures

```
cd Descargas/
unzip gestures-master.zip
cd gestures-master
sudo python3 setup.py install
# now you can remove all setup files from ~/Descargas/
```

Create your gestures. Launch gestures from terminal
```
gestures
```

In the gui interface you can add the desired gestures:
![Gesture interface](resources/screenshot.png)

In my case, I want to substitute the super+Up and super+Down gestures for swipping up and down with four fingers. A complete list of xdotool key codes here: https://gitlab.com/cunidev/gestures/-/wikis/xdotool-list-of-key-codes


## Aliases

Include these lines at the end of the ~/.bashrc file:
```
# Alias definitions.
# You may want to put all your additions into a separate file like
# ~/.bash_aliases, instead of adding them here directly.
# See /usr/share/doc/bash-doc/examples in the bash-doc package.

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```
Then, create the ~/.bash_aliases and add you aliases. In my case, I overuse the "ls -la" command and the git commands:
```
alias la='ls -la'
alias gc='git checkout'
alias ga='git add'
alias gco='git commit'
alias gps='git push'
alias gpl='git pull'
alias gs='git status'
alias gb='git branch'
alias gd='git diff'
alias gl='git log'
alias gm='git merge'
alias count='find . -type f | wc -l'
```
~
~




