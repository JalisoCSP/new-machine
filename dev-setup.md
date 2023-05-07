# Development Setup

* Check out my dotfiles: https://github.com/JalisoCSP/dotfiles

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

Copy aliases, vim & tmux settings, etc

* Trying to use a git command will suggest installing developer tools, do this

```
git clone https://github.com/JalisoCSP/dotfiles ~/.dotfiles
cd ~/.dotfiles
rake install
```

## Setup list

#### Vim

Nothing to do? Dotfiles take care of my usual set up

#### Tmuxinator

https://github.com/tmuxinator/tmuxinator

```
gem install tmuxinator
brew install tmuxinator
```

**TODO**: Setup standard tmux project in dotfiles

### ASDF

https://github.com/asdf-vm/asdf

Following steps from the Getting Started guide: https://asdf-vm.com/guide/getting-started.html

Check they are up to date

Install dependencies:

```
brew install coreutils curl git gpg gawk
```

Download ASDF:

```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf
```

Symlink to avoid version issues: https://github.com/asdf-vm/asdf/issues/418#issuecomment-454372616

**TODO**: See if this symlink can be added to dotfiles `rake install`

```
sudo ln -s /usr/local/opt/asdf/libexec/ /usr/local/libexec
```

* No need to add `$(brew --prefix asdf)/libexec/asdf.sh` to ~/.zshrc, that will already be done with the dotfiles
* Make sure to restart terminal after this point (just fully close and reopen, rather than messing around with `source`)

### Ruby

Versions: https://www.ruby-lang.org/en/downloads/releases/

```
asdf plugin add ruby
asdf install ruby <version>
asdf global ruby <version>
gem update --system
```

### Node

Versions: https://nodejs.org/en/download/releases

```
asdf plugin add nodejs
asdf install nodejs <version>
asdf global nodejs <version>
```

### PostgresQL

Versions: https://www.postgresql.org/support/versioning/

```
brew install libpq
brew install postgresql # requires libpq
brew services start postgresql
```

#### Standard Gems

```
gem install bundler rails
```
