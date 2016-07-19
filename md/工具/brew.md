### <center style="color:#238E23"> mac homebrew

##### 1.安装
  `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

##### 2.常用命令
  ```
  自检
    brew doctor
  更新
    brew update
  安装php
    brew install php55
    brew remove php55
    brew upgrade php55  //升级
    brew options php55  // 查看php55 安装选项
    brew home php55
    brew info php55

 ```
##### 3.安装cask
  ```
   brew tap phinze/homebrew-cask && brew install brew-cask
  ```
##### 4.安装开发包
 ```
  brew install wget watch tmux cmake openssl imagemagick graphicsmagick gearman geoip readline autoconf multitail source-highlight autojump zsh-completions sshfs
 ```
##### 5.升级系统自带的vim
 `brew install ctags macvim --env-std --override-system-vim`
