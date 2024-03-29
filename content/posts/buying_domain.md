---
title: "Buying your first domain"
date: 2021-11-01T12:23:54-04:00
draft: false
tag: ["DNS, startup, domain, basics, week0"]
categories: ["Secure Startup"]

---

# TLDR
Buy a domain on a trusted top-level domain, using an email with multi-factor authentication (MFA). On the registrar and domain, enable MFA, turn on transfer lock and domain privacy on the domain until you get corporate mailing and email addresses. 

# Buying your first domain

As a brand new company, you're going to need a domain name rapidly. This domain name will quickly be used for your website,  email, and generic "proof of existence".

It'll become the root for the identity related to your company. The faster you create it, the sooner it will stop looking suspicious, as many systems treat [newly registered domains](https://unit42.paloaltonetworks.com/newly-registered-domains-malicious-abuse-by-bad-actors/) (NRDs) as suspicious.

Why would you need a website rapidly, if you have nothing ready to sell yet? Many services require being linked to a domain. For example, to get onboarded to Apple's Device Enrolment Program, which lets you drop-ship laptops to employees directly from Apple but ready to go with your configuration, you need to have an HTTPS website. To get a certificate, you must be able to prove you control a domain. Therefore, there's no time to waste, you should get your domain as fast as possible when starting a new company.

## Picking a domain name

1. Ensure your company name and the domain you want to buy are available and legally appropriate. I am not a lawyer and don't pretend to be one on the Internet, but I recommend using real ones. You probably also want input from a marketing firm that'll help you pick a name while avoiding mistakes that are only [hilarious](https://drivetribe.com/p/15-of-the-worst-car-names-ever-Uuj3c_VxR7aCu-WkDCeahg?iid=aY9QSRXETP-k1K0_G7G05w) when they happen to others.
2. Avoid "weird" [top-level domains](https://www.zdnet.com/article/new-top-level-domains-a-money-grab-and-a-mistake-paul-vixie/). You do not want your company to depend on a small country's control of a TLD, and you definitely don't want it to use a domain name known for being used for [a lot of malicious activity](https://www.farsightsecurity.com/assets/media/download/VB2018-study.pdf). Pick an old favorite such as .com, even if it means not getting the perfect short name (you can get the weird TLD ones as well, but make your primary the "good" one.)

## Buying the domain name

Once you’ve picked your domain, you need to buy it. If you’re a startup, you don’t have any infrastructure yet, and probably have to rely on personal email accounts to get things started.

0. Ensure you have Multi-Factor Authentication enabled on your account, ideally, using a method that is not SMS or voice based. Your email account will be used to buy the domain, and until you have corporate email set up, could turn out to be the weakest link towards attacking your new company. It must be as safe as possible.
1. Pick  a registrar that supports Multi-Factor Authentication. Many do by now, though [some](https://www.hover.com) don’t [murder elephants](https://science.time.com/2011/04/04/godaddy-ceo-on-shooting-an-elephant-im-not-sorry/), and enable MFA as fast as possible.
2. Buy the domain for multiple years. You want to be sure you have time to move to a more corporate type account by the time it gets renewed.
3. Configure [domain privacy](https://en.wikipedia.org/wiki/Domain_privacy). While it looks shady for a company to hide details from [WHOIS](https://en.wikipedia.org/wiki/WHOIS), you don’t want to share your information until you have a real corporate address and email account.
4. Configure the [Registrar Lock](https://www.icann.org/resources/pages/locked-2013-05-03-en). This will ensure your domain can’t easily be transferred to another registrar out of your control.
5. Follow the same process to buy your domain names on other common TLDs (`.net`, `org`, your country's).


## Next Steps

Once you’ve configured corporate email (post on that coming soon!), you’ll need to go back and edit your domain.

1. If the cloud provider you’re using has a [cloud registrar](https://cloud.google.com/domains/docs/overview), prepare to move your domain(s) there. Keep in mind it’s not always possible to move recently purchased domains, sometimes requiring a period of 60 days to go by before moving them. **Set a reminder**. Why use a cloud provider’s registrar? You’re going to spend a lot of time controlling access to cloud resources, making domains a part of that is a good way to re-use future work. 
2. No matter what, make sure that logging in to your registrar as well as any "recovery option" is configured to use company emails by this point, not personal ones.
2. Change the contact information on the domain to a generic group on your new corporate email environment, pointing to at least two people. You wouldn’t want an important notice related to your domain to be missed due to vacation. 
3. Once you have a mailing address, disable domain privacy, as it looks suspicious for a company to be using that.
