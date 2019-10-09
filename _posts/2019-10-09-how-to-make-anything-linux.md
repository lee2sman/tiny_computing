---
layout: post
title: "Class 7 notes - How To Make Anything With Linux"
---


### In this class: Advanced Linux commands

### Class learning groups

1. Encryption Team
2. Collaboration / Multi-Users Team
3. Automation Team
4. Gluing together software with Pipes |


### Encryption

- Public / Private Keys
- SSH Keys

Ways to connect to you Pi in the Terminal:

#### Encryption / Remote Connection with ssh

1. ```ssh pi@xxx.xx.xx.xx```
2. Enter your password

Alternative 1-liner

Authorize your laptop to log into your Pi using SSH Keys

### Permissions and Users

Files and directories (folders) are owned by a user. Every file and directory is part of a group.

All users are members of groups.
 
There are three levels of permissions for every file:
1. Read permission
2. Write permission
3. Execute permission

Changing permissions with ```chmod```. 
 
[Wikipedia info](https://en.wikipedia.org/wiki/File_system_permissions)

### Automation

#### Daemons

A [daemon](https://en.wikipedia.org/wiki/Daemon_(computing)) is a background process. 

You can set your own tasks to run using ```cron```. Cron uses ```crontab```, a type of cron table file. 

There is a mini language to create a crontab to run processes automatically.

#### Gluing together software with Piping

Piping and Redirection

```||``` = a pipe

```>>``` redirection

Commands with a single bracket overwrite the destination’s existing contents. Commands with a double bracket do NOT overwrite.

```
    > - standard output

    < - standard input

    2> - standard error
```


### Discussion on Ubiquitous Computing and What Is Code?


### Low Tech Website server

{% include image.html image="lowtech.jpg" %}

[How To Build a Low Tech Website](https://solar.lowtechmagazine.com/2018/09/how-to-build-a-lowtech-website/)

### Hundred Rabbits Ecosystem

{% include image.html image="hundred-rabbits.jpg" %}

Hundred Rabbits](https://100r.co/)

### Open Book

{% include image.html image="openbook.jpg" %}

[Anyone can build this open source, DRM-free kindle alternative](https://www.vice.com/en_us/article/7x5kpb/anyone-can-build-this-open-source-drm-free-kindle-alternative)

more technical [description](https://www.hackster.io/news/the-open-book-an-open-feather-compatible-ebook-2011bffe9ddc)

{% include image.html image="openbook2.jpg" %}

### Autonomy Cube

{% include image.html image="autonomy.jpg" %}

> The Autonomy Cube is an art project run by American artists and technologists Trevor Paglen and Jacob Appelbaum which places Tor-relays in traditional art museums.
> 
>  "What would a more civic-minded version of the Internet look like? What could the Internet look like if the Internet hadn't been turned into the greatest means of mass surveillance in the history of humanity?


### Project 2 discussion

- Break into teams.
- What software?
- What hardware? (order it!)
- what resources / questions do you have?

## Homework - Writing (and acquiring)

1. Teams: create your markdown tutorial file. Add images if helpful. Upload the markdown file and any image files.
2. Project writing:
 - what are you making?
 - what resources are you using?
 - what questions do you have?
 - order parts for next class

## Homework - Reading

- read [Our Tool Ecosystem](https://100r.co/pages/tools_ecosystem.html)
- check out Rekka's [computer](https://100r.co/pages/the_computer.html)

Read ['Collapse OS' Is an Open Source Operating System for the Post-Apocalypse](https://www.vice.com/en_us/article/ywaqbg/collapse-os-is-an-open-source-operating-system-for-the-post-apocalypse)

Read the non-solar powered site is [here](https://www.lowtechmagazine.com/2018/09/how-to-build-a-lowtech-website.html)
