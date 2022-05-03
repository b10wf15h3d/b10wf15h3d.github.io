---
title: My First Python Script
author: Sam
date: 2022-05-03 09:00:00 +0000
categories: [Courses, Python]
tags: [courses,python,udemy,scripts]     # TAG names should always be lowercase
comments: false
---
# Intro

My Python is like my Spanglish, I can just about read it and writing it is even worse!

So I've just started the below linked course on Udemy. Like the instructor I believe that the best way to learn is to be hands on

> [Learn Python & Ethical Hacking From Scratch](https://www.udemy.com/share/101WfE3@ZR9_AzsIapqOzT7ICc6Wjvml1wjv_zgJ_L1nsCO2XQB17bDdYJf1kOjebU5-Bdz3/)
{: .prompt-info }

# MAC Address Changer

The mini project the course starts off with is a MAC address changer.

Within it you learn the following

* Print statements
* Importing modules
* Using ***subprocess.call*** from module **subprocess** to initiate system commands.
* Parsing arguments.
* Defining functions.
* Creating statements.

# Code

```python
#!/usr/bin/env python

import subprocess
import optparse

def get_arguments():
    parser = optparse.OptionParser()
    parser.add_option("-i", "--interface", dest="interface", help="Interface to change its MAC address")
    parser.add_option("-m", "--mac", dest="new_mac", help="New MAC address")
    (options, arguments) = parser.parse_args()
    if not options.interface:
        parser.error("[-] Please specify an interface, use --help for more info.")
    elif not options.new_mac:
        parser.error("[-] Please specify a new MAC address, use --help for more info.")
    return options

def change_mac(interface, new_mac):
    print("[+] Changing MAC Address for " + interface + " to " + new_mac)
    subprocess.call(["ifconfig", interface, "down"])
    subprocess.call(["ifconfig", interface, "hw", "ether", new_mac])
    subprocess.call(["ifconfig", interface, "up"])

options = get_arguments()
change_mac(options.interface, options.new_mac)
```	