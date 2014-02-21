---
layout: post
title: "Keeping a Clean System"
date: 2014-02-21 17:55:31 -0500
comments: true
categories: [Shell, Maintenance]
---

In the process of development, we often end up with a lot of tools on or systems. We install different databases, shells, languages, version control systems, etc. After a while it can be pretty hard to keep up with what's on your system and where, and also what needs to be updated. I wanted to share my method for keeping things up-to-date as simply as possible.
<!-- more -->
The first thing you need to do if you're on OS X and not already doing it, is install everything you possibly can through [homebrew](http://brew.sh/). I use it to install mysql, postgres, git, php, node.js, mongodb, vim, zsh and a bunch of other things. Homebrew does a lot of things for you, installing packages in a single directory and automatically loading them in your PATH (provided you have the homebrew directory in your PATH). The only thing I don't install with homebrew is ruby (there's [RVM](http://www.rvm.io) for that). Even if your system already comes with some of these things, installing them with homebrew makes sure you have the latest versions. Homebrew also updates all of your packages with a single command, so you don't have to track these down individually and run multiple updates. If there's an update, homebrew gets it extremely quickly and you'll be up and running with the latest in no time.

I make a habit to update all of my packages every morning when I start work, and to make it even easier I wrote a quick shell script to get everything done in one command. Modify this as you see fit.

``` bash
goodmorning() {
	echo "updating packages"
	brew update
	echo "updating any packages"
	brew upgrade
	echo "cleaning up old packages"
	brew cleanup
	echo "checking homebrew for errors"
	brew doctor
	echo "All good!"
	cd ~/.vim/autoload
	echo "updating pathogen"
	curl -O https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim
	echo "Pathogen updated!"
	for i in `ls` do
		cd "$i"
		echo "updating $i"
		git pull
		cd ..
	done
	cd ~
	echo "updating RVM"
	rvm get stable
	echo "cleaning up RVM"
	rvm cleanup all
	echo "Good to go!"
}
```
I hope this is helpful for you, if so, or if you'd like to change anything, let me know!
