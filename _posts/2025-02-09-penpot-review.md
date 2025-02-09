---
title: A Week with Penpot
date: 2025-02-09 21:50:22 +08:00
categories: [review]
tags: [penpot, docker, design, development]
author: NicholasChua
description: A review of Penpot, an open source design and code collaboration tool
---

# A Week with Penpot

## Disclaimer

As made clear in my [About]({% link _tabs/about.md %}) page, I do not do affiliate marketing or advertising. All products reviewed are either FOSS or purchased by me and all opinions are my own. I hate to see biased reviews as much as you do.

## Introduction

I had a need to create some UI mockups to explore a project idea further, and recently came across [Penpot][1], an open-source design and code collaboration tool. Having used Figma a little in school projects, and observing that design handoff tools were being used at my previous workplace, I decided to give Penpot a try. This review will cover my experience self-hosting Penpot on Docker, and some brief thoughts on the software after using it for a week.

## Product Overview

Penpot is an open source web-based design and prototyping tool that allows designers and developers to collaborate on design, reducing the problem of design being lost in translation during handoff. It can build interactive prototypes that model rich interactions, allowing for a more accurate representation of the final product. It leverages open standards like SVG, CSS, and HTML, and offers total freedom through self-hosted deployments, allowing users and teams to truly own their work and data.

#### Design Features

Penpot expresses design as code, harmonizing the design and development processes. It builds upon open standards that developers are already familiar with, and allows for the creation of reusable design systems and components. It also supports the creation of interactive prototypes, allowing for the creation of rich interactions that can be shared with stakeholders. Built-in support is available for responsive design, allowing for creation of designs that adapt to different screen sizes, a cornerstone of modern web design.

#### Development Features

Penpot was built from day one to be developer-friendly, built upon open standards. Every design element in Penpot is a piece of code, and that means even developers may contribute to the design process through code. Penpot's open source dedication means that one can self-host Penpot, and truly own their work and data. This is a stark contrast to other design tools that may lock users into proprietary formats and services behind paywalls. Penpot's support for webhooks and APIs also allow flexibility in integrating Penpot into development workflows.

#### Collaboration Features

Penpot is designed to be a collaborative tool used by both designers and developers, aligning dev and design processes and unifying standards. This allows developers to ship faster, design scaling true to vision, and a more efficient design process. The use of code standards for design effectively means concepts such as "exporting", "generating" or "outputting" can be eliminated, as the design is already code. This allows for a more seamless handoff between design and development, reducing the risk of design being lost in translation.

The emphasis on open sourcing also lends itself well to allowing universal access, removing the worry of having to pay for additional seats. Loop in as many stakeholders as required. With Penpot, the design process is less about learning an application, and more about learning workflows and open standards.

## Environment

This software was tested on the following environment:
- **OS**: Ubuntu 24.04 LTS
- **CPU**: 2 vCPUs
- **RAM**: 4 GB
- **Storage**: 64 GB

This software requires the following dependencies:
- **Docker Engine**: Used to run Penpot in a containerized environment (alternatively, it supports Elestio and Kubernetes)

## Why I Use It

As a cybersecurity engineer, I see Penpot's true value as a tool that allows me to express my ideas in a visual manner, and to communicate how I envision a project to look like and function. Imagine you are presenting an idea to your team. Would you rather describe how features look and function, or would you rather let them explore a prototype that lets them explore exactly how the features look and function? I imagine you would agree with the latter over the former. Penpot allows me to do just that.

The use of Penpot shows that I see my ideas as products, and that means a product management workflow is the best tool to develop them to their full potential. A product management workflow is well-adopted throughout the industry, and aligning my workflow with industry standards allows me to better communicate my ideas to stakeholders.

It is often the case that many people have ideas about how a product should look and function, but they may have difficulty expressing these ideas to others, or may not be aware of tools that can help express their vision. I believe that someone who can express their ideas visually (such as through a mockup) has a competitive edge over those who cannot, and allows them to take on the role of a "product manager". 

And as a product manager, one can place the onus onto others to use the same tool to express how they envision the product, in essence challenging others to put their ideas about the project into a visual form, raising the standard of communication, and providing the basis for constructive discussion.

This means to show, rather than tell. And Penpot allows anyone to do just that.

## Conclusion

Penpot is a powerful tool that allows for the creation of interactive prototypes that model rich interactions, and allows for a more accurate representation of the final product. It harmonizes the design and development processes, and allows for the creation of reusable design systems and components. It is developer-friendly, built upon open standards, and allows for the creation of responsive design. It is a collaborative tool used by both designers and developers, aligning dev and design processes and unifying standards. It reimagines the process of design handoff. It is self-hostable, allowing users and teams to truly own their work and data. It is a tool that allows the conversation to shift from abstract ideas to concrete visual representations, challenging to show rather than tell.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [Penpot][1]
2. [Penpot Repository][2]

[1]: https://penpot.app/
[2]: https://github.com/penpot/penpot

---
[Return to Top](#a-week-with-penpot)
