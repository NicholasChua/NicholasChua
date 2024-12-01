---
title: FIDO Authentication
date: 2024-12-01 21:59:50 +08:00
categories: [technical]
tags: [fido, u2f, fido2, ctap2, authentication, security]
author: NicholasChua
description: A description of how FIDO authentication works and how it can improve security
---

# FIDO Authentication

## Authentication Standards

In my previous post on [Two-Factor Authentication]({% link _posts/2024-11-17-two-factor-authentication.md %}), I discussed how I protected my accounts using two-factor authentication (2FA). In this post, I will discuss how standards such as FIDO (Fast Identity Online) can improve security and user experience.

### What is FIDO?

When one talks about FIDO, they are usually referring to the FIDO2 standard, which consists of two components: WebAuthn and CTAP2. These standards work together to provide passwordless authentication using biometrics, or authenticators like security keys.

#### WebAuthn

WebAuthn is a web standard that allows websites to interact with FIDO2 authenticators for passwordless authentication. WebAuthn is what allows the web browser to communicate with your security key or biometric sensor to verify your identity.

#### CTAP2

Client to Authenticator Protocol 2 (CTAP2) is a protocol that facilitates communication between the client (e.g., your web browser) and the authenticator (e.g., your security key). CTAP2 ensures that the authentication process is secure and that the authenticator is not susceptible to phishing attacks.

## How FIDO2 Works

When you use FIDO2 for authentication, the process typically involves the following steps:

1. **Registration**: The user registers their security key with the website, creating a new credential. The security key generates a unique public-private key pair using asymmetric cryptography. The public key is stored on the website, while the private key remains on the security key.
2. **Authentication**: When the user logs in, the website sends a challenge to the security key. The security key signs the challenge using the private key and sends the response back to the website. The website verifies the response using the public key stored during registration.

Why does this work? Because of the concept of asymmetric cryptography. The private key, as its name suggests, is kept private and never leaves the security key. The public key, on the other hand, can be shared with anyone. By verifying the response using the public key, the website can be sure that the response came from the security key and not an attacker.

## Benefits of FIDO Authentication

Notice how I never mentioned passwords in the FIDO2 authentication process? That's because FIDO2 is designed to be passwordless. Passwords are vulnerable to phishing, reuse, and brute-force attacks. By eliminating passwords and using public-private key pairs, FIDO2 provides a more secure and user-friendly authentication experience.

The lack of passwords also simplifies the login process, as there is less friction using a security key or biometric sensor than typing in a password that must be remembered. It is also well supported by major web services, making it ubiquitous and easy to use.

## FIDO U2F

How about services that do not support FIDO2? FIDO U2F (Universal 2nd Factor) was the predecessor to FIDO2 and is still widely supported by many services. U2F uses a similar process to FIDO2 but is limited to second-factor authentication. This means that you still need a password to log in, but the security key provides an additional layer of security.

FIDO U2F is also known as CTAP1.

## How FIDO U2F Works

When you use FIDO U2F for authentication, the process typically involves the following steps:

1. **Registration**: The user registers their security key with the website, creating a second factor for authentication. The security key generates a unique public-private key pair using asymmetric cryptography. The public key is stored on the website, while the private key remains on the security key.
2. **Authentication**: When the user logs in with their username and password, the website sends a challenge to the security key. The security key signs the challenge using the private key and sends the response back to the website. The website verifies the response using the public key stored during registration.

## FIDO2 vs. FIDO U2F

The main difference between FIDO2 and FIDO U2F is that FIDO2 is designed to be passwordless, while FIDO U2F is used as a second factor. FIDO2 provides a more secure and user-friendly authentication experience by eliminating passwords, while FIDO U2F adds an additional layer of security to existing password-based logins.

Realistically, you do not get to choose between using FIDO2 or FIDO U2F for a website. The website must support the standard you want to use. Both standards are considered secure and almost all major web services will support at least one of them.

## TOTP vs. FIDO U2F

In my previous post, I mostly focused on TOTP as a second factor for authentication. How does FIDO U2F compare to TOTP?

FIDO U2F is considered more secure than TOTP due to its use of public-private key pairs and the lack of shared secrets. Part of the standard also includes verifying the domain of the website, which prevents phishing attacks. TOTP, on the other hand, relies on shared secrets and is susceptible to phishing attacks if the user is tricked into entering the code on a malicious website.

FIDO U2F is also easier to use than TOTP, since it does not require the user to manually enter a code. The security key handles the authentication process, making it more user-friendly and less prone to human error. However, there are still services that do not support FIDO U2F, so TOTP remains a viable option for those cases.

TOTP does not require special hardware like FIDO U2F, making it more accessible to users who do not have a security key or biometric sensor. If FIDO U2F is not an option, TOTP is still a good choice for securing your accounts.

## Conclusion

No matter the flavor of two-factor authentication you choose, the most important thing is to enable it on all your accounts. FIDO authentication standards like FIDO2 and FIDO U2F provide a more secure and user-friendly alternative to passwords and TOTP. By using public-private key pairs and secure communication protocols, FIDO authentication can protect your accounts from phishing, reuse, and brute-force attacks.

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

## References

1. [FIDO Alliance Specifications Overview][1]

[1]: https://fidoalliance.org/specifications/

---
[Return to Top](#fido-authentication)