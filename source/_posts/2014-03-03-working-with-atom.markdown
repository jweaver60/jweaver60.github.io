---
layout: post
title: "Working with Atom"
date: 2014-03-03 18:56:15 -0500
comments: true
categories: [tools, editors, javascript]
---

I was fortunate enough to get access to Github's latest hotness, a new text editor called [Atom](http://www.atom.io). While this editor is
most definitely still in beta, it has already seen a lot of traction that has plagued other contenders in the text editor arena, such as
Brackets. Atom is built on top of node and web developers with experience in JavaScript (specifically CoffeeScript) will have a pretty easy
time developing packages for Atom as well as extending it. Let's go over some of the cool things Atom has to offer, as well as some of the
gotchas.
<!-- more -->
Users of Sublime Text will be nearly instantly at home with Atom. Atom sports a navigable file tree to the left and tabs to indicate all
of your open files. Atom already has support for a lot of languages and more are coming frequently. I already found a package to add blade
syntax support (although that package has mysteriously vanished since then). What's really great is that package management functionality
is built right into Atom, as opposed to Sublime Text which makes use of the fantastic Package Control plugin. You can open settings in Atom
and instantly search for additional packages and themes.

{% img /images/atom.png 'Atom' %}

Another cool feature of Atom is the integrated support for Git. The editor will tell you what branch you are on, what lines of your file have
changed and in the left navigation show what files and directories have uncommitted changes. I guess this support shouldn't be to surprising
considering who is creating this application, but it's particularly helpful to see at a quick glance what has changed.

{% img /images/dirty-tree.png 'Dirty Tree' %}

I really like this editor and can see it quickly becoming my primary text editor. There are still some bugs, primarily with the Emmet plugin,
but I find these things are quickly getting fixed. In addition, the ability to customize the editor with JavaScript makes it accessible to me
to develop for and extend. I'm looking forward to some great things from Atom.
