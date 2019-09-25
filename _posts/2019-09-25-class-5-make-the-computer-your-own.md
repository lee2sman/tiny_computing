---
layout: post
title: "Class 5 notes - Make It Your Own"
---


In this class


### Stand-up check-in

On a PC? [Install and use the Linux bash shell](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) with Linux Subsystem for Windows.

### Customizing your computer in Linux

#### your prompt

The prompt is the location on the command line where you type input commands to your computer. The Bash prompt default is where you type Bash commands. Bash is the name of the language as well as the text interface. The prompt usually contains the name of the environment running and a $, something like ```bash-3.2 $ ```. You can (and probably should) customize your prompt, adding color and useful information such as what directory you are in, the time, whether your project is up to date on GitHub, etc.

There are [websites](http://ezprompt.net/) to generate your prompt. Click some options and it produces code for you to put into your ```.bashrc```

#### Bashrc

The bashrc is the Bash Runtime Compiler. Any Bash code saved in this file will be run when you start up Bash in the Terminal.

We can put code in here to customize the prompt, to be run when we open Bash.

In your home directory (get there by typing ```cd``` alone), you can ```ls -a``` to see if you already have a hidden ```.bashrc``` file. If not, use ```nano``` or a text editor to create and save a file with the name ```.bashrc```. The period means the file will be normally hidden.

You can save the code for your custom Bash prompt inside the variable P1. In Bash, you can **get** the contents of a variable by placing a ```$``` in front of it. To make a custom Bash prompt, put a line such as the following saved in your bashrc file.

```
export PS1="\u@\h\w $ "
```

This will put the username, hostname then current folder in the Bash prompt.

Check out others' example [bashrc files](https://github.com/search?q=bashrc&type=Everything&repo=&langOverride=&start_value=1).

#### apt-get 'ing software

We covered websites like the [Snap Store](https://snapcraft.io/store) to use a browser to find and download Linux software. Let's also review how to use other package managers.

**apt-get**

```
sudo apt-get install essentialSoftwareIWant
```

This will install the software ```essentialSoftwareIWant``` as well as all of its *dependencies*. Dependencies are other pieces of software needed to run the software you want. For example, if you are downloading video editing software, you will also need the audio and video codecs. You might already have this on your computer. If not, apt-get will search and download those for you as well and tell you it is doing that.

You can also ```apt-get search whatImLookingFor``` before choosing to install if you want to search first.

#### choosing/customizing your shell

There are other Shells beside the basic (and boring) but ubiquitous Bash Shell. For example, Zsh (aka z-shell) provides lots of customizability. And Fish (aka Fish-shell) provides lots of good basic defaults, colors and auto-completion.

Let's install Z-shell.

```sudo apt-get install zsh```

To try it out, after installing type ```zsh``` to jump into it. You can exit out back to Bash by closing the Terminal or typing ```exit```.
To permanently change to zsh instead of bash, type ```chsh -s $(which zsh)``` which changes the default Shell from Bash to Zsh.

#### Aliases

You can make your own custom commands for actions that you take a lot.

For example, if you installed ```mplayer``` and want to play a radio station, you could write an alias to play a particular radio station.

[common Bash aliases](https://www.cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix.html)
