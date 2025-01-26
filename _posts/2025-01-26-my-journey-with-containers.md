---
title: My Journey with Containers
date: 2025-01-26 20:55:15 +0800
categories: [technical]
tags: [containers, docker, kubernetes]
author: NicholasChua
description: How I got started with containers and where I am now
---

# My Journey with Containers

## Introduction

It is hard to pinpoint when exactly I learned about containerization, but it was probably around 2015, around the time I was finishing my polytechnic studies (the equivalent of an associate degree). I was intrigued by the idea of containers, but it was only in the latter half of 2023 when I started actually using them myself. This post is a reflection on how I picked up containers, what I have learned, and where I am now.

## What Are Containers?

Imagine you have a box. This box contains everything your application needs to run: the code, the runtime, the system tools, libraries, and settings. This box is a container. Containers are a way to package software in a format that can run consistently across different environments. They are lightweight, portable, and efficient. Containers isolate applications from each other and from the underlying infrastructure, making them a popular choice for deploying and scaling applications.

## How Does This Differ from Virtual Machines?

Now, you might be wondering how containers differ from virtual machines (VMs). While VMs virtualize the hardware, containers virtualize the operating system. VMs run a full copy of an operating system, while containers share the host system's kernel. Reusing the same analogy, containers are like boxes, while VMs are like warehouses. Multiple containers can run on one VM, and with orchestration tools, you can even have multiple boxes running in multiple warehouses.

Containers don't just have to run on VMs, though. They can also run on bare-metal servers.

## Why Use Containers?

Imagine you need to use an application that uses Python 2.7, but you also need it to coexist with Python 3. You could install multiple versions of Python on your system, but then you would need to manage potential conflicts. Containers solve this problem by encapsulating the application and its dependencies. This way, you can have your Python 2.7 application running in a container while your system uses Python 3 for everything else, or you could even go ahead and containerize your other Python 3-based applications as well.

Containers also make it easier to deploy applications consistently across different environments. You can build your application in a container on your local machine, test it, and then deploy the same container to a production server. This consistency helps reduce the chances of "it works on my machine" issues.

But enough about the theory. Let's dive into my journey with containers.

## First Encounters

I first learned about the concept of containers through hearing about [Red Hat OpenShift][1]. At first, I didn't quite understand what containers were, and how they fit into the ecosystem of virtual machines and bare-metal servers. I knew that containers were a way to package applications and their dependencies, but I didn't understand the full implications of this.

## The Years in Between

Between 2015 and 2023, I continued to hear about containers, but I didn't have a reason to use them myself, given how I still didn't fully understand them. I knew that some of my colleagues were using containers to deploy applications, but I didn't have enough context or knowledge to ask them about it.

## Getting Started

Then came 2023, where I was in my third year of university. I was taking a module on Secure Software Development, and one of the core concepts covered was containerization. This was the first time I got my hands dirty with containers, and I saw firsthand how containers could be used to package applications and their dependencies in a consistent manner. We used [Docker][2] for this module, and we were tested on our ability to make use of containerization appropriately. It was enlightening to finally put theory into practice.

## Internship Experience

From April 2024, I started my internship at a local company, and proceeded to understand their tech stack. I felt I needed to get a better understanding of how my team had their containers set up so I could determine appropriate security policy and effective governance. At some point, I asked an important question: "What if I used containers myself so we could align the security team with the application team?"

This was where I really got my hands dirty with containers. I started using containers on a small scale project for automating security alert enrichment. I made sure my application could run in a containerized environment, and I learned how to deploy it to the company's chosen orchestration platform. This was a great learning experience, and it helped me understand the power of containers in a real-world scenario.

## Proxmox LXCs

At the same time, I was also experimenting with containers on my home server. I saw how [Proxmox VE][3] treated containers using Linux Containers (LXCs) as first-class citizens, and I started using them in lieu of virtual machines for certain workloads. This was a great way to experiment with containers in a more controlled environment, and it helped me understand the nuances of containerization better.

Combined with my internship experience, this allowed me to see how versatile containers could be: from running small applications to effectively replacing virtual machines for certain workloads. I also started to understand the importance of container orchestration platforms, and how they could help manage containers at scale.

## Where I Am Now

While I hesitate to consider myself a full-fledged software developer, or even a DevSecOps engineer, I feel that I have come a long way in my journey with containers. I feel like my knowledge on containers is now an instrumental part of my understanding of modern software development practices, and that helps me understand how security of containers fits into the bigger picture.

My university capstone project will definitely use containers to make sure that it can be run consistently across different environments, and I am excited to see how I can continue to develop my skills in this area through different projects in different environments.

## Conclusion

Containers are a powerful tool for packaging and deploying applications. They provide consistency, portability, and efficiency, making them a popular choice for modern software development. My journey with containers has been an effective blending of theory and practice, and I have learned a lot about how containers work in both professional and personal environments. I am excited to make use of containers in my current and future projects.

## References

1. [Red Hat OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift)
2. [Docker](https://www.docker.com/)
3. [Proxmox VE](https://www.proxmox.com/proxmox-ve)

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

---
[Return to Top](#my-journey-with-containers)