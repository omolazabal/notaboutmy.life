---
title: Maintaining Your Dotfiles 
categories: [Tutorial, Unix]
tags: [tutorial, software, unix, linux, mac]
---

# Overview
This article will suggest how you can organize and maintain your favorite dotfiles. Additionally, we'll go over the dotfiles I like to maintain.

# Introduction
Dotfiles are a set of configuration files for Unix and Unix-like systems. They are called dotfiles because the file names typically start with a dot (.bash_rc, .profile) to remain hidden from the user. They are typically hidden in the user's home directory.

> To view the dotfiles in your home directory, go ahead and run `ls -la ~` in your terminal

A lot of your favorite programs might be using these types of files, so it is often best to utilize some sort of version control to maintain them. This is especially useful if you find yourself using multiple computers.

----

# Organizing Your Dotfiles
## Creating Your Dotfiles Repository
The best way I've found to organize my dotfiles is to place my most relevant ones into a directory and version control the directory using Git and GitHub. This is useful for two reasons:  

1. It allows me to keep track of the states of my dotfiles. If I update a setting find that I do not like it, I can revert back to it by checking my Git logs.
2. If I'm working on a new computer, I can easily fetch my dotfiles from GitHub and put them to use immediately.

To set up your repository, simply create a repository on GitHub and name it `dotfiles` (be sure to make the repository private if you do not wish for others to see your configurations). Then, on your computer, clone your `dotfiles` repository in your home directory.

Next we'll be looking into how you can safely move your dotfiles into your `dotfiles` repository.


## Symbolic linking
Symbolic links are files that point to another file. They are different from hard links as they do not contain any data associated with the file being pointed to. We will be leveraging symbolic links to place our dotfiles into our `dotfiles` repository without breaking anything.

Symbolic links are created with the following command pattern.
```console
ln -s source_file link_file
```
Where `source_file` represents existing dotfile, and `link_file` represents the new file that will be pointing to your existing dotfile.

To safely move our existing dotfiles without breaking anything we want to
1. Move the dotfile into our `dotfiles` repository
2. Create a symbolic link of that dotfile and place it in the dotfile's original location. It is important to not where your dotfile's original location was.

This way, whenever the program needs to utilize your dotfile, it will reference it from its new location.

For example, to link your `.bash_rc` file, you would want to perform the following:
```console
mkdir ~/dotfiles/bash                        # Create a directory to hold your new dotfile (optional)
mv ~/.bash_rc ~/dotfiles/bash                # Move the dotfile from its origin to the dotfile repository
ln -s ~/dotfiles/bash/.bash_rc ~/.bash_rc    # Create a link to the dotfile. Place it in the dotfile's original location
```

And there you have it! You can now edit your files in the `dotfiles` repository and perform proper version control on them. Additionally you can push them to GitHub so you can access them anywhere.

# My Dotfiles

My main computers are a Linux machine and a Macbook Pro. Due to their differences, I have two set of dotfiles, one for my [Mac](https://github.com/omolazabal/dotfiles-mac), the other for my [Linux desktop](https://github.com/omolazabal/dotfiles-linux).

The dotfiles that I keep track of are the ones for:
- [Git](https://git-scm.com/)
- [Pandoc](https://pandoc.org/)
- [Tmux](https://github.com/tmux/tmux)
- [Vim](https://github.com/vim/vim)
- [VSCode](https://code.visualstudio.com/)
- [Oh My ZSH](https://ohmyz.sh/)
- [iTerm 2](https://www.iterm2.com/) (MacOS only)
- [Übersicht](http://tracesof.net/uebersicht/) (MacOS only)

Below I present how to install my dotfiles. Be sure to take a look at them first and see if they are any use for you.
- [Mac Dotfiles](https://github.com/omolazabal/dotfiles-mac)
- [Linux Dotfiles](https://github.com/omolazabal/dotfiles-linux)

## Git
### Mac
#### Install
```console
run xcode-select --install
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
#### Configure
```console
mkdir -p ~/dotfiles/git
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/git/.gitconfig -P ~/dotfiles/git
rm ~/.gitconfig
ln -s ~/dotfiles/git/.gitconfig ~/.gitconfig
```

### Linux
#### Install
```console
sudo apt install git -y
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
#### Configure
```console
mkdir -p ~/dotfiles/git
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/git/.gitconfig -P ~/dotfiles/git
rm ~/.gitconfig
ln -s ~/dotfiles/git/.gitconfig ~/.gitconfig
```


## Tmux
### Mac
#### Install
```console
brew install tmux
```
#### Configure
```console
mkdir -p ~/dotfiles/tmux
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/tmux/.tmux.conf -P ~/dotfiles/tmux
rm ~/.tmux.conf
ln -s ~/dotfiles/tmux/.tmux.conf ~/.tmux.conf
```


### Linux
#### Install
```console
sudo apt install tmux -y
```
#### Configure
```console
mkdir -p ~/dotfiles/tmux
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/tmux/.tmux.conf -P ~/dotfiles/tmux
rm ~/.tmux.conf
ln -s ~/dotfiles/tmux/.tmux.conf ~/.tmux.conf
```

## Vim
### Mac
#### Install
```console
brew install vim
```
#### Configure
```console
mkdir -p ~/dotfiles/vim
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vim/.vimrc -P ~/dotfiles/vim
rm ~/.vimrc
ln -s ~/dotfiles/vim/.vimrc ~/.vimrc
```
### Linux
#### Install
```console
sudo apt install vim -y
```
#### Configure
```console
mkdir -p ~/dotfiles/vim
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vim/.vimrc -P ~/dotfiles/vim
rm ~/.vimrc
ln -s ~/dotfiles/vim/.vimrc ~/.vimrc
```
		
## VSCode
### Mac
#### Install
- visit https://code.visualstudio.com/download
- Double click zip file to unzip
- Drag the .app file into you Applications folder

#### Configure
```console
mkdir -p ~/dotfiles/vscode
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vscode/settings.json -P ~/dotfiles/vscode
rm ~/Library/Application Support/Code/User/settings.json
ln -s ~/dotfiles/vscode/settings.json ~/Library/Application Support/Code/User/settings.json
```

```console
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vscode/keybindings.json -P ~/dotfiles/vscode
rm ~/Library/Application Support/Code/User/keybindings.json
ln -s ~/dotfiles/vscode/keybindings.json ~/Library/Application Support/Code/User/keybindings.json
```

### Linux
#### Install
- visit https://code.visualstudio.com/download
- run `sudo dpkg -i <filename>` on your installation

#### Configure
```console
mkdir -p ~/dotfiles/vscode
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vscode/settings.json -P ~/dotfiles/vscode
rm ~/.config/Code/User/settings.json
ln -s ~/dotfiles/vscode/settings.json ~/.config/Code/User/settings.json
```
```console
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vscode/keybindings.json -P ~/dotfiles/vscode
rm ~/.config/Code/User/keybindings.json
ln -s ~/dotfiles/vscode/keybindings.json ~/.config/Code/User/keybindings.json
```

## ZSH
### Mac
#### Install
```console
brew install zsh
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# Make it the default shell
```
#### Configure
```console
mkdir -p ~/dotfiles/zsh
wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/zsh/.zshrc -P ~/dotfiles/zsh
rm ~/.zshrc
ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc
mkdir -p "$HOME/.zsh"
git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
brew install autojump
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
source ~/.zshrc
```
### Linux
#### Install
```console
sudo apt install zsh -y
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# Make it the default shell
```
#### Configure
```console
mkdir -p ~/dotfiles/zsh
wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/zsh/.zshrc -P ~/dotfiles/zsh
rm ~/.zshrc
ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc
mkdir -p "$HOME/.zsh"
git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
sudo apt install autojump -y
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
source ~/.zshrc
```