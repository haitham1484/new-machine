# new-machine
Setting up a new OSX machine
For now, writing a list of everything. Then I'll write a script to automate.

First you'll need to download Xcode and accept the Xcode Licence Agreement.

## Homebrew
  
Install Homebrew.
```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
Install [Cask](http://caskroom.io/).
```
$ brew install caskroom/cask/brew-cask
```
Install Chrome and then [KeepingYouAwake](https://github.com/newmarcel/KeepingYouAwake), a Caffeine clone
```
$ brew cask install iterm
$ brew cask install google-chrome
$ brew cask install keepingyouawake
```

## git
```
$ brew install git
$ git config --global alias.co checkout
$ git config --global alias.fb "!sh -c \"git checkout feature/foo-$1\" -"
$ git config --global alias.st status
$ git config --global alias.ci commit -v
$ git config --global alias.lg log --oneline --decorate --all --graph¬
```


## vim

**Setup vim**      
Install vim with clipboard+ and python+ support.
```
$ brew install vim --override-system-vi
$ vim --version | grep python 
python+
$ vim --version | grep clipboard
clipboard+
$ whereis vim --version | grep clipboard
/usr/bin/vim
```
**Install vundle**

Follow steps from [here](https://github.com/VundleVim/Vundle.vim).
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
and then do `:PluginInstall` inside vim.

## tmux
**Setup tmux**    
```
brew install tmux
brew install reattach-to-user-namespace
```

**Automatically start tmux when you create iTerm session**    
Open iTerm Preferences. Go to *Profiles* at the top, *General* tab.
In the *Send text at start:* field, enter the following:
```
tmux new
```

**Add a shortcut to make scrolling in copy mode easier**    
Add the following the iTerm Profile Keys:    

- CTRL+U = Send Page Up
- CTRL+D = Send Page Down


## Unix

```
$brew install pidof
```

## Ruby
**Setup rbenv**    
```
$ brew install rbenv ruby-build
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
$ source ~/.bash_profile
```

**Install Ruby**    
Find the latest version number, `<version>`, of Ruby.    
At the time of writing, `<version> = 2.2.3`.
Install this version via `rbenv install`.
```
$ rbenv install <version>
```
Then point global ruby to be this version:
```
$ rbenv global
system
$ rbenv global <version>
$ rbenv global
2.3.3
$ ruby -v
ruby 2.2.3p173 (2015-08-18 revision 51636) [x86_64-darwin14]
```

**Setup Bundler**    
```
$ ruby -r bundler -e "puts RUBY_VERSION"
(an error complaining about bundler being missing)
$ gem install bundler
$ ruby -r bundler -e "puts RUBY_VERSION"
2.2.3
$ brew install rbenv-bundler
$ rbenv bundler on
```

**Local Ruby Project**     
Suppose you have written a Gemfile for a project. To install the gems:
```
$ rbenv local <version>
$ gem install bundler
$ bundle install
```
where `<version>` is the desired version of Ruby.  
