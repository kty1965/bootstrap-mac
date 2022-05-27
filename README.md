# bootstrap-mac

need to packages.

## brew

### install

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### install cask packages

```zsh
brew tap homebrew/cask-versions
brew install --cask 1password
# brew install --cask android-platform-tools
# brew install --cask blue-jeans
brew install --cask docker
brew install --cask google-chrome
brew install --cask istat-menus
brew install --cask java11
brew install --cask karabiner-elements
# brew install --cask mongodb-compass
brew install --cask postman
brew install --cask slack
brew install --cask sublime-text
brew install --cask visual-studio-code
brew install --cask webtorrent
brew install --cask alfred
# brew install --cask android-studio
# brew install --cask bose-soundtouch
brew install --cask dropbox
brew install --cask intellij-idea-ce
brew install --cask iterm2
# brew install --cask java8
brew install --cask macdown
brew install --cask notion
# brew install --cask react-native-debugger
brew install --cask spotify
brew install --cask tunnelbear
brew install --cask vlc
brew install --cask keybase
brew install --cask pritunl
brew install --cask aws-vault
brew install --cask tiles
brew install --cask 1password-cli
brew install --cask ngrok

brew install --cask discord
brew install --cask lens
brew install --cask zoom

brew install --cask via
```

### install packages

```zsh
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
brew install kubectx # for kubernetes
brew install fzf # for kubernetes
frew install stern # fro kubernetes
brew install derailed/k9s/k9s
brew install parquet-tools
brew install telnet
brew install tldr
brew install tree
brew install wget
brew install minikube
brew install istioctl
brew install dive # for docker image layer
brew install pre-commit
brew install terraform-docs tflint
brew install gawk tfsec coreutils checkov terrascan
brew install graphviz # for graph
brew install asciinema # for cli record
brew install mike-engel/jwt-cli/jwt-cli
brew install tfenv
brew install pyenv
brew install git-lfs
```

### install krew plugins

```zsh
kubectl krew install rbac-tool
```

## .zshrc settings

```zsh
touch ~/.zshrc
compaudit | xargs chmod g-w
```

## kubectl settings

```zsh
echo "source <(kubectl completion zsh)" >> ~/.zshrc
echo 'alias k=kubectl' >>~/.zshrc
echo 'complete -F __start_kubectl k' >>~/.zshrc
```

## Languages

### tfenv, terraform install

```zsh
brew install tfenv
tfenv install 0.12.29
tfenv use 0.12.29
```

### rvm, ruby install

```zsh
# ruby
brew install gpg
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash
rvm install ruby-2.6.0 # ruby-2.6.0
```

### nvm install

add `nvm`, `rvm` environemnt to `.zshrc` or `.bash_profile`

```zsh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
nvm install v14.19.2
```

### pip pacakges

```zsh
pip install s3-tree

### gvm install

```zsh
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

### node, ruby

```zsh
rvm use --default ruby-2.7.1
nvm use --default v14.19.2
```

### pyenv

```zsh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

pyenv install 3.10.4
pyenv global 3.10.4
```

### Add to `.zshrc` file

```zsh
# kube_ps1
source "/usr/local/opt/kube-ps1/share/kube-ps1.sh"
PS1='$(kube_ps1)'$PS1
# for krew
export PATH="${PATH}:${HOME}/.krew/bin"
# alias docker clean image, ps
alias docker_clean_images='docker rmi $(docker images --filter "dangling=true" -q --no-trunc) && docker rmi $(docker images | grep "none" | awk "/ / { print $3 }")'
alias docker_clean_ps='docker rm $(docker ps -qa --no-trunc --filter "status=exited")'

# $1: head_ref, $2: base_ref
function glc() {
  [[ "$#" != 2 ]]
  local head_ref=$1
  local base_ref=$2
  echo "checkout $head_ref track origin/$base_ref"
  command git fetch --all --prune
  command git checkout $head_ref 2>/dev/null || command git checkout -b $head_ref --track origin/$base_ref
  command git pull --rebase
}
```

### visualstudio code settings.json

`~/Library/Application\ Support/Code/User/settings.json`

```json
{
  "window.zoomLevel": 1,
  "editor.tabSize": 2,
  "workbench.iconTheme": "eq-material-theme-icons-darker",
  "editor.fontSize": 12,
  "editor.formatOnPaste": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "editor.snippetSuggestions": "top",
  "workbench.colorTheme": "Monokai",
  "workbench.colorCustomizations": {}
}

```

Visual studio [Setting Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync) 를 활용하여 extension 관리

## direnvrc

ref: [Roger's Blog](https://blog.differentpla.net/)

in `~/.direnvrc`

```sh
use_nodejs() {
  NODE_VERSION="$1"

  type nvm >/dev/null 2>&1 || . ~/.nvm/nvm.sh
  nvm use "$NODE_VERSION"
}
```

using `.envrc`

```sh
use nodejs v14.17.4
```

### nodejs tool

```bash
npm install -g zx
npm install -g tldr
npm install -g asciicast2gif # cli recording to gif
npm install -g commitizen@4.2.2 @commitlint@11.0.0 cz-conventional-changelog@3.3.0 # for conventional commit
```

### go tool

```bash
go get github.com/oklog/ulid/v2
```

### kubernetes tools

Add kube-ps1, showcurrent kubernetes context

```bash
source "/opt/homebrew/opt/kube-ps1/share/kube-ps1.sh"
PS1='$(kube_ps1)'$PS1
```

stern add bash-completion

```bash
source <(stern --completion=zsh)
```

kubectl zsh, alias k

```bash
alias k=kubectl
complete -F __start_kubectl k

source <(kubectl completion zsh)  # 현재 셸에 zsh의 자동 완성 설정
echo "[[ $commands[kubectl] ]] && source <(kubectl completion zsh)" >> ~/.zshrc # 자동 완성을 zsh 셸에 영구적으로 추가한다.
```
