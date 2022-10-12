---
title: You Thought You Came Here To Hack?
author: Sam
date: 2022-10-13 10:00:00 +0000
categories: [Work, Career]
tags: [work,career,job]     # TAG names should always be lowercase
comments: false
pin: true
---

# Intro

I wanted to write a quick blog post on how my first three months have gone after starting my role as a Penetration Tester!

I often wonder why I do not see many people write how things are going after so many posts on HTB write-ups, OSCP cheat sheets etc and now I know first hand why! The job seems to just take over and it takes a while to settle into a routine, by then the love or willingness to write evaporates. Hopefully there'll be some useful insights or takeaways from the post though it may be a be splatter gunnish in it's layout/content!

## You Thought You Came Here To Hack?

![Desktop View](/assets/img/laugh.jpeg){: w="560" h="320" }

I do not know how it works elsewhere but my company has a comprehensive onboarding process and as I've come to the end of it I understand the point of the journey.

You do not walk in and start dropping shells willy nilly and spinning up SQLMap on customer Web Apps (and yes I am having withdrawals from the RCE rush 😬)

Here we start to create a couple of images and build out a small AD network with at least a DC, Windows 10 workstation, linux web server and Windows file server. We do this so that we can perform the following tasks:

* Unauth/auth Penetration Test (mix 5x devices inc. DC)
* 1x Webapp Penetration Test
* 1x Linux Server Build Review
* 1x Windows 10 Client Build Review
* 1x iPhone Build Review
* 1x Firewall Build Review

There are many reasons behind doing this, one being that we can understand how easy it can be to mis-configure a service that can lead to the same vulnerabilities we ourselves are trying to exploit. On a personal level I feel this helps us build empathy towards our clients instead of this we beat you attitude that is so easy to slide into a Pen Testers mindset, which is one reason I took the Blue Team Level 1 course ( blog post to come in due course). We are employed to assist our clients and their internal teams, not to shame them.

The main purpose behind the exercise is to cover the main services we will be providing for our clients and build the foundational knowledge behind them without going gun ho on their networks. From there it is building up the soft skills to create the accompanying reports to a high standard without the panic of hitting a deadline.

# Technical Skills

## Build Reviews

Love those insecure service permissions for privilege escalations? How about those unquoted service paths?

If you can start off with a secure build then you limit the avenues an attacker can take and that's what we're here to check. Of course anything that goes on post build is out of our control 😬

## Firewall/Switch Build/Rule Reviews

Remember trying to pivot to the Dev or IT Admin vlan in the OSCP labs but your reverse shell kept dropping on port 4444? Well, we're the ones the sanity check those rules to ensure they're no ANY ANY rules enabled! Among other security concerns such as out of date software, weak encryption keys etc.

## Mobile Build Review

Apologies to those who wish they could use 0000 as a pin on their iPhone 😜

But hey with facial recognition and fingerprint authentication you'll rarely have to use that non-pattern 12 digit passcode anyway.

# Soft Skills

## Report Writing

Everyone's favourite part of the job! As my boss says "this is the most expensive PDF most people will ever purchase!"

We get this impression online that it's all about the shell's and the I got Domain Admin mic drop but it's not. All that it worthless unless we can document our process, compile possible mitigations and in a clear concise manner. The report is in two halves, one for management from a high level aspect with impact statements and the other for the technical teams that will be reviewing and remediating what was discovered.

And yes you should be anal about formatting, punctuation and grammar! Nobody should pay £££ for a report that the author forgets to remove a < Insert Here > or a different companies name as you've forgotten to remove it from the report template. It gives the impression that client is receiving a copy/paste report with no individual personalisation.

## Note Taking

I can not stress this enough, find a cross platform note taking solution that works for you! Like many I started off with CherryTree for my notes while studying for my OSCP however moving forward it had it's limitations. The main issue being that I work on a Windows laptop, do a lot of my testing on a Linux VM and during my personal time I use a Apple Mac but really struggled accessing my notes across all platforms seamlessly.

I am not going to re-invent the wheel and advise the available solutions, perform a quick Google search and you'll find many articles on the matter. I've settled on Notion for the time being as it's a cloud solution which I can access from a web browser when I'm unable to access it via the native app!

# Whitespace

Our role is quite intrusive on a company, so sometimes there are points where projects may get moved. This could be due to IT resources having to focus on more immediate pressing projects or the company has a product launch and does not want a distraction from their due date.

Whatever the reason may be, be prepared for whitespace! Now use that time wisely, we all know after a day of work it can be hard to focus on self development. This is where whitespace comes into its own. Update your notes, write up a new process, spend a day learning a new offensive tool. Whatever you do, do not waste that time!

I used last week to brush up on my Blue Team skills and take the Blue Team Level 1 exam from Security Blue. It was nice to start the exam as I would a working day instead of trying to take it on a Saturday thinking ah I need a lay maybe I'll push the exam until next week 😂

# TL;DR

* Don't expect to be catching shells any time soon.
* There is more paper work than you expect.
* Use non-project time for self development.
* Adopt a cross platform note taking solution.