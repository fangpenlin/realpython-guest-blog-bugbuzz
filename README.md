Bugbuzz is a web-based debugger. The idea behind it is trying to provide an very easy-to-use debugging experience. Currently it supports Python only. With Bugbuzz, you only need to install the debugging library - [bugbuzz-python](https://github.com/victorlin/bugbuzz-python), drop one line in your code, then you can start debugging, no need to setup anything else. The UI is very friendly, no need to memorize commands, you can click step buttons to trace through the code, or if you are familiar with VIM, you can also use shortcuts to debug like a pro.

![Bugbuzz screenshot](https://cloud.githubusercontent.com/assets/201615/7791039/504bf5ba-024d-11e5-9f19-ec865b1e5b36.png)

# Why yet another debugger

The reason I am creating yet another debugger is, I felt most of debugging tools out there are really hard to use. The most common Python debugger people use is the one build-in with Python - [pdb](https://docs.python.org/2/library/pdb.html).

![Python build-in debugger - pdb screenshot](https://cloud.githubusercontent.com/assets/201615/7790924/8b0dabe2-024a-11e5-86e4-ae46a07699bb.png)

It works, but I bet most of developers feel painful to use it. For me, I really hate to see only one line of code every single step. When you walk through the code, you don't know what's the next few lines, where the hell am I. You need to constantly type commands to know what's the situation, rather than focus on the problem you're solving. This reminds very a kind of ancient game - [MUD](http://en.wikipedia.org/wiki/MUD). I never played one, but I know what it looks like, it's like walking in a dungeon without seeing anything, you need to type command to tell what's infront you, what to do then. Maybe it is really fun in that era, but hey, it's 2015 now, and debugger is a tool for developer not a game, can we have something more advance?

Well, actually there is something better - [ipdb](https://pypi.python.org/pypi/ipdb)

![Another debugger - ipdb](https://cloud.githubusercontent.com/assets/201615/7791008/8406135a-024c-11e5-91be-75673ad5c543.png)

It's basically enhanced pdb, you have auto-complete, syntax highlight and mutiple lines displaying. But still, the way it works is still like pdb. You need to ask for trivials things while you debug.

There are actually more advance tools, like [Pydev](http://pydev.org), it's an IDE for Python based on Eclipse. Other similar IDEs can also provide better debugging experience. Although it's better experience, I still don't like IDE debugger for some reasons

 - You need to install IDE and configure to use the debugger
 - You need to add a project to use it
 - It's hard to do remote debugging, e.g. in a vagrant environment or remote server

I still miss the ability drop one line of code and start debugging. I wondered, well, we are in cloud and big data era, why not make the debugger as a software-as-service? In my dream, I want is to drop a new line, then open the debugger with fancy UI in the browser. I can read the complete source code, click around to see what's going on here. With the idea in my mind, so I spent some time created this pet project called Bugbuzz.

# Getting started

Bugbuzz is pretty easy to use, all you need to do is install the library package

```bash
pip install bugbuzz
```

then drop a line in the python file you like to debug

```
import bugbuzz; bugbuzz.set_trace()
```

for example, you have a simple python script like this

example.py:
```python
for i in range(10):
    print i
```

to debug it, you can drop it at the first line

example.py:
```python
import bugbuzz; bugbuzz.set_trace()
for i in range(10):
    print i
```

then run it

```
python example.py
```

and here you go, it should opens the debugger page on browser for you. If you are debuggin on a server, it might not be able to open the URL for you, as it will display the URL in stderr like this

```
Access Key: <ACCESS KEY>
Dashboard URL: http://dashboard.bugbuzz.io/#/sessions/SEY76Jq2hxgPFPNeA9BLmqqV?access_key=<ACCESS KEY>
```

You can copy it and paste on your browser.

# Shortcuts

If you are familiar with VIM shortcuts, then it won't be too difficult for you to pick up Bugbuzz shortcuts.

 - C Continue
 - H Return
 - J Next
 - L Step

As you can think it's like browsing code, J is down, so it's next line, and L is right, so you are step into a funtion call. H is left, so you are leaving a function call, so that would be run until return a function.

# Security concern

# The future

# Alternative solution
