---
title: Two-Factor Authentication
date: 2024-11-17 22:04:44 +08:00
categories: [review]
tags: [two-factor, 2-factor, authentication, security]
author: NicholasChua
description: A review of how I use two-factor authentication to secure my accounts
---

# Two-Factor Authentication

## Disclaimer

As made clear in my [About]({% link _tabs/about.md %}) page, I do not do affiliate marketing or advertising. All products reviewed are purchased by me and all opinions are my own. I hate to see biased reviews as much as you do.

## Introduction

Ask any security expert, and they will tell you that the best way to secure your accounts is to use two-factor authentication (2FA). In a world where security breaches are becoming more common, it is essential to take steps to protect your accounts. In this review, I will share how I use 2FA to secure my accounts and why you should too.

## What is Two-Factor Authentication?

Two-factor authentication (2FA) is a security process in which a user provides two different authentication factors to verify themselves. These factors may include something you know (like a password), something you have (like a smartphone), or something you are (like a fingerprint). By requiring two factors, 2FA adds an extra layer of security to your accounts.

Almost all major online services offer 2FA as an option to secure your accounts. This includes email services, social media platforms, and financial institutions. Chances are that your workplace also requires employees to use 2FA to access company resources. By enabling 2FA, you can protect your accounts from unauthorized access, even if your password is compromised.

## What Two-Factor Authentication Standards are Available?

There are several standards you have probably encountered when setting up 2FA on your accounts. Some of the most common ones include:

- **Biometric Authentication**: Uses your fingerprint or face to verify your identity. Most modern smartphones and laptops have biometric sensors built-in, although desktop users may need additional hardware. Usually not supported directly by web services, but can be used to unlock your device, which can then be used to access your accounts.
- **SMS-based One-Time Passwords (OTP)**: A one-time password is sent to your phone via SMS, which you enter to verify your identity. While better than not having 2FA, SMS can be intercepted by attackers using SIM swapping or social engineering attacks.
- **Email-based OTP**: Similar to SMS-based OTPs, but the OTP is sent to your email address. While more secure than SMS, email-based OTPs are still vulnerable to phishing attacks, and rely on the assumption that your email account is secure.
- **Time-based One-Time Passwords (TOTP)**: TOTP generates a one-time password that changes every 30 seconds. This password is generated offline by an app like Google Authenticator or Aegis, which you enter to verify your identity. TOTP is considered more secure than SMS or email-based OTPs. However, you should have backup codes or methods in case you lose the device you use to generate TOTP codes.
- **Push Notifications**: Instead of entering a code, you receive a push notification on your phone to approve or deny the login attempt. While convenient, push notifications require a stable internet connection due to the real-time nature of the verification process. Often found in corporate environments that use services like Okta or Microsoft Entra ID.
- **Hardware Tokens**: A physical device that uses protocols like FIDO2 to verify your identity. Hardware tokens are considered the most secure form of 2FA, as they are not susceptible to phishing attacks or malware on your device. However, they can be expensive and may not be supported by all services.

Out of these standards, I would recommend using at least TOTP wherever possible, as it requires no internet connection to generate codes. This makes it more secure than SMS or email-based OTPs, which rely on the security of your phone or email account. If you can afford it, and the service supports it, hardware tokens are the most secure form of 2FA.

## How I Use Two-Factor Authentication

I recently reviewed my online accounts and enabled 2FA for every service that I did not already have enabled. I use the [Aegis Authenticator][1] app on my smartphone to generate TOTP codes for services that support it. Being free and open-source, Aegis is a great alternative to Google Authenticator, with additional features like encrypted backups and support for multiple devices.

For services that do not support TOTP, I have no choice but to use SMS or email-based OTPs. This is unfortunately common for financial institutions and government services around the world that have not yet adopted modern 2FA standards. While not ideal, it is better than not having 2FA enabled at all.

I have also recently taken delivery of a pair of YubiKey 5 NFC hardware tokens, which I plan to use for services that support hardware tokens. While I have not yet had the opportunity to use them, I am excited to see how they improve my security posture. I will likely write a review of the YubiKey 5 NFC once I have had a chance to use them for a while.

![YubiKey 5 Pair](../assets/img/2024-11-17-two-factor-authentication/YubiKey%205%20NFC.jpg){: width="734" height="466" }
_A pair of YubiKeys_

## Why I Bought It

I bought the YubiKey 5 NFC hardware tokens in an effort to improve the security of my online accounts. While TOTP is considered secure enough for most users, hardware tokens are still the gold standard for 2FA. I wanted to see how hardware tokens would improve my security posture and whether they were worth the investment.

## Conclusion

Two-factor authentication is an essential security measure that everyone should use to protect their online accounts. By requiring two factors to verify your identity, 2FA adds an extra layer of security that can prevent unauthorized access to your accounts. I recommend using TOTP wherever possible, as it is more secure than SMS or email-based OTPs. If you can afford it, hardware tokens are the most secure form of 2FA. I hope this review has inspired you to enable 2FA on your accounts and take steps to improve your online security.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [Aegis Authenticator][1]

[1]: https://getaegis.app/

---
[Return to Top](#two-factor-authentication)