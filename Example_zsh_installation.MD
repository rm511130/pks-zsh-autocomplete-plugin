# How to install ZSH

* The Z shell (Zsh) is a Unix shell that can be used as an interactive login shell and as a command interpreter for shell scripting. Zsh is an extended Bourne shell with a large number of improvements, including some features of Bash, ksh, and tcsh. In June 2019, Apple announced that the forthcoming macOS Catalina (10.15) would adopt Zsh as the default shell, replacing Bash.[4][5]


## Installing zsh on a Ubuntu 16.04 Server

1. We need a Ubuntu 16.04 Server.

```
kubectl run -i --tty ubuntu --image=ubuntu:16.04 --restart=Never -- /bin/bash -il
```

You should see:

```
If you don't see a command prompt, try pressing enter.

root@ubuntu:/#
```

2. We need to install a few dependencies

```
apt-get update
apt-get install curl
apt install zsh
apt install git
apt-get install vim
```

And you're done! There's no need to `chsh -s $(which zsh)` just yet because the installation of the `oh-my-zsh` will do that for you.

3. Back to the [oh-my-zsh installation](https://github.com/rm511130/pks-zsh-autocomplete-plugin/blob/master/README.MD/#Installation).

