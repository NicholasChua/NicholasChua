---
title: The youread.me Tech Stack
date: 2024-05-26 23:29:35 +0800
categories: [blog, technical]
tags: [blog, jekyll, chirpy, github-pages, markdown, dns]
author: NicholasChua
description: An overview and motivation behind the tech stack used in youread.me
---

# The youread.me Tech Stack

## Problem Statement

I wanted to create a blog to document my journey, insights, and projects in the tech industry. I needed a platform that would allow me to easily write and publish content, and that would provide a clean and minimalistic design to showcase my work. I also wanted a platform that would be easy to maintain and host, and that would allow me to focus on creating content rather than managing the technical aspects of a website.

## Background

I have no formal experience in web development, although I have developed with web technologies as part of my coursework. I chose to use a static site generator in Jekyll to build this blog to ensure that I can focus on writing content rather than splitting my focus between writing and coding. I also sought a theme that was clean, minimalistic, and easy to read, which led me to choose the Chirpy theme. I decided to host my blog on Github Pages to take advantage of its free hosting service and to glean some understanding of the Continuous Integration/Continuous Deployment (CI/CD) process that Jekyll and Github Pages uses.

In addition to the tech stack, I also wanted to understand the basics of web hosting, particularly the underlying technologies of the Domain Name System (DNS) and how to configure a custom domain for my blog. I also wanted to learn how to use Markdown, a lightweight markup language, to write content for my blog.

## Solution

Technologies used in this blog include:

- [**Jekyll**][2]: A static site generator that allows me to write content in Markdown and generate a static website. As I do not require dynamic content or server-side processing, Jekyll is a good fit for my needs.
- [**Chirpy**][4]: A Jekyll theme that provides a clean, minimalistic, and easy-to-read design. It is primarily designed for technical writing, making it a good fit for a tech blog.
- [**GitHub Pages**][6]: A free hosting service that allows me to host my Jekyll-generated site. It also integrates with Github repositories, providing the benefits of version control and CI/CD.
- [**Markdown**][9]: A lightweight markup language that allows me to focus on writing content in a simple and readable format, without worrying about the coding and styling of the website.

## Learning Objectives

The key learning objectives of this project include:

- [x] Learning the syntax and structure of Markdown
- [x] Understanding the basics of Jekyll and static site generation
- [x] Understanding the features and customization options of the Chirpy theme
- [x] Learning about DNS records (e.g., A, CNAME) and configuration
- [x] Understanding the CI/CD process of Jekyll and Github Pages
- [x] Solve all errors during the process and understand the root cause of each error

## Steps Taken

##### Research

1. I watched Techno Tim's video on [Meet Jekyll - The Static Site Generator][1] to understand the basics of static site generation, Jekyll, and how it could be used to create a documentation site.
2. Before starting the project, I researched the technologies I would be using, particularly Jekyll and GitHub Pages. I read the documentation to understand how their features suited my needs.
3. I browsed through various Jekyll themes to find one that matched my requirements for a clean and minimalistic design. I chose the Chirpy theme for its readability and technical writing focus.

##### Implementation of Jekyll and Chirpy

1. Following the [Chirpy Starter Repository][5] instructions, I generated a new repository template to work with locally, and then cloned the repository to my local machine.
2. Returning to [Meet Jekyll - The Static Site Generator][1], I followed the instructions to set up a local development environment for Jekyll. This includes installing dependencies and the Jekyll bundler, then running the Jekyll server to preview the site.
3. I then wrote my first post in Markdown, following the [Markdown Guide][8] to understand the syntax and structure of Markdown. I followed the [Chirpy Theme Documentation][4] to generate the appropriate front matter, file name, and structure for the post.
4. After confirming that the post displayed correctly on the local server, I committed the changes to the repository and pushed them to the remote repository on GitHub.

##### Deployment on GitHub Pages

1. I then configured the repository settings to enable GitHub Pages, selecting the `main` branch as the source for the site. I used the default settings for the domain name (\<username>.github.io). I also enabled GitHub Actions to allow for automatic deployment of the site.
2. The site was then built and deployed by GitHub Actions, and I was able to access the site at the default domain name.

##### Custom Domain Configuration

1. I read the [Cloudflare - What is a DNS Record?][10] guide to understand the basics of DNS records and how they are used to configure custom domains.
2. I deliberated through the available domain names, deciding on one that would match what my site aimed to do. After discovering that **youread.me** was available, I purchased the domain name from [Porkbun][11], which I already had an account with.
3. I then consulted the [GitHub Pages Documentation][7] to understand how to configure a custom domain for my GitHub Pages site. I added the necessary DNS records (A and CNAME) to point the domain to the GitHub Pages site. In particular, I configured the A record to point to the GitHub Pages IP addresses (as they were the host of the site) and the CNAME record to point to my GitHub Pages domain (NicholasChua.github.io).
4. After allowing some time for the DNS records to propagate, I changed the repository settings to use the custom domain name (youread.me) instead of the default GitHub Pages domain. This is done by creating a `CNAME` file that contained the domain name. I also enforced HTTPS on the site by enabling the HTTPS option in the repository settings, as HTTPS is ubiquitous and expected in modern websites.
5. The site was then accessible at youread.me, and I was able to verify that the site was correctly configured and accessible.

## Errors Encountered

1. **DNS Propagation**: After configuring the custom domain, I encountered issues with DNS propagation. The changes did not take effect immediately, and I had to wait for the DNS records to propagate before the site was accessible at the custom domain. This was resolved by waiting for the changes to propagate, which took a few hours.
2. **CI/CD Failing On Tests**: I encountered issues with deploying the site using GitHub Actions, as the tests were failing. This was due to two issues that were my mistakes. After fixing these issues, the site could be successfully deployed using GitHub Actions.
   - I had not set the 'url' variable in the `_config.yml` file correctly and missed the protocol (`https://`youread.me).
   - I had made the same error in the `_data/authors.yml` file resulting in an unworkable link caught by the CI/CD test.

## Conclusion

With the completion of this project, I have successfully set up a blog that suited my goal of documenting my journey, insights, and projects in the tech industry. I have achieved all the [Learning Objectives](#learning-objectives) I set out to accomplish and have gained a better understanding of the technologies used in this project. This retrospective serves to document the research, implementation, and errors encountered during the project, providing a comprehensive overview of the process.

If you are interested in the code or the development process for this blog, you can find it in the [youread.me Repository][12]. Feel free to explore the code and use it as a reference for your own projects.

## What's Next?

This is my first technical post on the blog, setting the stage for future technical posts that will follow in the future. The next post will be something less technical, focusing on my journey and experiences in the tech industry. I look forward to sharing more content with you in the future. Stay tuned!

```bash
exit
```

## References

1. [Meet Jekyll - The Static Site Generator][1]
2. [Jekyll Documentation][2]
3. [Jekyll Repository on GitHub][3]
4. [Chirpy Theme Documentation][4]
5. [Chirpy GitHub Repository][5]
6. [GitHub Pages][6]
7. [GitHub Pages Documentation][7]
8. [Markdown Guide][8]
9. [RFC 7763 - The text/markdown Media Type][9]
10. [Cloudflare - What is a DNS Record?][10]
11. [Porkbun][11]
12. [youread.me Repository][12]

[1]: https://technotim.live/posts/jekyll-docs-site/
[2]: https://jekyllrb.com/
[3]: https://github.com/jekyll/jekyll
[4]: https://chirpy.cotes.info/
[5]: https://github.com/cotes2020/chirpy-starter
[6]: https://pages.github.com/
[7]: https://docs.github.com/en/pages
[8]: https://www.markdownguide.org/
[9]: https://www.rfc-editor.org/rfc/rfc7763.html
[10]: https://www.cloudflare.com/learning/dns/dns-records/
[11]: https://porkbun.com/
[12]: https://github.com/NicholasChua/NicholasChua

---

[Return to Index](#the-youreadme-tech-stack)