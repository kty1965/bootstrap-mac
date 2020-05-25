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
brwe install aws-iam-authenticator
brwe install awscli
brwe install bash-completion
brwe install eksctl # for kubernetes
brwe install helm # for kubernetes
brwe install htop
brwe install jq
brwe install k9s # for kubernetes
brwe install kube-ps1 # for kubernetes
brwe install kubectx # for kuberntes
brwe install parquet-tools
# brwe install redis
# brwe install openjdk
# brwe install sbt
# brwe install scala
# brwe install kotlin
# brew install gradle
# brew install postgres
brwe install telnet
brwe install terraform
brwe install tldr
brwe install tree
brwe install wget
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

add nvm environemnt to `.zshrc` or `.bash_profile`

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
nvm install v12.14.0
```

### node, ruby
```bash
rvm use --default ruby-2.6.0
nvm use v12.14.0
```

