# Set up your shiny OS X for software development

After having maintained [this gist](https://gist.github.com/danguita/6242852/revisions) with a bunch of [stargazers](https://gist.github.com/danguita/6242852/stargazers), I'd like to let people contribute here. Feel free to pull request!

## Table of Contents

- [Command Line Tools](#command-line-tools)
- [Homebrew](#homebrew)
- [Dropbox](#dropbox)
- [Google Drive](#google-drive)
- [Google Chrome](#google-chrome)
- [iTerm2](#iterm2)
- [Git](#git)
- [Ack](#ack)
- [Grep](#grep)
- [Perl](#perl)
- [Python](#python)
- [Freetype](#freetype)
- [Fonts](#fonts)
- [Curl](#curl)
- [Bash](#bash)
- [Findutils](#findutils)
- [GNU tar](#gnu-tar)
- [GNU sed](#gnu-sed)
- [GnuPG](#gnupg)
- [ZSH](#zsh)
- [Vim](#vim)
- [Htop](#htop)
- [Exuberant Ctags](#exuberant-ctags)
- [Ranger](#ranger)
- [Gist](#gist-client)
- [Tmux](#tmux)
- [Rainbarf](#rainbarf)
- [Docker](#docker)
- [Postgresql](#postgresql)
- [MySQL](#mysql)
- [Elasticsearch](#elasticsearch)
- [Redis](#redis)
- [Capybara](#capybara-dependencies)
- [Imagemagick](#imagemagick)
- [Ghostscript](#ghostscript)
- [Weechat](#weechat)
- [Twitter](#twitter-client)
- [Livestreamer](#livestreamer)
- [Ruby](#ruby)
- [Nodejs](#nodejs)
- [Bower](#bower)
- [VirtualBox](#virtualbox)
- [Vagrant](#vagrant)
- [Packer](#packer)
- [X11](#x11)
- [Java runtime](#java-runtime)
- [Microsoft IE OVA images](#microsoft-ie-ova-images)

- - -

## The Checklist

### Command Line Tools

1. Get Xcode from App Store
2. Open Xcode
3. Go to Preferences
4. Downloads > Components > Command Line Tools > Install

#### Command Line Tools (CLI)

```
xcode-select --install
```

### Homebrew

Follow instructions from http://brew.sh

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Homebrew dupes

```
brew tap homebrew/dupes
```

#### Homebrew versions

```
brew tap homebrew/versions
```

#### Homebrew Cask (http://caskroom.io/)

```
brew install caskroom/cask/brew-cask
```

### Dropbox

```
brew cask install dropbpox
```

### Google Drive

```
brew cask install google-drive
```

### Google Chrome

```
brew cask install google-chrome
```

### iTerm2

```
brew cask install iterm2
```

### Git

```
brew install git
brew install git-extras # Git utilities
brew install tig        # front-end to Git (ncurses)
brew install gh         # GitHub wrapper
```

### Ack

```
brew install ack
```

### Grep

```
brew install grep
```

### Perl

```
brew install perl
brew link perl --force
```

### Python

```
brew install python
pip install --upgrade setuptools
pip install --upgrade pip
```

### Freetype

```
brew install freetype
ln -s /usr/local/opt/freetype/include/freetype2 /usr/local/include/freetype
```

### Fonts

```
brew cask install caskroom/fonts/font-hack # Hack
```

### Curl

```
brew install curl
brew link curl --force
```

### Bash

```
brew install bash
```

### Findutils

```
brew install findutils
```

### GNU tar

```
brew install gnu-tar
```

### GNU sed

```
brew install gnu-sed
```

### GnuPG

```
brew install gpg
```

### ZSH

```
brew install zsh
sudo mv /etc/zshenv /etc/zprofile # system-wide environment settings
```

### Vim

```
brew install vim
brew cask install macvim
mkdir ~/Applications
brew linkapps
```

### Htop

```
brew install htop
```

### Exuberant Ctags

```
brew install ctags
```

### Ranger

```
brew install ranger
```

### Gist client

```
brew install gist
gist --login
```

### Tmux

```
brew install reattach-to-user-namespace
brew install tmux
```

### Rainbarf

```
brew install rainbarf
```

### Docker

```
brew install boot2docker
brew install docker-compose
```

```
boot2docker init
```

#### Docker hub

```
docker login
```

### Postgresql

```
brew install postgresql
initdb /usr/local/var/postgres -E utf8
```

#### Postgresql: Avoid passing a host

```
sudo mkdir /var/pgsql_socket
sudo ln -s /private/tmp/.s.PGSQL.5432 /var/pgsql_socket/
```

#### Postgresql: Install `pg` gem on x86_64

```
ARCHFLAGS="-arch x86_64" gem install pg
```

### MySQL

```
brew install mysql
```

### Elasticsearch

```
brew install elasticsearch
```

#### Elasticsearch-head plugin

```
/usr/local/Cellar/elasticsearch/0.90.3/bin/plugin -install mobz/elasticsearch-head
open http://localhost:9200/_plugin/head/
```

### Redis

```
brew install redis
```

### Capybara dependencies

```
brew install qt5
brew link --force qt5
```

### Imagemagick

```
brew install imagemagick --disable-openmp --build-from-source
```

#### libMagick: Dynamic libraries

```
cd /usr/local/Cellar/imagemagick/6.8.6-3/lib
ln -s libMagick++-6.Q16.1.dylib libMagick++.dylib
```

### Ghostscript

```
brew install gs
```

### Weechat

```
brew install weechat --with-perl --with-ruby
```

#### Weechat Scripts

```
/script install buffers.pl beep.pl
```

#### TOR

```
brew install tor
```

#### Set up IRC SASL:

- http://www.weechat.org/files/doc/stable/weechat_user.en.html#irc_sasl_authentication
- http://freenode.net/irc_servers.shtml#tor

### Twitter client

```
easy_install -U rainbowstream
```

#### Rainbowstream: Run with `image-on-term`

```
rainbowstream -iot
```

### Livestreamer

```
easy_install -U livestreamer
```

### Ruby

```
brew install chruby
brew install ruby-install
brew install chgems
```

#### Install rubies

```
ruby-install ruby 1.9.3
ruby-install ruby 2.2.0
ruby-install ruby 2.2.2
...
```

### Nodejs

```
brew install node
```

#### npm

```
curl https://npmjs.org/install.sh | sh
```

#### nvm

```
curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

### bower

```
npm install bower
```

### VirtualBox

```
brew cask install virtualbox
```

### Vagrant

```
brew cask install vagrant
```

#### Keep VirtualBox Guest Additions updated

```
vagrant plugin install vagrant-vbguest
```

### Packer

```
brew tap homebrew/binary
brew install packer
```

### X11

```
brew cask install xquartz
```

### Java Runtime

http://support.apple.com/kb/dl1572

### Microsoft IE OVA images

http://www.modern.ie/en-us/virtualization-tools

```
curl -O http://virtualization.modern.ie/vhd/IEKitV1_Final/VirtualBox/OSX/IE6_WinXP.ova.zip
curl -O http://virtualization.modern.ie/vhd/IEKitV1_Final/VirtualBox/OSX/IE7_Vista.ova.zip
curl -O http://virtualization.modern.ie/vhd/IEKitV1_Final/VirtualBox/OSX/IE8_Win7.zip
curl -O http://virtualization.modern.ie/vhd/IEKitV1_Final/VirtualBox/OSX/IE9_Win7.zip
curl -O http://virtualization.modern.ie/vhd/IEKitV1_Final/VirtualBox/OSX/IE10_Win8.ova.zip
```

