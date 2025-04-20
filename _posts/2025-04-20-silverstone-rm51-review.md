---
title: Silverstone RM51 Review
date: 2025-04-20 22:19:59
categories: [review]
tags: [homelab, server, case]
author: NicholasChua
description: A short review of the Silverstone RM51 case, covering my experience with it.
---

# Silverstone RM51 Review

## Disclaimer

As made clear in my [About]({% link _tabs/about.md %}) page, I do not do affiliate marketing or advertising. All products reviewed are purchased by me and all opinions are my own. I hate to see biased reviews as much as you do.

## Introduction

I recently purchased the [Silverstone RM51][1] case for a future build that I am planning. I was looking for a case that would be able to accomodate the tall CPU cooler (Noctua NH-D15) that I was planning to reuse. I also wanted something unique, being rackmountable and horizontally oriented so that GPU sag (especially with the increasingly large and heavy GPUs in the market) would not be an issue. I also wanted maximum compatibility with different standards, such as PSU and motherboard form factors.

## Product Overview

The Silverstone RM51 is a 5U rackmount case that is horizontally oriented. It is designed to be used in a 19" rack, but can also be used as a desktop case. The case is extremely well built, with a full stainless steel construction and utilitarian design that eschews aesthetic choices like glass side panels and RGB lighting, instead being completely sealed except for the front and back perforated panels. The case is also heavy, weighing in at 10.5 kg (23.1 lbs) without any components installed.

#### Broad Compatibility

The 5U form factor allows the RM51 to support practically all form factors of components, such as:

- Motherboards
  - ATX
  - Micro-ATX
  - Mini-ITX
  - E-ATX
  - SSI-CEB
  - SSI-EEB
- Power Supplies
  - ATX (up to 190mm)
  - SFX
  - SFX-L
- Storage
  - 3.5" HDDs (up to 4)
  - 2.5" SSDs (up to 4)
  - M.2 NVMe SSDs
- Fans
  - 180mm (up to 2x, intake, provided)
  - 360mm radiator (up to 1x, intake, optional, replaces 180mm fans)
  - 140mm (up to 1x, exhaust, optional)
  - 120mm (up to 1x, exhaust, optional)
  - 80mm (up to 2x, exhaust, optional)
- GPU
  - 455mm length, 198mm width
- CPU Cooler
  - 192mm height

Standoffs are provided for all supported motherboard form factors, and there are two mounting points for the PSU, allowing one to use both an ATX PSU and an SFX PSU at the same time (or two 3.5" drives in place of the SFX PSU). The case also has a GPU support bracket that spans the entire length of the case, helping to hold the GPU in place and prevent sagging. The GPU support bracket has adjustable plastic supports that can be moved to accomodate different GPU PCIe slot heights, and also serves as mounting points for the storage drives.

#### Chassis Intrusion Switch

You have likely never heard of this feature before, but the RM51 has a chassis intrusion switch that can be programmed to trigger alarms when the case is opened. This is a feature that is usually found in enterprise-grade servers, and is a nice touch for a consumer-grade case. The switch is located on the back of the case, and can be connected to motherboards that support it.

#### Rack Mounting

The case is designed to be mounted in a 19" rack, and a set of tool-less rack rails, the [Silverstone RMS05-22][2], may be purchased separately. While I do not like the idea of having to purchase the rails separately, I understand that these rails are not needed for everyone, and they are a proprietary design that would not be compatible with other cases. If no rails are purchased, the case includes plastic feet that can be installed to allow the case to stand up vertically.

The case is also designed for a 5 rack unit (5U) height, which is going to occupy a lot of space in a rack. This is a potential downside for some users, as it may be difficult to find the rack space for it. However, I believe that the 5U height is perfect for ensuring compatibility with the tallest CPU coolers, and especially with the Noctua NH-D15, which is 165mm tall, and possibly even taller if one needs to move the second fan upwards to accommodate RAM clearance. An additional point to note is that Nvidia's latest GPUs, such as the RTX 4000 and 5000 series, feature a 12VHPWR connector, which requires some allowance for cable bend radius, and an insufficient height may force the cable to bend at an angle that is not recommended. The 5U height of the RM51 allows for a more gentle bend radius, which is a nice touch.

For now, I am waiting for the rails and rack to arrive. I will have a follow-up post once I have the opportunity to install the case in a rack.

## Specifications

| ‎          | Name                                        |
| ---------- | ------------------------------------------- |
| Color      | Black / Silver                              |
| Weight     | 10.5 kg (23.1 lbs)                          |
| Dimensions | 440 mm Width x 220 mm Height x 485 mm Depth |
| MSRP       | ~$420 USD + ~$89 USD rails                  |

## Why I Bought It

I had the idea to build a new PC that would function as both a gaming PC and a server, and to have it rack mounted. To ensure maximum compatibility with the components I had in mind, the Silverstone RM51 was the cheapest solution from a reputable brand that I could find. I also wanted to try out a rackmount case, as it has a different aesthetic and use case compared to the traditional "fish tank" cases commonly seen in the market. With that in mind, I decided to purchase the RM51. It won't win any awards for aesthetics, but I believe investing in a rackmount case now is an investment for the future, where I plan to expand my homelab with a dedicated server rack and accomodate more rackmountable equipment.

## Conclusion

The Silverstone RM51 is a well-built, utilitarian case that is perfect for those looking for a rackmountable solution. It has broad compatibility with different components, and the chassis intrusion switch is a nice touch. The case is also heavy and sturdy, which is a plus for those looking for a durable solution. The only downside is the price, which may be a bit steep for some users. However, I believe that the RM51 is worth the investment for those looking for a high-quality rackmount case. I would recommend it to anyone who is looking for an entry into the rackmount case market with regular PC components.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [Silverstone RM51][1]
2. [Silverstone RMS05-22][2]

[1]: https://www.silverstonetek.com/en/product/info/server-nas/RM51/
[2]: https://www.silverstonetek.com/en/product/info/server-nas/RMS05-22/

---
[Return to Top](#silverstone-rm51-review)
