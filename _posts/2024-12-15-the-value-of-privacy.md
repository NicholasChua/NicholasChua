---
title: The Value of Privacy
date: 2024-12-15 22:39:20 +08:00
categories: [reflection]
tags: [security, privacy, singapore]
author: NicholasChua
description: Thoughts on the value of privacy given a recent incident in Singapore
---

# The Value of Privacy

## Introduction

We often think about security as the most important factor in our work and personal lives, though we forget sometimes that security is only the tool used to protect our privacy. Privacy is the right to keep any knowledge to ourselves, and choose how and whom we wish to share it with.

## Explicit Trust

Often, though, we have choices in who we share our information with. We can choose not to do business with those that we don't trust, or have proven to be untrustworthy. We can also intentionally choose to limit the types of information we share, and even revoke that information if we feel it is being misused.

## Implicit Trust

Sometimes, though, we don't have a choice in who we share our information with (e.g., government agencies, employers, etc.). In these cases, we implicitly trust that they will not misuse the information we provide them, and the countries we live in have laws to protect us from blatant misuse of such information. However, it isn't always safe to assume that our information is safe with these entities.

## Case Study: Singapore's NRIC Number Debacle

For those outside Singapore, the NRIC number is a unique identifier assigned to each Singaporean citizen and permanent resident. It is used for all government transactions, and is often used by private entities as a form of identification.

On 9 December 2024, the Accounting and Corporate Regulatory Authority (ACRA) launched a new digital service portal for business registration, filing, and information, called Bizfile. However, it was soon discovered that one could search for names and NRIC numbers of private individuals on the portal without logging in, which raised much alarm over the privacy of Singaporeans' personal information. This was especially concerning, given how the Personal Data Protection Commission (PDPC) had, in 2018, [issued guidelines][2] to stop the indiscriminate collection of NRIC numbers by private entities. 

For context, the PDPC's Personal Data Protection Act (PDPA) requires organizations to obtain consent before collecting, using, or disclosing personal data, and to only collect personal data that is necessary for the purpose for which it is collected. However, the PDPA does not apply to public agencies, which are exempted from the requirement to obtain consent before collecting personal data, and are only required to comply with the PDPA's data protection provisions. This means that ACRA's Bizfile portal was not in violation of the PDPA, as it is a public agency.

Given how the NRIC number's generation process has been reverse-engineered, it is possible for anyone to generate a large list of NRIC numbers to run through the Bizfile portal en masse, retrieving the full names of the individuals associated with those numbers. I have no doubt that this has already been done in the 5 days this has been available, and the data is probably in the hands of malicious actors by now.

On 14 December 2024, the PDPC [announced][2] that it would be updating its guidelines to align with the new policy intent of the government, which is to stop masking NRIC numbers, after recognizing the privacy concerns raised by the public. They had also removed the ability to search for people in the Bizfile portal as a stopgap measure.

## Mismatch of Expectations

The NRIC number debacle highlights a mismatch of expectations between the government and the public. The PDPC's stance on the matter, at least up until 14 December 2024, was that the NRIC number was considered private and confidential data, and should not be disclosed without the individual's consent. This lead private organizations such as banks and telcos to treat the NRIC number as a primary identifier for their customers, and to ask for it as a form of verification. However, with the announcement of the new policy intent, it seems that private organizations will be left 'holding the bag', as they scramble to update their processes to identify legitimate customers without the NRIC number. Similarly, the government's reliance on using the NRIC number as a primary identifier for its own online services (e.g., SingPass) will also need to be re-evaluated.

## Chaos for Now

We were all caught off-guard by this sudden change in direction, and it is a stark reminder that our privacy is not guaranteed, even by the government. Until the processes and systems have caught up with the new policy intent, we will need to be especially vigilant about scams and phishing attempts that may try to take advantage of the confusion. This is especially concerning, given how it is possible that not everyone, especially the elderly, may be aware of the announcement, and may fall victim to someone reciting their full name and NRIC number to them pretending to be an authority figure.

It will also be interesting to see how the situation plays out from tomorrow onwards, the first working day after the announcement. Will bad things happen? I hope not, but I am not optimistic.

## Long-Term Implications

One word. Distrust.

I don't believe many people are going to be happy with the government about this sudden change, likening it to the act of moving the goalposts, or colloquially, "flipping prata". Given how the government has beaten the drum of promoting awareness of scams and phishing attempts, it is ironic that they have now created the perfect environment for such activities to thrive. It is also a stark reminder that, even if we are not responsible for the misuse of our information, we are still responsible for the consequences of that misuse.

## What Do I Think?

Having verified that I could search for people's personal information myself, I think this is a serious breach of privacy. The announcement of the new policy intent does make clear that the government believes that the NRIC number would likely not be safe to keep private in the future, although I think it is negligent of them to have allowed such exposure to happen in the first place. As a cybersecurity professional, I can only hope that the government builds secure frameworks such as public-private keypairs or even some sort of Zero-Trust architecture, to verify the identity of individuals.

## Conclusion

Given how Singapore has handled the recent NRIC number debacle, it is clear that blind trust in authorities is not enough to protect our privacy. I believe that we should keep in mind that privacy is our responsibility to deal with, even if breaches are not our fault. We should hope that governments and organizations around the world will see this as a cautionary tale, and adopt sound security and privacy practices to protect the data they hold.

## References

1. [PDPC Guides on Data Sharing][1]
2. [PDPC guidelines to be updated to 'align with new policy intent'][2]

[1]: https://www.pdpc.gov.sg/-/media/Files/PDPC/PDF-Files/Other-Guides/Guide-to-Data-Sharing-revised-26-Feb-2018.pdf)
[2]: https://www.channelnewsasia.com/singapore/pdpc-nric-numbers-personal-data-protection-4807096

```bash
nicholaschua@youread.me:~$ exit
logout
```
{: .nolineno }
{: file="nicholaschua@youread.me: ~" }

---
[Return to Top](#the-value-of-privacy)