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


## Installing zsh on a MacOS (earlier than 10.15)

1. You need [Homebrew](https://treehouse.github.io/installation-guides/mac/homebrew)

2. Using Homebrew you install ZSH.

```
$ brew install zsh 

Updating Homebrew... ==> Auto-updated Homebrew! Updated 2 taps (homebrew/core and homebrew/cask).
==> Updated Formulae mosh
==> Renamed Formulae transmission -> transmission-cli

==> Installing dependencies for zsh: ncurses and pcre
==> Installing zsh dependency: ncurses
==> Downloading https://homebrew.bintray.com/bottles/ncurses-6.1.mojave.bottle.tar.gz
==> Downloading from  https://akamai.bintray.com/01/01e03... gda__=exp=15..439~hmac=50 ## 100.0%
==> Pouring ncurses-6.1.mojave.bottle.tar.gz
==> Caveats
ncurses is keg-only, which means it was not symlinked into /usr/local, because macOS already provides this software and installing another version in parallel can cause all kinds of trouble.
If you need to have ncurses first in your PATH run:
  echo 'export PATH="/usr/local/opt/ncurses/bin:$PATH"' >> ~/.bash_profile

For compilers to find ncurses you may need to set:
  export LDFLAGS="-L/usr/local/opt/ncurses/lib"
  export CPPFLAGS="-I/usr/local/opt/ncurses/include"

==> Summary 🍺  /usr/local/Cellar/ncurses/6.1: 3,869 files, 8.3MB
==> Installing zsh dependency: pcre
==> Downloading https://homebrew.bintray.com/bottles/pcre-8.43.mojave.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/08/08e7414a7...~hmac=07               ## 100.0%
==> Pouring pcre-8.43.mojave.bottle.tar.gz 🍺  /usr/local/Cellar/pcre/8.43: 204 files, 5.5MB
==> Installing zsh
==> Downloading https://homebrew.bintray.com/bottles/zsh-5.7.1.mojave.bottle.tar.gz
==> Downloading from https://akamai.bintray.com/79/793d87f67... ~hmac=7f.            ### 100.0%
==> Pouring zsh-5.7.1.mojave.bottle.tar.gz 🍺  /usr/local/Cellar/zsh/5.7.1: 1,515 files, 13.3MB
==> `brew cleanup` has not been run in 30 days, running now...
Removing: bosh-cli--5.5.1... dialog--1.3-20190211.Mojave jenv--0.5.2.tar.gz... 
==> Caveats
==> ncurses. <repeat of the same message>
```
