# Notes from setting up a new machine

Happy to take tips on how to do this a bit more seemlessly!

* Following me on Twitter: [@JalisoCSP](https://twitter.com/JalisoCSP)
* Check out my personal site: https://craigpetterson.co.uk
* Check out my dotfiles: https://github.com/JalisoCSP/dotfiles

---

## Development Setup

### Terminal

* Font size: 14
* TODO: Review Rosetta option? Not had any issues yet, maybe was only issue with M1 when it was a new release

### Generate new SSH key

From Github settings: https://github.com/settings/keys

* Follow these steps from Github: https://docs.github.com/authentication/connecting-to-github-with-ssh
* Add public key to authorized keys in dotfiles: https://github.com/JalisoCSP/dotfiles/blob/master/ssh/authorized_keys.pub

### Install Homebrew

Double check command at: https://brew.sh/

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Clone dotfiles

* Trying to use a git command will suggest installing developer tools, do this

Copy aliases, vim & tmux settings, etc

```
git clone https://github.com/JalisoCSP/dotfiles ~/.dotfiles
cd ~/.dotfiles
rake install
```

### Setup list

* Setting up `rbenv` first, otherwise there is `gem install` issues with write permissions

```
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory.
```

#### Rbenv

https://github.com/rbenv/rbenv

```
brew install rbenv ruby-build
rbenv install <version>
rbenv global <version>
```

* No need to add `eval "$(rbenv init - zsh)"` to ~/.zshrc, that will already be done with the dotfiles
* Make sure to restart terminal after this point (just fully close and reopen)

#### Vim

Nothing to do? Dotfiles take care of my usual set up

#### Tmuxinator

https://github.com/tmuxinator/tmuxinator

```
gem install tmuxinator
brew install tmuxinator
```

TODO: Setup standard tmux project in dotfiles

#### Bundler

```
gem install bundler
```

#### NVM

????

### Project setup

TODO:
* Pull a project down
* Steps to get server up and running
* Thinking: postgresql, redis, etc
