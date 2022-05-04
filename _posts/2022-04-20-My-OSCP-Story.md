---
title: My OSCP Story
author: Sam
date: 2022-05-04 09:00:00 +0000
categories: [Courses, OSCP]
tags: [oscp,courses,review]     # TAG names should always be lowercase
comments: false
pin: true
---

# Intro

You haven't truly passed your OSCP certification until you've written even a brief blog post about it.

![Desktop View](/assets/img/thisistheway.jpeg)

# My Background

I have worked in IT support roles for the past 16/17 years from 1st line support to Service Desk manager. Being a "people's person" I got pigeonholed into customer facing roles and was unable to break into more technical roles. Unfortunately I became a victim of my own success and having transitioned into contract work 10 years ago it was even harder to escape.

# Studying

I have been studying for the OSCP exam on and off for about a 18 months. The biggest break being about 4/5 months. 

> There is no fixed `timeline` to when you are ready for the exam. I see many posts asking how long you need and the only appropriate response is `how long is a piece of string?` Only you'll know when the time is right.
{: .prompt-info }

## PWK Labs

The PWK labs were essential to my initial learning. I know there is a consensus out there that they are "easy" and pointless in undertaking but I passed the AD section of the exam due to me returning to the labs a month beforehand. Re-hashing a certain attack vector is the only reason I was able to get a foothold on the AD chain.

I completed 58/75 machines in the labs and unlocked all the VLANs.

## TJ Null

If you've never heard of TJ Null go search for him now!

TJ Null has compiled a list of OSCP like machines external to the PWK labs covering HackTheBox, OffSec's Proving ground and Vulnhub

> [TJ Nulls OSCP List](https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/edit#gid=1839402159)
{: .prompt-info }

## Burnout

Who doesn't experience burnout?! Don't be afraid to admit it to yourself or to others. Sometimes you need to push the chair away from your desk and step away. Maybe for an hour, day, week or even a month! It is best to address the signs early on before it gets so intense you wave the white flag and give up for good.

It's important to surround yourself with those who support what you're trying to achieve. Taking this path awakened me to those who really support me and those who are just fair weathered friends. Treasure the people that relish in the success in others.

# The Exam

Having failed the exam back in Oct '21 I entered this one very nonchalant, what will be will be! With the addition of Active Directory I really had no idea what to expect, on one hand reading Reddit posts I knew if I had covered the OSCP pdf I would be fine however on the other hand a lengthy post with dozens of disgruntled students made me weary.

Oh btw I passed with 80/100 points!

## Advice

The following tips are what I believe are important whilst taking the exam.

> Pre-schedule your `breaks` before taking the exam but remember it's fluid. If you're on a roll keep going, if you're at the point of banging your head take your break early.
{: .prompt-tip }

> `Sleep` is important, treat the exam like a working day. Even if you get 4 hours sleep it's better than "powering" through.
{: .prompt-tip }

> Prep `meals/snacks` in advance, don't waste precious time cooking. Nothing stodgy (carb heavy), don't want to fall asleep at your workstation. 
{: .prompt-tip }

## Active Directory

If you've read the course PDF then yes you have the necessary knowledge to pass the Active Directory section. I can not go into detail because of the NDA so I'll keep this section light.

> When I state the course PDF I mean in it's entirety, not just the section on Active Directory! 
{: .prompt-warning }

The Reddit posts had me very nervous when I realised that I had the AD chain that individuals had caused some noise. After a couple of hours I moved onto the BOF exploit as to not burn out my motivation before returning. Taking that step back made me realise I was on the right path before the Reddit posts came to the forefront of my mind!

## Stand Alone Machines

I stand by my view that along with technical knowledge blah blah, you will need luck on your side in passing the exam.

You could of rooted 100 HTB machines, 50 PG machines and all the PWK labs but it doesn't mean you can root what will be presented in the exam. I am not stating they are harder or easier however if the route is something you've not come across or understand you won't be able to root! 

e.g. my brother has his OSCP and 4/5 years as a Pen Tester and now Red Teamer, sometimes I can point out a vuln before he does, not because I'm better but from experience of exploiting something similar!

So if luck truly isn't on your side you may end up with 3 standalones that you will not get a shell on!

**TL;DR** I got root on 2/3 machines before running out of time. Luck is a factor in exams!

# What is Next?

I know it's a cliche but ideally I want to get into penetration testing / leaning towards red teaming in the long run. After 17 odd years supporting and resolving issues I have a strong drive to "swap teams" and be on the offensive side!

## Courses

### Certified Red Team Operator (CRTO)

If you've used the Windows privilege escalation powershell script Sherlock then you've heard of Rasta Mouse! 

Mr Mouse has put together an online course that teaches the basic principles, tools and techniques, that are synonymous with red teaming.

Access to your own lab environment you'll gain hands on experience of using Cobalt Strike to pivot your way through an Active Directory Forest.

Google reviews, check out some YouTube vids, I can't do the course justice! Better value for money than the Red Labs at Pentestacademy with a great Discord community.

> [Certified Red Team Operator](https://courses.zeropointsecurity.co.uk/courses/red-team-ops)
{: .prompt-info }

### Learn Python & Ethical Hacking From Scratch

I had never seen a python script before this course so although I can "read" python now it is on very limited understanding. I am undertaking a hands on Udemy course to better understand it and be able to write my own scripts.

> [Learn Python & Ethical Hacking From Scratch](https://www.udemy.com/share/101WfE3@ZR9_AzsIapqOzT7ICc6Wjvml1wjv_zgJ_L1nsCO2XQB17bDdYJf1kOjebU5-Bdz3/)
{: .prompt-info }

### CREST CPSA/CRT

A large number of companies favour those who hold CREST CRT. For those who hold the OSCP there is a certification equivalency recognition programme that allows you to take the CPSA and convert it to the CRT.

> [CREST CRT Equivalency Recognition Programme](https://www.crest-approved.org/certification-careers/certification-equivalency-recognition-programmes/)
{: .prompt-info }

The CPSA is a theory based exam with material that will have been covered in the OSCP but in greater detail. For e.g. what service is generally hosted on port 25.

# Is OSCP For Me?

Standard question people have asked me or others on forums. The truth is it depends what you're trying to achieve.

The certification is a door opener yes but there is so much more to learn before an employer will take you on. For example I lack scripting skills, which is not a major red flag but it certainly edges out other candidates by being fluent in at least one.

I would recommend checking out the following resources and the reviews online. Great for a small initial investment, great return on knowledge and if you feel this is the path for you then go for the OSCP. 

[https://tryhackme.com/](https://tryhackme.com/)

[https://www.hackthebox.com/](https://www.hackthebox.com/)

[The Cyber Mentor](https://academy.tcm-sec.com/)

[https://elearnsecurity.com/](https://elearnsecurity.com/)

[https://www.virtualhackinglabs.com/](https://www.virtualhackinglabs.com/)

# TL;DR F.A.Qs

_**What is your background?**_

IT support from resetting passwords to organising migrations of Windows 7 to 10.

_**Why did you want to gain the OSCP certification?**_

I wanted a experience a new challenge in my career and break out of user support roles.

_**How long did you study for?**_

On/off for about 18 months.

**_Did you experience burnout?_**

Who doesn't?! Don't be afraid to admit it to yourself or to others. Step away, have a coffee, go for dinner with friends or whatever it is you do to reset your mind!

**_What were your key resources external to the PWK material?_**

TJ Nulls OSCP like machines

[TJ Nulls OSCP List](https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/edit#gid=1839402159)

Hacktricks bible of info, cheatsheets etc

[HackTricks](https://book.hacktricks.xyz/)

**_How many times did you take the exam?_**

Twice!

1st attempt (old format) 60/100 points.

2nd attempt 80/100 points.

**_What is your ideal 1st job?_**

Penetration tester

_**What courses are undertaking next?**_

Certified Red Team Operator (CRTO)

[Certified Red Team Operator](https://courses.zeropointsecurity.co.uk/courses/red-team-ops)

CREST CPSA/CRT

[CREST CRT Equivalency Recognition Programme](https://www.crest-approved.org/certification-careers/certification-equivalency-recognition-programmes/)

Learn Python & Ethical Hacking From Scratch

[Learn Python & Ethical Hacking From Scratch](https://www.udemy.com/share/101WfE3@ZR9_AzsIapqOzT7ICc6Wjvml1wjv_zgJ_L1nsCO2XQB17bDdYJf1kOjebU5-Bdz3/)
