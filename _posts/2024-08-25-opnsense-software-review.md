---
title: Opnsense Software Review
date: 2024-08-25 16:26:48 +08:00
categories: [technical]
tags: [opnsense, router, homelab]
author: NicholasChua
description: A review of OPNsense 24.1, an open-source firewall and routing platform based on FreeBSD
---

# Opnsense Software Review

## Disclaimer

As made clear in my [About]({% link _tabs/about.md %}) page, I do not do affiliate marketing or advertising. All products reviewed are either FOSS or purchased by me and all opinions are my own. I hate to see biased reviews as much as you do.

## Introduction

I have been using [OPNsense][1] for the past two months and I wanted to share my thoughts on the software. OPNsense is an open-source, easy-to-use firewall and routing platform based on FreeBSD. It is a fork of pfSense, which is another popular firewall and routing platform. OPNsense has a web-based interface and can be used to secure a network, manage traffic, provide VPN services, and more.

## Product Overview

OPNsense is primarily a firewall first and a router second. I use OPNsense to manage my home network, and understand how network traffic is managed. I also use it to provide VPN services to my devices when I am outside my home network, replacing my previous pivpn setup.

Migrating from my Asus router to OPNsense was relatively straightforward. I had to set up the IP range that the LAN interface would use, and a few configuration settings provided by my ISP for the WAN inteface. Once that was done, it was plug and play.

#### Plugins

OPNsense has a rich plugin ecosystem that allows you to extend the functionality of the software. I currently use the following plugins:

- os-acme-client: To manage SSL certificates for my domain
- os-crowdsec: An open-source IDS that uses crowd-sourced data to block malicious IPs
- os-ddclient: To update my dynamic DNS provider with my public IP
- os-git-backup: To backup my configuration to a git repository
- os-qemu-guest-agent: To allow the Proxmox host to communicate with the VM
- os-theme-rebellion: A dark theme for the web interface
- os-vnstat: To monitor network traffic
- os-wol: To wake up my devices via Wake on LAN remotely

#### WireGuard

It was nice to see that OPNsense has WireGuard support built-in. I used to use pivpn for my VPN needs, and configuring WireGuard in OPNsense was much more involved. However, I did see a good increase in speed and reliability as this had much more performant hardware than my Raspberry Pi 4B.

#### Crowdsec

Given that my OPNsense router is now exposed to the internet, I believe some protection is necessary. I wanted to try out Crowdsec, an open-source IDS that uses crowd-sourced data to block malicious IPs. I have not had any issues with it so far, and it has stopped a few mass scanning attempts.

## Environment

This software was tested on the following environment:
- **OS**: Proxmox VE 8.2

## Why I Use It

While I previously used an Asus router and experimented with Merlin firmware, I wanted to try out an enterprise-grade solution. I had heard good things about OPNsense, and it aligned with my goal of open-source software and self-hosting. I also wanted to learn more about networking and security, and OPNsense has been a great platform for that.

Although the learning curve was steep at first, I found that the basic configuration was still simple and straightforward. I still have a lot to learn about the more advanced features, but I am happy with the software so far.

With OPNsense active, I could now decouple my router from my wireless access point, and have more granular control over my network. For example, I could now bring down my Asus router for maintenance without affecting my wired devices. I would also not be tied to the WiFi capabilities of the router, and could upgrade my wireless access point separately. I am looking to purchase an enterprise-grade access point in the future, although that will be a topic for another post.

Running my OPNsense on Proxmox VE also allowed me to leverage the power of virtualization. I could take full advantage of backups, snapshots, and run other services on the same hardware. I also had the flexibility to move the OPNsense VM to another host if needed, although this is complicated by the fact that the WAN and LAN interfaces are passed through to the VM.

I have had to restore OPNsense from a backup due to unexpected power loss once, and the option to restore from a backup was a lifesaver. This saved me from having to reinstall and reload the configuration, and it was something I would not have had with my Asus router.

The latest upgrade to OPNsense 24.7 was also painless, and while I took precautions by backing up the VM state, I did not need to use it. The upgrade process was smooth and I did not encounter any issues. I will need more time to evaluate what has changed, though this doesn't affect my daily usage.

## Conclusion

I have been using OPNsense for the past two months and I am happy with the software. It has been stable and reliable, and I have not had any issues with it so far. I have also learned a lot about networking and security, and I am looking forward to learning more about the advanced features of the software.

I would recommend OPNsense to anyone looking for an open-source firewall and routing platform. It is easy to use, has a rich plugin ecosystem, and is actively developed. I am looking forward to using OPNsense for the foreseeable future.

## What's Next?

I will be writing a reflective piece about how one particular life decision has affected my approach to my professional life and career. Though it is not directly related to cybersecurity, it is something that has undeniably changed my perspective on how I approach technology, and I believe it is worth sharing.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [OPNsense][1]

[1]: https://opnsense.org/

---
[Return to Top](#opnsense-software-review)