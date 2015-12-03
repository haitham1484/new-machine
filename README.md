# new-machine
Setting up a new OSX machine
For now, writing a list of everything. Then I'll write a script to automate.

- Xcode Licence Agreement
- Install iTerm 2.
- Install zsh + oh-my-zsh
- Install Homebrew.


**Setup vim**      
- Install vim with clipboard+ and python+ support.
```
$ brew install vim --override-system-vi
$ vim --version | grep python 
python+
$ vim --version | grep clipboard
clipboard+
$ whereis vim --version | grep clipboard
/usr/bin/vim
```
- Install vundle.
Follow steps from [here](https://github.com/VundleVim/Vundle.vim).
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
and then do `:PluginInstall` inside vim.

**Setup tmux**    
```
brew install tmux
brew install reattach-to-user-namespace
```


