# Notes from setting up a new machine

Happy to take tips on how to do this a bit more seemlessly!

* Following me on Twitter: [@JalisoCSP](https://twitter.com/JalisoCSP)
* Check out my personal site: https://craigpetterson.co.uk
* Check out my dotfiles: https://github.com/JalisoCSP/dotfiles

---

### Generate new SSH key

From Github settings: https://github.com/settings/keys

https://docs.github.com/authentication/connecting-to-github-with-ssh

### Install Homebrew

Check command at: https://brew.sh/

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Clone dotfiles

- Got an error here, that could be reviewed
- Trying to use a git command will suggest installing developer tools, do this

Copy aliases, vim & tmux settings, etc

```
git clone https://github.com/JalisoCSP/dotfiles ~/.dotfiles
cd ~/.dotfiles
rake install
```

### Setup list

* Vim
* Tmuxinator: https://github.com/tmuxinator/tmuxinator

#### Rbenv

https://github.com/rbenv/rbenv

```
brew install rbenv ruby-build
```

No need to add `eval "$(rbenv init - zsh)"` to ~/.zshrc, that will already be done with the dotfiles
