---
title: Nmap in the movies !
date: 2023-04-12
categories: [networking, network security]
tags: [networking, nmap, hacking]
author: verlaine
---

## **what’s the difference between movies and our daily life as engineers ?**

### The Tale:

They say movies are not real life, it's just a way to create more illusions in our minds!

the answer is just relative, movies are great a way to inspire us to learn and innovate for the present and future.

with sci-fi what we saw 20 or 30 years later,is now a part of our daily life, the touch screen, the metaverse,robots working in some plants around the world, the artificial intelligence domination and soon we may attain singularity proven by brilliant minds like Raymond Kurzweil.

Mr robot, Chloe O'Brien, how many people inspired us to become computer nerds through the movies?

Nmap is seen in different successful movies like **Ocean 8** , **the matrix reloaded** , **die-hard 4** and there's a great tribe of curious learners after watching some footage!

are you one of them?

### The Path:

Let's discover together!

**What is Nmap?**

Nmap or Network Mapper is a free and open-source **utility** used by network engineers for network discovery and audits.

a network admin can use the utility to scan active network devices the service they are running,and open ports.

in pen testing white or black hat hackers can use Nmap to scan and discover vulnerabilities on target computers,it's written in the Lua language and currently it's still the favorite daily companion for pen testers and network admins.

3 primary functionalities are given by Nmap :

- _shows detailed information on every active network and each IP address_
- _helps to identify security vulnerabilities_
- _shows a list of active hosts and identifies the operating system of every connected device_

**Nmap basics**

the best way to know the tool is through daily practice let's discover basic commands to train your brain and fingers as a future pen tester.

in our short demo, we use Nmap on Ubuntu our favorite Linux distribution, you can also use it on Windows but Linux remains the best kernel to test advanced things in security.

if Nmap is already installed on your Ubuntu you can skip the installation, here we show the installation if it's not done yet on your computer.

![nmap1](/assets/img/favicons/nmap1.jpg)

**sudo apt install nmap** : to install you need a higher privilege as root "sudo"

once the utility is installed run "nmap" in the shell, the version will be displayed, and additional arguments to add to the utility.

![nmap2](/assets/img/favicons/nmap2.jpg)

**nmap** : displays the version, and options to make the most of the utility.

let's scan a host with an IP address of **172.20.120.174** to see if it's active

![nmap3](/assets/img/favicons/nmap3.jpg)

the result shows an active host.

let's scan [www.nasa.gov](http://www.nasa.gov/) to get some details about the scan

![nmap4](/assets/img/favicons/nmap4.jpg)

**nmap –vv** : gives more details about the scan,the output shows the time a ping was initiated, the website, number of ports scan.

![nmap5](/assets/img/favicons/nmap5.jpg)

**nmap -A** : to enable operating system detection, version detection and script scanning.

in the output, we can see **Android** running.

Now you have some basic knowledge of nmap, open your shell and go further by testing more commands

### The Challenge:

Open your shell and run these 5 commands to discover **nmap** 

- **sudo apt install nmap** to install the utility in your shell 
- **nmap** by targeting an IP address in your local network 
- **nmap -vv** followed by a website of your choice to get some details 
- **nmap -A** to detect the operating system of a target machine 
- **nmap -Pn --script vuln** followed by the ip address of your target PC to discover vulnerabilities 


To learn more: - [Cisco Learning Network](https://learningnetwork.cisco.com/s/blogs/a0D6e00000sRFJIEA4/my-first-common-vulnerability-exposure-cve-a-devnet-journey-part-1)

- [Nmap: the Network Mapper - Free Security Scanner](https://nmap.org/)
- [Movies Featuring the Nmap Security Scanner](https://nmap.org/movies/)

Happy learning and stay curious !
