%title: A Brief introduction to tmux
%author: murph	
%date: 2024-03-29

-> A brief introduction to tmux <-

# What is it?

tmux is a terminal multiplexer.  It allows a user to run multiple windows, and manipulate them out of a single ssh or console session.  This can be very useful in limited access situations.  It also allows for the continuation of a session, even if it is accidentally cut off.

---

# Introduction:  

I'm murph, a Linux systems administrator in NJ, and long time desktop Linux user, and EFF supporter.

The slides are at **https://murphnj.neocities.org**

You can ask questions via email at murph@weirdness.com or on The Fediverse with Mastodon at

@murph@hackers.town or @murph@gardenstate.social

---

# How to install tmux.

On most versions of Linux, it's in the repositories, so installing is easy:

Redhat and similar distros:

`yum install tmux` or `dnf install tmux`

Debian/Ubuntu and similar:

`apt install tmux`

Arch and similar:

`pacman -S tmux`

These commands also tend to work on WSL, if that's where you're trying this from, use the Linux command corresponding to the distro you're using.

On the Mac, either Homebrew or MacPorts are the way to install.
`brew install tmux`  or `port install tmux`

---

# Getting started with tmux.

To start tmux, simply type tmux at a command prompt.

You'll see a command prompt, just like before, but at the bottom of the window, you'll notice that there's a status bar with the current command, the hostname, and the time and date.

This is the basic screen, to activate tmux, you need the command key which is:  `ctrl-b`  This, followed by a command is what allows you to utilize tmux's power.

One useful trick is `ctrl-b ?` , which brings up the help screen.

---

# Disconnected

Let me show you one of tmux's best features, the one that makes it essential for me.  If we start a session, and run a program, normally is something happens, like your laptop going to sleep, or other bad connection, you lose your session, along with the program you were running shutting down.  With tmux, if you lose your connection, the programs you started keep running in the background, and you can re-establish your connection to the server, and pick up right where you left off.

You can disconnect purposely with `ctrl-b d` .  When you reconnect, you can start tmux with the command `tmux a`, and it will pick up your existing session.

---


So, if this hasn't convinced you, we have some ways to make the terminal that you're using richer, and more capable.



# Multiple Windows

Once you have started tmux, you can open new windows, each with its own prompt, and each can run an application of its own.  With `ctrl-b c`, you can create a new window.  `ctrl-b p` and `n` go to the previous, and next window, respectively.   `ctrl-b <#>` brings you directly to the numbered window.


---

# Split Panes

Furthermore, you can split the windows into different panes, horizontally with `ctrl-b %` and horizontally with `ctrl-b "`
There are tons of commands to resize and select between windows (show help screen for examples)

You can move between panes with `ctrl-b o` or `ctrl-b <arrow key>` and get rid of a pane with `ctrl-b x`

---

# Synchronize panes

IF you have the same command that you want to run in several panes (could be separate machines) at once, without installing more complex orchestration software, you can do the following:

`ctrl-b :` and type `setw synchonize-panes`

Now, anything you type will go into all the visible panes.

---


# Copy and Paste

Copy mode allows you to cut and paste information within tmux sessions.  ctrl-b [ starts copy mode.  Start selecting text to copy with `ctrl-space`, and end the selection with `ctrl-w`.  You can then go to another window or pane, and use `ctrl-b ]` to paste the text

This can be really useful when using a system where you don't have the ability to cut and copy text with the mouse, for example, on a tty on a Linux system, or on the console on a VMware server.  This can be a lifesaver.

There are many options for cutting and pasting text, this was just a few basics.

---

# Mouse support

If you have a system that supports it, you can enable the mouse in tmux with the following:

`ctrl-b :`  (Which enters command mode) and then `:set -g mouse on` at the prompt

This allows selection of the current pane with the mouse selecting text, and bringing up some menus with the right mouse button.

# Configuration

I found it a little funny that most of guides for tmux that I found almost immediately go into how to remap the keys that make it work.  For this presentation, I have exclusively used the default keybindings, but I can see that some customization may make things easier.

tmux has a robust set of configuration options available so that it can start up in nearly any way that you see fit, from the colors, to the taskbar to any key combination shown.


The configuration options and command mode are extremely powerful, someone even wrote a compiler for it to prove that tmux itself is Turing complete.

https://news.ycombinator.com/item?id=39713435


---

# Conclusion and questions

tmux is a very powerful and useful tool for making a command line connection as flexible and configurable as most graphical environments.  The ability to leave and reattach to a running session makes it an invaluable tool for working with remote systems.

If you want to contact me with questions or constructive criticism, please do:

You can ask questions via email at **murph@weirdness.com** 

or on The Fediverse with Mastodon at
**https://hackers.town/@murph** or 
**https://gardenstate.social/@murph**

# Thank you, and I'm open for questions.

The slides are at **https://murphnj.neocities.org**
