---
title: Proxmox Helper Scripts
date: 2024-10-06 20:51:17 +08:00
categories: [review]
tags: [proxmox, scripts, homelab]
author: NicholasChua
description: Review of Proxmox helper scripts for managing Proxmox VE deployments
---

# Proxmox Helper Scripts

## Disclaimer

As made clear in my [About]({% link _tabs/about.md %}) page, I do not do affiliate marketing or advertising. All products reviewed are either FOSS or purchased by me and all opinions are my own. I hate to see biased reviews as much as you do.

## Introduction

Normally the process of setting up new applications or services involves a lot of manual steps. This can be time-consuming and error-prone. I recently came across the [Proxmox VE Helper Scripts][1] project which aims to automate some of these tasks. In this review, I will be looking at the Proxmox VE Helper Scripts and how they helped me in managing my Proxmox VE setup.

## Product Overview

The Proxmox VE Helper Scripts is a collection of scripts that help automate various tasks in Proxmox VE. The scripts are written in Bash and are designed to be easy to use. The scripts cover a wide range of tasks, from enhancing your Proxmox VE installation to creating a wide range of applications and services, self contained in LXC containers. The scripts are well-documented and come with examples to help you get started.

#### New Service Setup

The main appeal of these scripts is the ability to easily spin up new applications and services. A simple command is all it takes to create a new LXC container with the desired application or service, the catalogue of which is extensive. Options are always available to customize the installation, with basics like the resource allocation and network configuration, to more advanced things like the specific application configuration.

#### Proxmox Optimization

There are also scripts to help optimize your Proxmox VE installation. Proxmox is designed for enterprise in mind, and some default settings may not be optimal for a homelab environment. The scripts help you tweak these settings to better suit your needs. This include things like disabling the Enterprise repository, enabling the No-Subscription repository, and updating LXCs.

## Environment

This software was tested on the following environment:
- **OS**: Proxmox VE 8.2

## Why I Use It

Does anyone really want to do **MORE** work? I know I don't, and it's likely you don't either. I used one command to set up a new Pi-hole instance the same way I had set up my Pi-hole instance on my Raspberry Pi. This took a fraction of the time it would have taken me to set up manually. I also used it to set up the [Git server](https://gitea.io/) I mentioned in my [Homelab Plans 2024]({% link _posts/2024-09-22-homelab-plans-2024.md %}). The scripts are well-documented and easy to use, and I would recommend them to anyone looking to automate their Proxmox VE setup.

In addition, I had had to deal with the annoyance of the Enterprise repository nagging me about not having a subscription. The scripts allowed me to get rid of that small annoyance. I also used it for updating my LXCs, which I will continue to use in the future. I also used it to apply microcode updates to the Intel CPU that it ran on, which I think is even more important considering this box would always be running exposed to the internet by virtue of running a firewall.

## Conclusion

The Proxmox VE Helper Scripts are a great addition to any Proxmox VE setup. Chances are that you will find a script that will help you in your setup, whether it is for setting up new applications or optimizing your Proxmox VE installation. This should be a good middle ground between manual setup and full blown automation and orchestration.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [Proxmox VE Helper Scripts][1]

[1]: https://tteck.github.io/Proxmox/

---
[Return to Top](#proxmox-helper-scripts.md)