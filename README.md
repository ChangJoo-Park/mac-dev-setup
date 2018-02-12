# Mac 환경 설정 모음

개발환경 및 자주 사용하는 프로그램 설치는 Homebrew와 Brewfile을 이용합니다.

```bash
# Homebrew 설치
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# 이 저장소 클론
git clone https://github.com/ChangJoo-Park/mac-dev-setup
cd mac-dev-setup

# Brewfile 실행
brew bundle
```

## 시스템 업데이트

  - High Sierra

```bash
# 전체 소프트웨어 업데이트
sudo softwareupdate -ia 
# 매일 업데이트 확인
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1
```

## 시스템 설정

  - Spotlight 단축키 변경
  - 한영 전환 키 변경
  - 한글에서 백틱 (`) 사용하기
```bash
mkdir ~/Library/KeyBindings
touch ~/Library/KeyBindings/DefaultkeyBinding.dict
echo '{ "₩" = ("insertText:", "`"); }' >> ~/Library/KeyBindings/DefaultkeyBinding.dict
```

  - Dashboard 사용 중지 
```bash
defaults write com.apple.dashboard mcx-disabled -boolean YES 
killall Dock 
```

  - 트랙패드 탭 활성화
```bash
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true
defaults -currentHost write NSGlobalDomain com.apple.mouse.tapBehavior -int 1
defaults write NSGlobalDomain com.apple.mouse.tapBehavior -int 1
```

  - 숨긴 파일 보기
```bash
defaults write com.apple.finder AppleShowAllFiles -bool true
```
  
  - .DS_Store 방지
```bash
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
```

## 폰트

  - [FiraCode](https://github.com/tonsky/FiraCode) : font-ligature 지원 monospace 폰트
  - [FlottFlott](http://www.dafont.com/flottflott.font) : italic, Operator Mono 폰트 대용으로 사용


## 터미널

  - iTerm2
  - iTerm2 Color Scheme - [Adventure Time](https://github.com/mbadolato/iTerm2-Color-Schemes/blob/master/schemes/AdventureTime.itermcolors)
  - zsh
```
# zsh 을 기본으로 설정
chsh -s /bin/zsh
```
  - oh-my-zsh
```
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
```
  - zsh theme - [spaceship](https://github.com/denysdovhan/spaceship-zsh-theme)
```shell
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"

# ./zshrc 에 테마 설정
ZSH_THEME="spaceship"
```
  - zsh autosuggestion
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
```

  - ssh-keygen
```
ssh-keygen -t rsa -b 4096 -C "pcjpcj2@gmail.com"
cat ~/.ssh/id_rsa.pub | pbcopy
```


## 커맨드라인 인터페이스 도구

  - Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
  - Heroku
  - NVM
  - git
```
git config --global user.name "ChangJoo Park"
git config --global user.email "pcjpcj2@gmail.com"
```
  - TaskWarrior
  - openssl
  - mas


## 언어

  - Ruby
```bash
# rbenv in ~/.zshrc
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc

# rbenv 문제로 Ruby를 설치할 수 없을 때, 2.5.0은 사용할 Ruby 버전
RUBY_CONFIGURE_OPTS=--with-readline-dir="$(brew --prefix readline)" rbenv install 2.5.0
```
  - Python 
  - Node.js
  - Vue CLI 3.x
```bash
yarn global add @vue/cli
```
  - Crystal
  - Amber Framework

## 프로그램
  
  - Visual Studio Code
  - Google Chrome
  - Dash
  - Alfred
  - Boom3d
  - Postman
  - Spotify
  - TunnelBear
  - Xcode
  - SourceTree
  - Sequel Pro
  - Caret
  - YakYak
  - Slack
  - Caret
  - Popclip


## Chrome 확장 프로그램

## Visual Studio Code

  - [Vue Development Extension Pack](https://marketplace.visualstudio.com/items?itemName=changjoo-park.vscode-vue-devpack)
    - [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur) - :)
    - [vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)
    - [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    - [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame)
    - [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
    - [Git Project Manager](https://marketplace.visualstudio.com/items?itemName=felipecaputo.git-project-manager)
    - [Sublime Text Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings)
    - [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
    - [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.bookmarks)
    - [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics)
    - [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
    - [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
    - [JavaScript Snippet Pack](https://marketplace.visualstudio.com/items?itemName=xabikos.javascriptsnippets)
    - [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)
    - [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
    - [npm Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
    - [Quokka](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)
    - [Rest Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
    - [Todo Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
    - [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)


## 기본 디렉터리
  - ~/Developments
