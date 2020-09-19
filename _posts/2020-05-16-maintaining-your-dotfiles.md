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

