# Bugbuzz - a web-based python debugger

**Let's look at [Bugbuzz](https://github.com/victorlin/bugbuzz-python), an open source, web-based debugger that provides an easy-to-use debugging experience.**

![Bugbuzz screenshot](https://cloud.githubusercontent.com/assets/201615/7791039/504bf5ba-024d-11e5-9f19-ec865b1e5b36.png)

With Bugbuzz, you just need to install the debugging library, drop one line of code into your codebase, and then you can immediately start debugging your code. That's it! There's no need to setup anything else. The UI is super friendly. You don't have to memorize commands; instead, you simply click buttons to trace through the code, or if you are familiar with VIM, you can also use shortcuts to debug like a pro.

Finally, since it's in the cloud, you can share debugging sessions with your co-workers - you can debug together, seek out help, or explain to them how the program works. It can also be a great learning tool for those new to debugging.

## Yet Another Debugger?

Let's face it: Most of the debugging tools out there are really hard to use.

The most common Python debugger is [pdb](https://docs.python.org/2/library/pdb.html), which is part of the standard library. 

![Python build-in debugger - pdb screenshot](https://cloud.githubusercontent.com/assets/201615/7790924/8b0dabe2-024a-11e5-86e4-ae46a07699bb.png)

It gets the job done, but it can be painful at times and it's a struggle for many to learn.

For starters, as you walk through the code, you see only one line of code at each step. You don't know what the next few lines show or, really, where the hell you're at in the program. You need to constantly type commands to know what's happening, rather than focus on the problem you're solving. 

It's sort of like playing the ancient [MUD](http://en.wikipedia.org/wiki/MUD) game, where the main player walks around the game world without seeing anything. You need to type a command to tell what's in front of you and what action should be performed. Maybe it is really fun in that era, but hey - It's 2015 now. We need a more advanced debugger that's not only easier to learn and use.

Sure, there is [ipdb](https://pypi.python.org/pypi/ipdb)-

![Another debugger - ipdb](https://cloud.githubusercontent.com/assets/201615/7791008/8406135a-024c-11e5-91be-75673ad5c543.png)

-but it's basically an enhanced version of pdb. You get auto-complete, syntax highlighting and multiple lines are displayed. Unfortunately, it still works in much the same way as pdb: You need to ask for trivial, distracting things while you debug, which takes away from the actual debugging experience.

There are more advance tools that come packaged with IDEs, like [Pydev](http://pydev.org), which provide a better debugging experience. However, there are a number of downsides to this approach:

 - First and foremost, you need to (possibly) purchase and install the IDE, and then configure to use the debugger
 - You also need to create a project to use it
 - It's hard to do remote debugging - e.g., in a vagrant environment or remote server

In essence, you lose the simplicity that pdb offers. Setup becomes much more than just adding a single line of code to your program, in other words.

So, since we are in the cloud and big-data era, why is there not a simple debugger that operates as a software-as-service? The goal is to coupled the simplicity of pdb - e.g., having to only add a single line of code and then you're ready to debug - with a fancy UI where you can read the complete source code, and click around to see what's happening in order to debug. 

Enter Bugbuzz.

## Getting Started

Install the package globally:

```sh
$ pip install bugbuzz
```

And then drop a line in the python file you want to debug, like so:

```python
import bugbuzz; bugbuzz.set_trace()
```

Now you're ready to debug!

For example, add the following code to a file called *example.py*:

```python
for i in range(10):
    print i
```

To debug it, you can just add `import bugbuzz; bugbuzz.set_trace()` just above the first line of code:

```python
import bugbuzz; bugbuzz.set_trace()
for i in range(10):
    print i
```

Then run the script:

```sh
$ python example.py
```

And there you go. This should open the debugger in the browser for you.

> **NOTE** If you are debugging on a remote server, it might not be able to open the URL for you, however, you will see the URL in `stderr`:

>    ```sh
    Access Key: <ACCESS KEY>
    Dashboard URL: http://dashboard.bugbuzz.io/#/sessions/SEY76Jq2hxgPFPNeA9BLmqqV?access_key=<ACCESS KEY>
    ```

> Just copy the URL and paste into your local browser.

## Shortcuts

If you' re familiar with VIM shortcuts, then it won't be too difficult for you to pick up the Bugbuzz [shortcuts](ADD LINK).

 - *C*: Continue
 - *H*: Return
 - *J*: Next
 - *L*: Step

As you can tell it's like browsing code- J is down, so it's next line, and L is right, allowing you to step into a function call. H is left, so you leave a function call.

## Security concern

As you can tell, since the debugging is provided as a service, the Bugbuzz client library uploads all source code and local variables needed to the server. Don't worry: The source code is encrypted before it's uploaded to the server, and you must have the access key to decrypt it.

## The future

As a prototype, Bugbuzz can only do very basic things for now, yet it shows a very promising start. Feel free to let me know if you have any feedback of if you'd like to contribute! 

Cheers!
