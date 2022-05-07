---
title: Improving MAC Address Changer Script
author: Sam
date: 2022-05-06 08:00:00 +0000
categories: [Courses, Python]
tags: [courses,python,udemy,scripts]     # TAG names should always be lowercase
comments: false
---

# Intro

Previously I wrote a Python script that allows you to change the MAC address of an interface on a linux machine. 

> [My First Python Script](https://passthehash.co.uk/posts/My-First-Python-Script/)
{: .prompt-info }

# Improvements

Create a function that can read and print the MAC address of the interface.

Create an IF statement that compares the previous MAC address and then compares it to the changed address to determine if it has changed.

# What Was Learnt?

* Using ***re.search*** to search for patterns and strings.

This was used to search for the MAC Address within the **ifconfig** command and passes to a variable.

To better work out what regex (regular expression) is needed use the following website

> [Regex Cheat Sheet](https://pythex.org/)
{: .prompt-info }

#  Proof of Concept

## Initial Code

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

## Revised Code

```python
#!/usr/bin/env python
import re
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

def get_current_mac(interface):
    ifconfig_result = subprocess.check_output(["ifconfig", interface])
    mac_address_search_result = re.search(r"\w\w:\w\w:\w\w:\w\w:\w\w:\w\w", str(ifconfig_result))
    if mac_address_search_result:
        return mac_address_search_result.group(0)
    else:
        print("[-] Could not read MAC address")

options = get_arguments()

current_mac = get_current_mac(options.interface)
print("current MAC = " + str(current_mac))

change_mac(options.interface, options.new_mac)

current_mac = get_current_mac(options.interface)
if current_mac == options.new_mac:
    print("[+] MAC address was successfully changed to " + current_mac)
else:
    print("[-] MAC address did not get changed.")
```
 
## Testing Code

![terminalshot](/assets/img/macaddresschange.png)