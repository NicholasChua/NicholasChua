---
title: "Pi 4B Starter Homelab Part 1/2: DNS"
date: 2024-06-27 21:15:48 +0800
categories: [technical]
tags: [raspberry pi, homelab, server, dns, pihole, unbound]
author: NicholasChua
description: "The quintessential starter homelab: Pi-hole and Unbound server"
---

# Pi 4B Starter Homelab Part 1/2: DNS

## Problem Statement

I wanted to start off my homelab with a reliable device. I wanted a more private DNS resolution service while on-the-go. I wanted something that I personally hosted, rather than relying on a third-party. I also wanted to block ads and tracking domains at the DNS level, with a friendly interface to manage blocking.

## Background

I decided to purchase the latest Raspberry Pi at the time: a Pi 4 Model B 8GB, to start off my homelab. With a homelab, I could take a more hands-on approach to understanding common technologies such as DNS. I decided to set up a DNS server on the Raspberry Pi, using Pi-hole for ad-blocking and Unbound for recursive DNS resolution. This would allow me to have more control over my DNS requests and provide a more private and secure DNS resolution service. I also wanted to use the Pi as a VPN server to securely and remotely access my home network anywhere in the world.

##### ***Who do you trust?*** 

When a DNS request is made, it is first checked against a cache to see if your Pi-Hole already knows the destination. If not, it is sent to an upstream DNS resolver to find the IP address of the domain. This DNS resolver can be your ISP, Google, Cloudflare, or any other public DNS provider. These DNS resolvers then reach out to the root DNS servers to find the authoritative DNS server for the domain. 

This process can be intercepted or logged by the DNS resolver, potentially compromising your privacy. To this end, I believe in cutting out the middleman and having my own DNS resolver that can provide recursive DNS resolution which places the logging and interception in my hands instead of a third party.

Do note that the burden of trust in this case merely shifts from the DNS resolver to the ISP, as the ISP can still see the DNS requests that the Unbound service makes. In an ideal world, the root DNS servers would make use of DNS-over-HTTPS (DoH) or DNS-over-TLS (DoT) to encrypt the DNS requests, but this is not the case at the time of writing.

More steps are being taken during the DNS resolution process, which can lead to a slight increase in latency. This can be mitigated by efficient caching in Unbound to minimize the number of queries that need to be sent to the root DNS servers.

## Solution

##### Technologies Used

- [Raspberry Pi 4 Model B][1]: A palm-sized low-power computer that can be used for various software and hardware projects and as a server
- [Pi-hole][2]: A network-wide ad blocker that acts as a DNS sinkhole, blocking ads and tracking domains at the DNS level
- [Unbound][3]: A recursive DNS resolver that provides DNS resolution for the network
- [Dynamic DNS][4]: A service that automatically updates the DNS records for a domain name when the IP address changes

## Learning Objectives

The key learning objectives of this project include:

- [x] Set up a basic Linux OS on the Raspberry Pi through CLI
- [x] Install and configure Pi-hole for ad-blocking
- [x] Install and configure Unbound for recursive DNS resolution
- [x] Learn about DNS resolution and how DNS requests are processed
- [x] Set up Dynamic DNS to automatically keep DNS records updated for on-the-go access

## Steps Taken

##### Research

1. I researched the technologies I would be using, particularly Pi-hole and Unbound. I read the documentation to understand how they worked and how they could be configured.
2. I familiarized myself with the basics of DNS resolution and how DNS requests were processed. I read about the differences between recursive and authoritative DNS servers.
3. Although I already have some experience in Linux administration, I still read up on Linux commands related to managing the software I would use.

##### Setting up Raspberry Pi OS

1. I downloaded the [Raspberry Pi Imager](https://www.raspberrypi.com/software/) tool from the Raspberry Pi website.
2. I used the Raspberry Pi Imager tool to flash the Raspberry Pi OS Lite image to my primary storage media.
   - If reusing a storage media, ensure that it is formatted before flashing the image.
   - Select *Advanced options* and enable *SSH*, allowing only public-key authentication.
     - If you do not already have a key pair, generate one using *ssh-keygen*.
     - `ssh-keygen -t ed25519 -b 256 -f <keyfile> -q -N ""` (replace `<keyfile>` with the name of your key file, no extension necessary)
   - Also set the hostname, locale, time zone and keyboard layout.
3. I connected the primary storage media to the Raspberry Pi and booted it up.
4. The Pi takes around 30 seconds to boot up. After booting up, I started an SSH session into the Pi using the following command:
   - `ssh -i <keyfile> pi@<ip-address>` (replace `<ip-address>` with the IP address of the Pi)
     - It is recommended to set a static IP address for the Pi on your router via a DHCP reservation, as this simplifies connecting to the Pi.
     - On your first connection, you will be prompted to accept the host key. Do so.
5. Run the following commands to update the Pi's package manager before installing more software:
   - `sudo apt update && sudo apt upgrade -y`

##### Setting up Pi-hole

1. With reference to the [Pi-hole Basic Install][7] guide, I installed Pi-hole on the Raspberry Pi Server by running the following command:
   - `curl -sSL https://install.pi-hole.net | bash`
2. I followed the on-screen instructions to set up Pi-hole. I was asked to set up the upstream DNS provider, blocklists, and other settings during the installation process.
   - Since I was going to use Unbound as the upstream DNS server later, I set the upstream DNS provider to `9.9.9.9` (Quad9). This is a secure and privacy-focused DNS resolver, though you can choose any provider.
3. Once the setup is complete, you can access the Pi-hole admin interface by navigating to `http://<ip-address>/admin` in a web browser. The default password is displayed at the end of the installation process.
4. For further customization, you may wish to add additional adlists to block more ads and tracking domains. I provide my list below.

    ```
    advertising.apple.com
    ck.ads.oppomobile.com
    metrika.yandex.ru
    appmetrica.yandex.ru
    log.fc.yahoo.com
    udcm.yahoo.com
    udc.yahoo.com
    widgets.pinterest.com
    log.byteoversea.com
    business-api.tiktok.com
    ```
    {: file="Additional Domains (Set Type to Exact blacklist):" }

    ```
    https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt
    https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Spam/hosts
    https://adaway.org/hosts.txt
    https://v.firebog.net/hosts/AdguardDNS.txt
    https://v.firebog.net/hosts/Easyprivacy.txt
    https://v.firebog.net/hosts/Prigent-Ads.txt
    https://osint.digitalside.it/Threat-Intel/lists/latestdomains.txt
    https://v.firebog.net/hosts/RPiList-Malware.txt
    https://v.firebog.net/hosts/RPiList-Phishing.txt
    ```
    {: file="Additional Adlists:" }

##### Setting up Unbound

1. With reference to the [Pi-hole Unbound][8] guide, I installed Unbound on the Raspberry Pi Server by running the following command:
   - `sudo apt install unbound`
2. I opened the Unbound configuration file in a text editor:
    - `sudo nano /etc/unbound/unbound.conf`
3. I pasted the configuration content listed under the section "Configure `Unbound`" in the guide, overwriting any existing content.
4. I restarted the Unbound service to apply the changes and performed a dig test to verify that Unbound was working correctly. This should return the IP address of pi-hole.net.
   - `sudo systemctl restart unbound`
   - `dig pi-hole.net @127.0.0.1 -p 5335`
5. I added the following content to `/etc/dnsmasq.d/99-edns.conf`.
   - `echo "edns-packet-max=1232" | sudo tee -a /etc/dnsmasq.d/99-edns.conf`
6. I tested DNSSEC validation by running the following commands. The first query should return a SERVFAIL response with no IP address, while the second query should return a NOERROR response with an IP address:
    - `dig fail01.dnssec.works @127.0.0.1 -p 5335`
    - `dig dnssec.works @127.0.0.1 -p 5335`
7. I set the Pi-hole to use the local Unbound resolver by navigating to the Pi-hole admin interface and removing all the upstream DNS servers and setting the custom DNS server to `127.0.0.1#5335`.
8. With the Pi-hole now using Unbound as the upstream DNS resolver, I set it as the primary DNS server for my network (including VPN clients) by configuring the DHCP settings on my router to assign the Pi-hole's IP address as the DNS server for clients.
9. I also had Dynamic DNS set up on my router to automatically update the DNS records for my domain name when the IP address changes. I used the Dynamic DNS service provided by Asus, which is integrated into my router. You can use other Dynamic DNS services like DuckDNS, No-IP, or even set up your own using a script. This will be important in the next part of this homelab series when I set up a VPN server on the Raspberry Pi.

## Conclusion

With the completion of this part of the project, I have successfully set up a recursive DNS resolver that is self-hosted and private. I have achieved all the [Learning Objectives][#learning-objectives] I set out to accomplish. With this setup, I managed to shift the trust from third-party DNS resolvers to my own server, providing a more private and secure DNS resolution service. I also got to block ads and tracking domains at the DNS level, which is a nice bonus.

This project has given me a better understanding of DNS resolution and how DNS requests are processed, as well as hands-on experience with setting up and configuring DNS servers and DDNS.

## What's Next?

In the next part of this homelab series, I will be setting up a VPN server on the Raspberry Pi to securely and remotely access my home network from anywhere in the world. I will also be setting up a file and media server on the Raspberry Pi to host and stream music and books, as I found my Pi underutilized with just the DNS and VPN services running. Stay tuned for the next part of this homelab series!

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [Raspberry Pi 4B][1]
2. [Pi-hole][2]
3. [Unbound][3]
4. [Dynamic DNS][4]
5. [Raspberry Pi OS Lite][5]
6. [Raspberry Pi Imager][6]
7. [Pi-hole Basic Install][7]
8. [Pi-hole Unbound][8]

[1]: https://www.raspberrypi.com/products/raspberry-pi-4-model-b/
[2]: https://pi-hole.net/
[3]: https://nlnetlabs.nl/projects/unbound/about/
[4]: https://en.wikipedia.org/wiki/Dynamic_DNS
[5]: https://www.raspberrypi.org/software/operating-systems/
[6]: https://www.raspberrypi.com/software/
[7]: https://docs.pi-hole.net/main/basic-install/
[8]: https://docs.pi-hole.net/guides/dns/unbound/

---
[Return to Top](#pi-4b-starter-homelab-part-12-dns)