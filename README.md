# init-linux-shell

### Things
* https://github.com/robbyrussell/oh-my-zsh
* https://github.com/junegunn/fzf

### brew

```
brew install jq
brew install autojump
brew install git-extras
brew tap homebrew/cask
brew cask install jumpcut
brew install txn2/tap/kubefwd

```



### .zshrc
* alias toJson='jq .'
* plugins=(git dirhistory sublime colorize copydir)
* ZSH_THEME="gnzh"

### iTerm2

* https://elweb.co/making-iterm-2-work-with-normal-mac-osx-keyboard-shortcuts/
* https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x

Working key mapping: 
```
⌥ Option + <- == "send escape sequence 'b'"
⌥ Option + -> == "send escape sequence 'f'"
⌥ Option + Delete == "Send Hex codes: 0x1B 0x08"
```
