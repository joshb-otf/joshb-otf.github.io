---
layout: post
title:  "Can You Trust Your Phone?"
date:   2023-09-25 18:27:29 -0700
categories: jekyll update
---
### What kind of phone do you have? 
Do you know where it comes from? Do you know where the parts come from? Do you know how the parts work?
For many of us, the answer to that last question is no. The modern cell phone has evolved greatly in a short span of time. It is a highly complex device that promises many forms of security such as physical and digital-- types of security that protect our communication and types of security that protect our phones from getting broken into or stolen. There are many phones to choose from, and many different systems behind them. 
### Do you trust your phone?
Most of us do things on our phones that we would prefer to keep private. For example, some of us use banking applications, send sensitive emails or messages, express political beliefs, or use our payment information to make purchases. For these reasons it is important to most users that their phones be secure. For users in countries with oppressive governments or censorship and information restriction, the privacy and security of these items are even more important. Luckily, we are conducting research to gather more information in helping everyone determine which phones are trustworthy.
### What makes a phone trustworthy? How do you decide whether or not to trust a phone?
Phones are complex systems. Making one involves balancing a myriad of hardware and software designs. In these designs a few areas are of uique interest in the context of whether or not one should trust their phone:
#### Cryptographic keys
You might have heard of cryptography or end to end encyption, and you'd be right to understand it as a technology that is capable of both securing communications between two users, or securing data that is physically on your device. What's more, in the modern web almost every communication needs to utilize encryption to maintain security, otherwise an attacker need only be on the same network as you to access any information you share-- including a websites credentals, such as your banks. In order to store and manage such keys, phones come with special purpose-built designs to keep keys secure from anyone who might try to install malware (viruses) on your phone or even from someone who has stolen your device. 
#### Trusted software
Most people understand that their phone is running an operating system, or OS for short, and that this operating system handles lots of behind-the-scenes things that happen on a phone. A fun fact is that modern phones also contain multiple operating systems, usually at least two! At least one of these operating systems is reserved for running secure software. This secure or trusted software is chosen by the manufacturer of the device and can handle any number of use-cases. Phones are complex systems that combine communication between these operating systems to accomplish certain activities with less risk, such as storing or using cryptographic keys! Since this software has a huge security impact, depends on the phone you have, and isn't usually accessible by the user, it is of special interest for research efforts looking to understand which phones are trustworthy. If an untrustworthy party were to have full control of the trusted software on your phone, they could implement any number of privacy violating, security compromising, or information controlling capabilities.
#### Main operating system
Every modern cellphone user is probably familiar with the main OS their phone runs-- possibly Android or IOS come to mind. In modern cellphones the manufacturer of the cellphone often provide alterations the original OS, often in the form of features such as design changes or the set of priveliged apps that come with a phone. The operating system needs to be complex to represent the complexity of the rest of the system as a whole. It ultimately controls how every request an application makes is handled, and how every action the user performs is handled. This means that an operating system is capable of preventing privacy preserving apps from being available to install, or it can leak information in the app. It can also explicitly enforce censorship or aid in apps ability to thwart privacy or security.

<img src="/images/Phone_info_4.svg">
_____ Below is largely TODO _____

...thwarting privacy apps through os, thwarting security/privacy through os, providing means of censorship through os

### Hardware restrictions
Where they come in, how they make it harder to trust the above things since they are sometimes determined at the factory

> Infograph of hardware restrictions goes here

### The research we have planned
Due to the complexity of modern phones, all the aspects that decide a phones trustworthiness listed above are tighly woven into the system design and as such to properly analyze them researchers must include hardware and firmware (low level software that controls hardware) in the scope of their analysis.

...Talk about our investigation into the proving possibilities of existing hardware in enforcing censorship in the future

> Inforgraph of research?

### What can you do?
...If you are a another researcher we believe it is imperitive that the trustworthiness of phones be looked into and publicized by as many parties as possible.

__Rough notes below___

### What about if your phone was stolen?
If an average person came across or stole your phone, would it be important to you that they can not gain access? What if an advanced organization such as a hacker group or nation had your phone?
### Do you trust your network?
For people in some nations the reality is that their network, either internet service provider or mobile network, is operated by entities looking to gain access to the information they hold private. Many applications exist to aid in the circumvention of this kind of prying eye: end to end encrypted messengers like Singal and Whatsapp.

As the underlying systems that make up our phones increase in capability, the cost to implement custom logic on each system decreases. This logic could be a new feature, or it could be spyware.

Information controls as systems
Changes to software
Changes to hardwares

Explanation of TEE/trust zone/secure processors/security keys

Can existing hardware be subverted by governments to enact information controls

Can hardware be easily created by governements to enact information controls

Why is is ultimately important to the non-technical?
Knowing which devices are safe for users that could be susceptible to information controls

Actions the energetic reader can partake in:
Limit hardware to trusted companies with a track record in privacy.
Ensure the hardware is sourced safely.