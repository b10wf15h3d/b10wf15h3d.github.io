---
title: Writing a Network Scanner
author: Sam
date: 2022-05-10 08:00:00 +0000
categories: [Courses, Python]
tags: [courses,python,udemy,scripts]     # TAG names should always be lowercase
comments: false
---

# Intro

This is the third Python project from my Udemy course.

> [Learn Python & Ethical Hacking From Scratch](https://www.udemy.com/share/101WfE3@ZR9_AzsIapqOzT7ICc6Wjvml1wjv_zgJ_L1nsCO2XQB17bDdYJf1kOjebU5-Bdz3/)
{: .prompt-info }

# Network Scanner

In this project I created a network scanner using ARP requests.

During this project I learnt

* Creating Dictionaries.
* Printing tabs to display info more efficiently.

## Code

```#!/usr/bin/env python

import scapy.all as scapy
import optparse

def get_arguments():
    parser = optparse.OptionParser()
    parser.add_option("-t", "--target", dest="target", help="Target IP / IP range.")
    options, arguments = parser.parse_args()
    if not options.target:
        parser.error("[-] Please specify a target, use --help for more info.")
    return options

def scan(ip):
    arp_request = scapy.ARP(pdst=ip)
    broadcast = scapy.Ether(dst="ff:ff:ff:ff:ff:ff")
    arp_request_broadcast = broadcast/arp_request
    answered_list = scapy.srp(arp_request_broadcast, timeout=1, verbose=False)[0]
    clients_list = []
    for element in answered_list:
        client_dict = {"ip": element[1].psrc, "mac": element[1].hwsrc}
        clients_list.append(client_dict)
    return clients_list

def print_result(results_list):
    print("IP\t\t\tMAC Address\n---------------------------------------")
    for client in results_list:
        print(client["ip"] + "\t\t" + client["mac"])

options = get_arguments()
scan_result = scan(options.target)
print_result(scan_result)
```

## Upgrade python2 to python3

Even though the module optparse works with python3 it has been replaced with the module argparse which operates similarly it adds more functionality.

We will update the code to reflect the changes.

**parser = optparse.OptionParser()** will become:
**parser = argparse.ArgumentParser()**

**parser.add_option** will become:
**parser.add_argument**

### Updated Code

```python
#!/usr/bin/env python

import scapy.all as scapy
import argparse

def get_arguments():
    parser = argparse.ArgumentParser()
    parser.add_argument("-t", "--target", dest="target", help="Target IP / IP range.")
    options = parser.parse_args()
    if not options.target:
        parser.error("[-] Please specify a target, use --help for more info.")
    return options

def scan(ip):
    arp_request = scapy.ARP(pdst=ip)
    broadcast = scapy.Ether(dst="ff:ff:ff:ff:ff:ff")
    arp_request_broadcast = broadcast/arp_request
    answered_list = scapy.srp(arp_request_broadcast, timeout=1, verbose=False)[0]
    clients_list = []
    for element in answered_list:
        client_dict = {"ip": element[1].psrc, "mac": element[1].hwsrc}
        clients_list.append(client_dict)
    return clients_list

def print_result(results_list):
    print("IP\t\t\tMAC Address\n---------------------------------------")
    for client in results_list:
        print(client["ip"] + "\t\t" + client["mac"])

options = get_arguments()
scan_result = scan(options.target)
print_result(scan_result)
```