# init-linux-shell

### Things
* https://github.com/robbyrussell/oh-my-zsh
* https://github.com/junegunn/fzf
* https://sw.kovidgoyal.net/kitty/overview/
* https://github.com/romkatv/powerlevel10k

### brew

```
brew install jq
brew install autojump
brew install git-extras
brew tap homebrew/cask
brew install --cask jumpcut
# brew install txn2/tap/kubefwd
# brew install kubectx stern fzf kube-ps1 derailed/k9s/k9s kustomize helm minikube hyperkit htop dockerd kube-ps1
brew install fzf htop
brew install --cask docker
# brew install --cask 
# brew install nmap
brew install --cask signal
```
Links:
* https://github.com/ahmetb/kubectx


######################## ZSH start ######################
### .zshrc
```
alias toJson='jq .'
plugins=(git dirhistory sublime colorize copydir)
ZSH_THEME="gnzh"

function aws_login_template {
        eval $(AWS_PROFILE=backup aws sts get-session-token --serial-number arn:aws:iam::number:mfa/grzegorz.miejski --token-code $1 | jq -r '.Credentials | @sh "export AWS_SESSION_TOKEN=\(.SessionToken)\nexport AWS_ACCESS_KEY_ID=\(.AccessKeyId)\nexport AWS_SECRET_ACCESS_KEY=\(.SecretAccessKey) "')
}

alias gcp=gcloud

function kk {
        source "/usr/local/opt/kube-ps1/share/kube-ps1.sh"
        PS1='$(kube_ps1)'$PS1
}

alias kn="kubens"
alias kc="kubectx"
alias k='kubectl'

function clearAppK8S {
        if [[ -z $ENV || -z $APP ]]
        then
                echo "ENV and APP needs to be defined"
                return
        fi
        kubectl -n $ENV delete deployment/$APP;
        kubectl -n $ENV delete svc $APP;
        kubectl -n $ENV delete sa $APP;
        kubectl -n $ENV delete ing $APP;
        kubectl -n $ENV delete hpa $APP;
        kubectl -n $ENV delete pvc $APP-pvc;
        kubectl -n $ENV delete middleware $APP;
}

alias dockerKillAll="docker kill $(docker ps -q)"
```
######################## ZSH end ######################

### iTerm2

* https://elweb.co/making-iterm-2-work-with-normal-mac-osx-keyboard-shortcuts/
* https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x

Working key mapping: 
```
⌥ Option + <- == "send escape sequence 'b'"
⌥ Option + -> == "send escape sequence 'f'"
⌥ Option + Delete == "Send Hex codes: 0x1B 0x08"
```

