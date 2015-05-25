Bugbuzz is a web-based debugger. The idea behind it is trying to provide an very easy-to-use debugging experience. Currently it supports Python only. With Bugbuzz, you only need to install the debugging library - [bugbuzz-python](https://github.com/victorlin/bugbuzz-python), drop one line in your code, then you can start debugging, no need to setup anything else. The UI is very friendly, no need to memorize commands, you can click step buttons to trace through the code, or if you are familiar with VIM, you can also use shortcuts to debug like a pro.

# Why yet another debugger

The reason I am creating yet another debugger is, I felt most of debugging tools out there are really hard to use. The most common Python debugger people use is the one build-in with Python - [pdb](https://docs.python.org/2/library/pdb.html).

![Python build-in debugger - pdb screenshot](https://cloud.githubusercontent.com/assets/201615/7790924/8b0dabe2-024a-11e5-86e4-ae46a07699bb.png)

It works, but I bet most of developers feel painful to use it. For me, I really hate to see only one line of code every single step. When you walk through the code, you don't know what's the next line, where the hell am I. You need to constantly type commands to know what's the situation, rather than focus on the problem you're solving. This reminds very ancient game - [MUD](http://en.wikipedia.org/wiki/MUD). I never played one, but I know what it looks like, it's like walking in a dungeon without seeing anything, you need to type command to tell what's infront you, what to do then. Maybe it is really fun in that era, but hey, it's 2015 now, and it's debugger is a tool for developer not a game, can we have something more advance?

Well, actually there is something better - [ipdb](https://pypi.python.org/pypi/ipdb)

![Another debugger - ipdb](https://cloud.githubusercontent.com/assets/201615/7791008/8406135a-024c-11e5-91be-75673ad5c543.png)

It's enhanced pdb, you have auto-complete, syntax highlight and mutiple lines displaying. But still, the way it works is still like pdb. You need to ask for trivials things while you debug.


# Getting started

# Shortcuts

# Security concern

# The future

# Alternative solution
