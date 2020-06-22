# bootstrap-mac
need to packages.

## brew

### install

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### install cask packages

```bash
brew tap caskroom/versions
brew cask install 1password
# brew cask install android-platform-tools
# brew cask install blue-jeans
brew cask install docker
brew cask install google-chrome
# brew cask install istat-menus
brew cask install java11
brew cask install karabiner-elements
# brew cask install mongodb-compass
brew cask install postman
brew cask install slack
brew cask install sublime-text
brew cask install visual-studio-code
brew cask install webtorrent
brew cask install alfred
# brew cask install android-studio
# brew cask install bose-soundtouch
brew cask install dropbox
brew cask install intellij-idea-ce
brew cask install iterm2
# brew cask install java8
brew cask install macdown
brew cask install notion
# brew cask install react-native-debugger
brew cask install spotify
brew cask install tunnelbear
brew cask install vlc
brew cask install zoomus
```

### install packages
```bash
brew tap weaveworks/tap

brew install aws-iam-authenticator
brew install awscli
brew install bash-completion
brew install eksctl # for kubernetes
brew install helm # for kubernetes
brew install htop
brew install jq
brew install k9s # for kubernetes
brew install kube-ps1 # for kubernetes
brew install kubectx # for kuberntes
brew install parquet-tools
brew install telnet
brew install terraform
brew install tldr
brew install tree
brew install wget
brew install minikube
```


## xcode install
```bash
# install mac app store
# and then
sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer
```

## Languages

### rvm, ruby install
```bash
# ruby
brew install gpg
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash
rvm install ruby-2.6.0 # ruby-2.6.0
```

### nvm install

add `nvm`, `rvm` environemnt to `.zshrc` or `.bash_profile`

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
nvm install v12.14.0
```

### node, ruby
```bash
rvm use --default ruby-2.6.0
nvm use v12.14.0
```

### Add to `.zshrc` file

```bash
# kube_ps1
source "/usr/local/opt/kube-ps1/share/kube-ps1.sh"
PS1='$(kube_ps1)'$PS1
# for krew
export PATH="${PATH}:${HOME}/.krew/bin"
# alias docker clean image, ps
alias docker_clean_images='docker rmi $(docker images --filter "dangling=true" -q --no-trunc) && docker rmi $(docker images | grep "none" | awk "/ / { print $3 }")'
alias docker_clean_ps='docker rm $(docker ps -qa --no-trunc --filter "status=exited")'
```