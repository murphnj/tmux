%title: A Brief introduction to tmux
%author: murph	
%date: 2024-02-26

-> A Brief introduction to tmux <-

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

`yum install tmux or dnf install tmux`

Debian/Ubuntu and similar:

`apt install tmux`

These commands also tend to work on WSL, if that's where you're trying this from.

On the Mac, either Homebrew or MacPorts are the way to install.

---

# Getting started with tmux.

To start tmux, simply type tmux at a command prompt.

You'll see a command prompt, just like before, but at the bottom of the window, you'll notice that there's a status bar with the current command, the hostname, and the time and date.

This is the basic screen, to activate tmux, you need the command key which is:  `ctrl-b`  This, followed by a command is what allows you to utilize tmux's power.

One useful trick is `ctrl-b ?` , which brings up the help screen.

---

# Disconnected

Let me show you one of tmux's best features, the one that makes it essential for me.  If we start a session, and run a program, normally is something happens, like your laptop going to sleep, or other bad connection, you lose your session, along with the program you were running shutting down.  With tmux, if you lose your connection, the programs you started keep running in the background, and you can re-establish your connection to the server, and pick up right where you left off.

You can disconnect purposely with `ctrl-b d` .  When you reconnect, you can start tmux with the command tmux a, and it will pick up your exisiting session.

---


So, if this hasn't convinced you, we have some ways to make the terminal that you're using richer, and more capable.

---

# Multiple Windows

Once you have started tmux, you can open new windows, each with its own prompt, and each can run an application of its own.  With `ctrl-b c`, you can create a new window.  `ctrl-b p` and `n` go to the previous, and next window, respectively.   `ctrl-b <#>` brings you directly to the numbered window.


---

# Split Panes

Furthermore, you can split the windows into different panes, horizontally with `ctrl-b %` and horizontally with
`ctrl-b`
There are tons of commands to resize and select between windows (show help screen for examples)




---


# Copy and Paste

Copy mode allows you to cut and paste information within tmux sessions.  `Ctrl-b [` starts copy mode, `ctrl-b ]` pastes.  Start selecting text to copy with `ctrl-space`, and end the selection with `ctrl-w`.  You can then go to another window or pane, and use `ctrl-b ]` to paste the text

This can be really useful when using a system where you don't have the ability to cut and copy text with the mouse, for example, on a tty on a Linux system, or on the console on a VMware server.  This can be a lifesaver.

---



