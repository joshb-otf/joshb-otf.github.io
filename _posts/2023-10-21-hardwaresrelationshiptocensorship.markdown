---
layout: post
title:  "Introduction to Hardware Restrictions: Can You Trust Your Phone?"
date:   2023-10-21 00:00:00 -0700
categories: jekyll update
---
## What kind of phone do you have? 
Do you know where it comes from? Do you know where the parts come from? Do you know how the parts work?
For many of us, the answer to that last question is no. The modern cell phone has evolved greatly in a short span of time. It is a highly complex device that promises many forms of security such as physical and digital-- types of security that protect our phones from getting broken into or stolen and types of security that protect our communication and information. There are many phones to choose from and many different systems behind them. 


### Do you trust your phone?
Most of us do things on our phones that we would prefer to keep private. For example, some of us use banking applications, send sensitive emails or messages, express beliefs, or use our payment information to make purchases. For these reasons and more it is important to most users that their phones be secure. For users in countries with oppressive governments or censorship and information restriction, the privacy and security of these devices are even more important. Luckily, research communities are putting more effort into gathering information to determine which phones are trustworthy-- especially for at-risk users. The site this blog is posted on is one such effort being supported by the <A href="https://www.opentech.fund">Open Technology Fund's</A> Information Controls Fellowship!
## What makes a phone trustworthy? 
How do you decide whether or not to trust a phone? Phones are incredibly complex systems; the basis of trust is understanding. Making a phone involves balancing a myriad of hardware and software designs. In these designs a few areas are of special interest in deciding whether one should trust their phone:
### Cryptographic keys
You might have heard of cryptography or end to end encryption, and you'd be right to understand it as a technology that is capable of securing both communications between two users and securing data that is locally on your device. Cryptography utilizes large numbers called keys and some special math to create a system in which data is either encrypted or decrypted with one's keys. Different cryptography models use keys differently, but private keys are almost always treated as secrets, and shouldn't be known by any untrusted parties. What's more, in the modern web almost every communication needs to utilize encryption to maintain security, otherwise an attacker need only be on the same network as you to access any information you share-- including a website's credentials, such as your bank's. In order to store and manage such keys, many phones come with special purpose-built designs that utilize hardware to keep your keys secure from anyone who might try to install malware (viruses) on your phone or even keep them secret from someone who has physically stolen your device.
### Trusted software
Most people understand that their phone is running an operating system, or OS for short, and that this operating system handles lots of behind-the-scenes things that happen on a phone. A fun fact is that modern phones also often contain multiple operating systems, usually at least two! At least one of these operating systems is reserved for running secure software. This secure or trusted software is chosen by the manufacturer of the device and can handle any number of use-cases. Phones are complex systems that combine communication between these operating systems to accomplish certain activities with less risk, such as storing or using cryptographic keys! Since this software has a huge security impact, depends on the phone you have, and isn't usually accessible by the user, it is of special interest for research efforts looking to understand which phones are trustworthy. If an untrustworthy party were to have full control of the trusted software on your phone, they could implement any number of privacy violating, security compromising, or information controlling capabilities.
### Main operating system
Every modern cellphone user is probably familiar with the main OS their phone runs-- the most popular being Android and iOS. In modern cellphones the manufacturer of the cellphone often provides alterations to the original OS, often in the form of features such as design changes or the set of privileged apps that come with a phone. The operating system is complex because it must interact with and utilize most of the other components in the system which, together, make up a phone. It ultimately controls how every request an application makes is handled, and how every action the user performs is handled. This means that an operating system is capable of preventing privacy-preserving apps from being available to install, or it can leak information in the app. It can also explicitly enforce censorship or aid in an app's ability to thwart privacy or security.

<img src="/images/Phoneinf3.svg">

## Hardware restrictions and information controls
This blog is about how something called hardware restrictions might give manufacturers or other interested parties the ability to introduce information controls. But what are information controls, and what are hardware restrictions?
### Information controls
Previously, we saw examples on how several components in the complex machines we call phones can be an opportunity for a manufacturer or other entity in control of the design process, such as a parts manufacturer or government, to implement capabilities that either control or monitor the information that our phones send, receive, and store. We call these capabilities "information controls". Information controls are usually implemented on networks or through import/export laws in a country, but with the increasing level of control in modern phones the cost for implementing controls on phones may be dropping sharply.

**If your phone was capable of enacting information controls, why couldn't you just turn them off in settings?** Not only could you not turn them off, it is unlikely that anyone could avoid them through the means of software. Unfortunately, phone makers have historically often not exposed the full capability of software to the user. This is done for various reasons, often because it is cited as too confusing, or that there are security risks to a non-technical user to modify the behavior of the device. But if one owns their device and knows the password, what is actually stopping one from disabling these information controls?
### Hardware restrictions 
In the past users have been able to modify the behavior or code of applications on their devices. They could download and use other peoples' applications directly from the source and could easily make applications that access whatever information they wanted which they could then distribute however they wished for whoever to download and use. The user could take control of any application on their device, which meant an application was subject to the user's intentions. The user could design or download their own operating system and use it on their hardware. The user was in charge of either devising a method to keep their device secure or picking a party that they trusted (usually an operating system vendor) to decide the strategy. With modern phones and hardware-based restrictions of the user's capability, this agency or freedom of the user is often not only no longer the default shipped on devices, it is not available at all.
#### Why?
When we mentioned the three concepts from before (<A href="#cryptographic-keys">"cryptographic keys"</A>, <A href="#trusted-software">"trusted software"</A>, and <A href="#main-operating-system">"main operating system"</A>) we talked briefly about how they were designed with security in mind. In most cases the user's security is the driving force for design patterns, but in some cases security decisions are not purely for the user's security. The pursuit of security in modern devices has sometimes even meant the sacrifice of the user's agency. This sacrifice of users' agency can provide obscurity for the device manufacturer's security efforts and can stop certain unwanted parties from accessing the device-- such as hackers who have physical access to the device, or hackers who have compromised an application on the device. It can also help stop social engineering attacks, a type of hacking strategy in which the hacker attempts to convince the user to compromise their own system; since users do not have the ability to completely compromise their own system (only partially), they cannot be convinced to do so by strangers. However, these designs also make room for some capabilities that are seemingly motivated by the profit of the manufacturer or other interested parties; these capabilities allow security models like Digital Rights Management or DRM, in which the main security objective is to protect the data from the user accessing it so that digital content such as songs/movies/games can be delivered to a device without risk of piracy or even fair-use alterations. Another capability seen is the strategy to lock users into certain application distributors or "app stores", which can deny the user the ability to access certain information or content but in exchange gives the manufacturer the ability to take a cut of app sales and ensure only apps that have passed certain security and usability standards may exist on the device. Other capabilities exist in the form of anti-cheat for games, region locking devices, locking devices into certain carriers, 'jailbreak' or 'root' detection and more.
#### How?
Hardware restrictions are not usually a documented part of a system that can be easily looked up. Hardware restrictions are often either implemented as a feature or part of a component of the system's overall design. This means their parts are integrated at every level in the device, with varying uses and security models (their goals). For example, in the process of powering on or booting a device hardware restrictions can often be utilized to deny the loading of code or in many cases operating systems and trusted software that do not exactly match the version the manufacturer chose. The risk of locking the user into the manufacturers chosen main operating system is that once locked in, not only is the degree of freedom for certain information avenues like web browsers, app stores, and messaging apps decided by the manufacturer, the way that an operating system utilizes trusted software, cryptographic keys, and also hardware is also locked in; this means that in an environment where the manufacturer has this level of control, there are tons of ways they could implement information controls! This doesn't mean that if a user can control the main operating system they are immune to information controls, but it is a huge advantage to any interested parties trying to implement hardware restrictions to make sure they have control of this system. This is just one example of a hardware restriction and the various ways it could be utilized to make information controls more effective, in reality there are several ways in which a manufacturer designing the hardware and software of a phone could restrict the user's operating capacity through hardware means with an end goal of controlling information on a device. 

<img src="/images/hardware_restrictions_f3.svg">

## The research we have planned
It is my (the Author's) personal nightmare that we may find ourselves in a future where countries with the means to develop information technology might have the inclination to deploy, sell, or build information technology devices or infrastructure that enacts that country's own --or provides an authoritarian government the means to set up their own-- information controls. I believe properly handling these risks is paramount to human rights, especially when you consider the at-risk users in these circumstances. Authoritarian governments and foreign nations have been utilizing their technological developments and resources to manipulate under-developed nations and minority populations for much of modern history, control of information must not happen. Since hardware restrictions can lock the user in to the manufacturer's choices and also obscure the details of how a device works, they can make it hard to trust a device in a world where the cost of effort to implement information controls on a device is decreasing rapidly-- especially if the device originates from a company or nation that exercises its own information controls, has an authoritarian government, or has an incentive to control the flow of information of a population.
#### As countries and manufacturers continue to influence and develop their own main operating systems, trusted software, and especially hardware, the opportunity to introduce novel hardware restrictions and information controls presents itself as all too easy.
To help mitigate the risks of this situation and to discover to what degree this harmful use of information controls and hardware restrictions exists in our modern day, the  <A href="https://www.opentech.fund">Open Technology Fund's</A> Information Controls Fellowship has green lit a project dedicated to exploring hardware restrictions and information controls, specifically: which exist, which are currently possible with today's hardware, and what risks are greatest in modern phones from authoritarian countries with information restrictions. This project is important since 
public researchers usually have no more access than regular users to these devices, as such there is a scattered history of public analysis and awareness on the capability of these designs. The project will start with this non-technical blog and continue over the year with the analysis of several target devices. At the end of the project the findings will be presented in a non-technical manner and the technical resources gathered will become publicly available to assist in other research.

<img src="/images/research_planned.svg">

## What can you do?
If you have information you would like to contribute or need to make contact you can reach out to <A href="mailto:info@trustinghardware.com">info@trustinghardware.com</A>.
In the meantime, the organization funding this research-- the <A href="https://www.opentech.fund">Open Technology Fund</A> has funded excellent <A href="https://www.opentech.fund/results/supported-projects/?page=1">projects</A> that provide resources on information controls and open technology.
Subscribe to our <A href="https://trustinghardware.com/feed.xml">RSS feed</A> or sign up for notifications below to get updates on the project!

<style>
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview {
  display: flex !important;
  flex-direction: column !important;
  justify-content: center !important;
  margin-top: 30px !important;
  padding: clamp(17px, 5%, 40px) clamp(17px, 7%, 50px) !important;
  max-width: none !important;
  border-radius: 6px !important;
  box-shadow: 0 5px 25px rgba(34, 60, 47, 0.25) !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview,
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview *{
  box-sizing: border-box !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-heading {
  width: 100% !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-heading h5{
  margin-top: 0 !important;
  margin-bottom: 0 !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field {
  margin-top: 20px !important;
  width: 100% !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field input {
  width: 100% !important;
  height: 40px !important;
  border-radius: 6px !important;
  border: 2px solid #e9e8e8 !important;
  background-color: #fff !important;
  outline: none !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field input {
  color: #000000 !important;
  font-family: "Montserrat" !important;
  font-size: 14px !important;
  font-weight: 400 !important;
  line-height: 20px !important;
  text-align: center !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field input::placeholder {
  color: #000000 !important;
  opacity: 1 !important;
}

.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field input:-ms-input-placeholder {
  color: #000000 !important;
}

.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-input-field input::-ms-input-placeholder {
  color: #000000 !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-submit-button {
  margin-top: 10px !important;
  width: 100% !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-submit-button button {
  width: 100% !important;
  height: 40px !important;
  border: 0 !important;
  border-radius: 6px !important;
  line-height: 0px !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .form-preview .preview-submit-button button:hover {
  cursor: pointer !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .powered-by-line {
  color: #231f20 !important;
  font-family: "Montserrat" !important;
  font-size: 13px !important;
  font-weight: 400 !important;
  line-height: 25px !important;
  text-align: center !important;
  text-decoration: none !important;
  display: flex !important;
  width: 100% !important;
  justify-content: center !important;
  align-items: center !important;
  margin-top: 10px !important;
}
.followit--follow-form-container[attr-a][attr-b][attr-c][attr-d][attr-e][attr-f] .powered-by-line img {
  margin-left: 10px !important;
  height: 1.13em !important;
  max-height: 1.13em !important;
}
</style>
<div class="followit--follow-form-container" attr-a attr-b attr-c attr-d attr-e attr-f><form data-v-1bbcb9ec="" action="https://api.follow.it/subscription-form/bE9sYzFKWDhUQW15dU5VRGtKZkxTV3hxczVhK1ExeCszN0ZjSHVBSC84T3FEQ3l5Qy8yYjNQeGUvOXFxOVpkaWNKT3FMNGRVVGpOUm1oQTFzWDJTWVl1T2gyNnJlajNFcmpZZURUTmF4dy91dDU0OVNiSjRGVzhzT2E3TmFkQWp8OGJSRG5SVlJNdHlHeW4ySGRWWHFDcFRETWlBejVjaVNCZjQwOUdDSnNNTT0=/8" method="post"><div data-v-1bbcb9ec="" class="form-preview" style="background-color: rgb(255, 255, 255); position: relative;"><div data-v-1bbcb9ec="" class="preview-heading"><h5 data-v-1bbcb9ec="" style="text-transform: none !important; font-family: Arial; font-weight: bold; color: rgb(0, 0, 0); font-size: 16px; text-align: center;">
                  Get new posts by email:
                </h5></div> <div data-v-1bbcb9ec="" class="preview-input-field"><input data-v-1bbcb9ec="" type="email" name="email" required="required" placeholder="Enter your email" spellcheck="false" style="text-transform: none !important; font-family: Arial; font-weight: normal; color: rgb(0, 0, 0); font-size: 14px; text-align: center; background-color: rgb(255, 255, 255); background-size: auto, 25px; background-image: none, url(&quot;data:image/svg+xml;utf8,<svg width='26' height='28' viewBox='0 0 26 28' fill='none' xmlns='http://www.w3.org/2000/svg'><path d='M23.8958 6.1084L13.7365 0.299712C13.3797 0.103027 12.98 0 12.5739 0C12.1678 0 11.7682 0.103027 11.4113 0.299712L1.21632 6.1084C0.848276 6.31893 0.54181 6.62473 0.328154 6.99462C0.114498 7.36452 0.00129162 7.78529 7.13608e-05 8.21405V19.7951C-0.00323007 20.2248 0.108078 20.6474 0.322199 21.0181C0.53632 21.3888 0.845275 21.6938 1.21632 21.9008L11.3756 27.6732C11.7318 27.8907 12.1404 28.0037 12.556 27.9999C12.9711 27.9989 13.3784 27.8861 13.7365 27.6732L23.8958 21.9008C24.2638 21.6903 24.5703 21.3845 24.7839 21.0146C24.9976 20.6447 25.1108 20.2239 25.112 19.7951V8.21405C25.1225 7.78296 25.0142 7.35746 24.7994 6.98545C24.5845 6.61343 24.2715 6.30969 23.8958 6.1084Z' fill='url(%23paint0_linear_714_179)'/><path d='M5.47328 17.037L4.86515 17.4001C4.75634 17.4613 4.66062 17.5439 4.58357 17.643C4.50652 17.7421 4.4497 17.8558 4.4164 17.9775C4.3831 18.0991 4.374 18.2263 4.38963 18.3516C4.40526 18.4768 4.44531 18.5977 4.50743 18.707C4.58732 18.8586 4.70577 18.9857 4.85046 19.0751C4.99516 19.1645 5.16081 19.2129 5.33019 19.2153C5.49118 19.2139 5.64992 19.1767 5.79522 19.1064L6.40335 18.7434C6.51216 18.6822 6.60789 18.5996 6.68493 18.5004C6.76198 18.4013 6.8188 18.2876 6.8521 18.166C6.8854 18.0443 6.8945 17.9171 6.87887 17.7919C6.86324 17.6666 6.82319 17.5458 6.76107 17.4364C6.70583 17.3211 6.62775 17.2185 6.53171 17.1352C6.43567 17.0518 6.32374 16.9895 6.20289 16.952C6.08205 16.9145 5.95489 16.9027 5.82935 16.9174C5.70382 16.932 5.5826 16.9727 5.47328 17.037ZM9.19357 14.8951L7.94155 15.6212C7.83273 15.6824 7.73701 15.7649 7.65996 15.8641C7.58292 15.9632 7.52609 16.0769 7.49279 16.1986C7.4595 16.3202 7.4504 16.4474 7.46603 16.5726C7.48166 16.6979 7.5217 16.8187 7.58383 16.9281C7.66371 17.0797 7.78216 17.2068 7.92686 17.2962C8.07155 17.3856 8.23721 17.434 8.40658 17.4364C8.56757 17.435 8.72631 17.3978 8.87162 17.3275L10.1236 16.6014C10.2325 16.5402 10.3282 16.4576 10.4052 16.3585C10.4823 16.2594 10.5391 16.1457 10.5724 16.024C10.6057 15.9024 10.6148 15.7752 10.5992 15.6499C10.5835 15.5247 10.5435 15.4038 10.4814 15.2944C10.4261 15.1791 10.348 15.0766 10.252 14.9932C10.156 14.9099 10.044 14.8475 9.92318 14.8101C9.80234 14.7726 9.67518 14.7608 9.54964 14.7754C9.42411 14.7901 9.30289 14.8308 9.19357 14.8951ZM14.2374 13.1198C14.187 13.0168 14.1167 12.9251 14.0307 12.8503C13.9446 12.7754 13.8446 12.7189 13.7366 12.6842V5.38336C13.7371 5.2545 13.7124 5.12682 13.6641 5.00768C13.6157 4.88854 13.5446 4.78029 13.4548 4.68917C13.365 4.59806 13.2583 4.52587 13.1409 4.47678C13.0235 4.42769 12.8977 4.40266 12.7708 4.40314C12.6457 4.40355 12.522 4.42946 12.407 4.47933C12.292 4.52919 12.188 4.602 12.1013 4.69343C12.0145 4.78485 11.9467 4.89304 11.902 5.01156C11.8572 5.13007 11.8364 5.25651 11.8407 5.38336V12.7168C11.7327 12.7516 11.6327 12.8081 11.5466 12.883C11.4606 12.9578 11.3903 13.0495 11.3399 13.1525C11.2727 13.2801 11.2346 13.4213 11.2284 13.5659C11.2222 13.7104 11.2481 13.8545 11.3041 13.9875C11.2481 14.1205 11.2222 14.2646 11.2284 14.4091C11.2346 14.5536 11.2727 14.6949 11.3399 14.8225C11.3903 14.9255 11.4606 15.0172 11.5466 15.092C11.6327 15.1669 11.7327 15.2233 11.8407 15.2581V22.5916C11.8407 22.8516 11.9425 23.1009 12.1236 23.2847C12.3047 23.4686 12.5504 23.5718 12.8065 23.5718C13.0627 23.5718 13.3084 23.4686 13.4895 23.2847C13.6706 23.1009 13.7724 22.8516 13.7724 22.5916V15.2218C13.8804 15.187 13.9804 15.1305 14.0664 15.0557C14.1525 14.9809 14.2228 14.8892 14.2732 14.7862C14.3404 14.6586 14.3785 14.5173 14.3847 14.3728C14.3909 14.2283 14.365 14.0842 14.309 13.9512C14.3917 13.6751 14.3661 13.3772 14.2374 13.1198ZM16.6735 10.6112L15.4215 11.3373C15.3127 11.3985 15.2169 11.481 15.1399 11.5802C15.0628 11.6793 15.006 11.793 14.9727 11.9147C14.9394 12.0363 14.9303 12.1635 14.946 12.2887C14.9616 12.414 15.0016 12.5348 15.0638 12.6442C15.1436 12.7958 15.2621 12.9229 15.4068 13.0123C15.5515 13.1017 15.7171 13.1501 15.8865 13.1525C16.0475 13.1511 16.2062 13.1139 16.3515 13.0436L17.6036 12.3175C17.7124 12.2563 17.8081 12.1737 17.8851 12.0746C17.9622 11.9755 18.019 11.8617 18.0523 11.7401C18.0856 11.6184 18.0947 11.4913 18.0791 11.366C18.0635 11.2408 18.0234 11.1199 17.9613 11.0105C17.906 10.8952 17.828 10.7927 17.7319 10.7093C17.6359 10.626 17.524 10.5636 17.4031 10.5261C17.2823 10.4887 17.1551 10.4769 17.0296 10.4915C16.904 10.5061 16.7828 10.5469 16.6735 10.6112ZM19.639 10.9742C19.8 10.9728 19.9587 10.9357 20.104 10.8653L20.7122 10.5023C20.8208 10.4406 20.9164 10.3578 20.9935 10.2586C21.0705 10.1593 21.1275 10.0456 21.1611 9.92394C21.1947 9.80228 21.2043 9.67508 21.1893 9.54965C21.1744 9.42421 21.1351 9.30302 21.0739 9.19302C21.0126 9.08303 20.9305 8.9864 20.8324 8.90869C20.7342 8.83098 20.6219 8.77372 20.5019 8.7402C20.3818 8.70667 20.2564 8.69755 20.1329 8.71335C20.0094 8.72915 19.8902 8.76957 19.7821 8.83227L19.174 9.19531C19.0651 9.25651 18.9694 9.33909 18.8924 9.43822C18.8153 9.53735 18.7585 9.65106 18.7252 9.77271C18.6919 9.89436 18.6828 10.0215 18.6984 10.1468C18.7141 10.272 18.7541 10.3929 18.8162 10.5023C18.8981 10.6494 19.018 10.7711 19.163 10.8543C19.308 10.9374 19.4725 10.9789 19.639 10.9742ZM20.7122 17.4001L20.104 17.037C19.8859 16.9133 19.6284 16.8823 19.3878 16.9508C19.1472 17.0193 18.9432 17.1816 18.8202 17.4024C18.6973 17.6231 18.6655 17.8843 18.7318 18.1288C18.798 18.3733 18.957 18.5812 19.174 18.707L19.7821 19.0701C19.9274 19.1404 20.0861 19.1776 20.2471 19.179C20.4165 19.1766 20.5821 19.1282 20.7268 19.0388C20.8715 18.9494 20.99 18.8223 21.0699 18.6707C21.1339 18.5648 21.1755 18.4466 21.1921 18.3235C21.2087 18.2003 21.1999 18.0751 21.1662 17.9556C21.1326 17.8361 21.0749 17.7251 20.9967 17.6294C20.9185 17.5338 20.8216 17.4557 20.7122 17.4001ZM17.6 15.6212L16.348 14.8951C16.2399 14.8324 16.1207 14.792 15.9971 14.7762C15.8736 14.7604 15.7482 14.7695 15.6282 14.803C15.5082 14.8365 15.3958 14.8938 15.2977 14.9715C15.1995 15.0492 15.1174 15.1458 15.0562 15.2558C14.9949 15.3658 14.9557 15.487 14.9407 15.6125C14.9257 15.7379 14.9353 15.8651 14.9689 15.9868C15.0026 16.1084 15.0595 16.2221 15.1366 16.3214C15.2136 16.4206 15.3092 16.5035 15.4179 16.5651L16.6699 17.2912C16.8152 17.3615 16.974 17.3987 17.135 17.4001C17.3043 17.3977 17.47 17.3493 17.6147 17.2599C17.7594 17.1705 17.8778 17.0434 17.9577 16.8918C18.0228 16.7862 18.0653 16.6679 18.0825 16.5445C18.0997 16.4212 18.0911 16.2955 18.0574 16.1757C18.0237 16.0559 17.9655 15.9447 17.8867 15.8491C17.8079 15.7536 17.7103 15.6759 17.6 15.6212ZM7.94155 12.2812L9.19357 13.0073C9.33888 13.0776 9.49761 13.1148 9.6586 13.1162C9.82798 13.1138 9.99363 13.0654 10.1383 12.976C10.283 12.8866 10.4015 12.7595 10.4814 12.6079C10.5435 12.4985 10.5835 12.3777 10.5992 12.2524C10.6148 12.1272 10.6057 12 10.5724 11.8784C10.5391 11.7567 10.4823 11.643 10.4052 11.5439C10.3282 11.4447 10.2325 11.3622 10.1236 11.301L8.87162 10.5749C8.76383 10.5118 8.64476 10.4712 8.52134 10.4553C8.39792 10.4395 8.27262 10.4487 8.15275 10.4825C8.03288 10.5163 7.92084 10.574 7.82317 10.6521C7.72549 10.7303 7.64413 10.8275 7.58383 10.9379C7.46399 11.166 7.43428 11.4319 7.50073 11.6814C7.56719 11.9309 7.72481 12.1454 7.94155 12.2812ZM6.40335 9.19531L5.79522 8.83227C5.68714 8.76957 5.56791 8.72915 5.44439 8.71335C5.32087 8.69755 5.19549 8.70667 5.07546 8.7402C4.95542 8.77372 4.8431 8.83098 4.74493 8.90869C4.64676 8.9864 4.56469 9.08303 4.50343 9.19302C4.44217 9.30302 4.40293 9.42421 4.38796 9.54965C4.37299 9.67508 4.38259 9.80228 4.4162 9.92394C4.44981 10.0456 4.50677 10.1593 4.58382 10.2586C4.66087 10.3578 4.75647 10.4406 4.86515 10.5023L5.47328 10.8653C5.61859 10.9357 5.77732 10.9728 5.93831 10.9742C6.10769 10.9718 6.27334 10.9234 6.41804 10.834C6.56273 10.7447 6.68118 10.6176 6.76107 10.466C6.82193 10.3592 6.861 10.2411 6.87592 10.1187C6.89085 9.99635 6.88134 9.87216 6.84796 9.75358C6.81457 9.635 6.758 9.52446 6.68161 9.42854C6.60523 9.33263 6.51059 9.25331 6.40335 9.19531Z' fill='%2320133A'/><defs><linearGradient id='paint0_linear_714_179' x1='7.13608e-05' y1='14.001' x2='25.1156' y2='14.001' gradientUnits='userSpaceOnUse'><stop stop-color='%239059FF'/><stop offset='1' stop-color='%23F770FF'/></linearGradient></defs></svg>&quot;); background-repeat: repeat, no-repeat; background-position: 0% 0%, right calc(50% + 0px); background-origin: padding-box, content-box;" class="relay-email-input-with-button-hovered"><button type="button" style="border: 0px none; clip: rect(0px, 0px, 0px, 0px); clip-path: inset(50%); height: 1px; margin: 0px -1px -1px 0px; overflow: hidden; padding: 0px; position: absolute; width: 1px; white-space: nowrap;">Generate new mask</button></div> <div data-v-1bbcb9ec="" class="preview-submit-button"><button data-v-1bbcb9ec="" type="submit" style="text-transform: none !important; font-family: Arial; font-weight: bold; color: rgb(255, 255, 255); font-size: 16px; text-align: center; background-color: rgb(0, 0, 0);">
                  Subscribe
                </button></div></div></form></div>