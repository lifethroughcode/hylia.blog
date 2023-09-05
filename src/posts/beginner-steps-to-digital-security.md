---
layout: layouts/post.njk
title: Beginner steps to digital security
date: 2023-08-28T18:24:00.135Z
---
##### *It's been a while since I last made a post here - a little too long!*

##### *I am going to try post here at least once a month going forward. I had a few messages from people that found my last post about Proton VPN helpful, and that was really nice to see, and has prompted me to make a bit more effort with this blog.*

Our whole lives are connected to the internet, so it's important to understand some ways you can protect yourself.

This post is going to cover a few things you can do, or should be aware of, that will help you become more secure online. I see a lot of people on a daily basis that are not security conscious at all, or do not understand the importance of online security. 

# \#1 Use a password manager

This is the first step I would recommend to everyone, get control over your online accounts and secure them properly. 

There are several options for helping organise your accounts and passwords, the main one I recommend is Bitwarden, it's easy to get started and using the cloud option means your passwords will sync between devices.

This will allow you to create random passwords for your accounts rather than the same 3 passwords for everything! With a password manager you don't need to know your passwords, they should be completely random. You can then copy the password from your vault, or even use auto-fill features via browser extensions or mobile apps. 

There are many others on the market but this is the one I have the most experience with. I would like to try Proton Pass at some point as I'm interested in the SimpleLogin integration for email aliases, so I may migrate to that eventually.

If your technical skills are more advanced you could host Bitwarden yourself, or use something like KeyPassXC. But if you want a hassle/maintenance free password manager that just works I would not recommend this. 

Just make sure you use a good master password, and take regular backups!! A USB with a Veracrypt volume is a great way to have a last resort backup - <https://bitwarden.com/resources/guide-how-to-create-and-store-a-backup-of-your-bitwarden-vault/>

# \#2 Two Factor Authentication

Often referred to as 2FA or MFA (multi factor authentication).

When you login to site or service, you will be prompted to enter a code which is sent or created from another device. The most common one's seen are SMS based authentication where the site will send a code to the mobile number on the account. This is ok, but not as secure as using an authenticator app, like Aegis (Android only), Authy, Google Authenticator, etc. That being said SMS 2FA is better than nothing! 

Personally I like Aegis if you have an android device, it feels a lot more security focused than other options. And it encrypts the tokens at rest. It's also available on F-Droid if preferred. <https://getaegis.app/>

Just make sure you are backing up your token vault, and you securely save the backup codes for any site you set this up on to ensure you can get back into your account should you lose your vault somehow.

Make sure you set up 2FA on your Password Manager too! 

# \#3 Update everything

Updates are so important, they often include security fixes that help protect your device from known attacks. 

If set up to do so then most devices will update automatically but I make an effort to check mine on a regular basis, including; computer operating system, mobile phone iOS/Android, app updates from PlayStore/AppStore, if you run any servers update them regularly as well where possible. 

Don't forget to check for updates on your network equipment, routers, switches, access points, etc. just be sure to backup the config first. 

# \#4 Be careful what you post online

I see so many people post personal identifiable information online, or even pictures that make it very easy to work out where they live, I've even seen this on Instagram accounts of famous people. 

Before you post pictures to social media check whats in the background, the smallest details can be used to figure out your location, or potentially useful to get into online accounts, or for identity fraud. 

I would highly recommend not posting photos of your children online. There are so many risks involved with doing this, the biggest risk is child predators using these pictures, and it does happen. I could write a whole post about this topic and possibly will in future. 

Also consider the little things like your WhatsApp profile picture for example, this is public to anyone if they have your mobile number.

The more information you post online about your life the more vulnerable you become. It can be nice to share goals and achievements but be careful who you are sharing this with, and is the risk worth it.

# \#5 VPN

When you search online this is not private, your ISP (Internet Service Provider) will be able to see this, and the data can then be used for advertising as well as other things. Websites will also log information about your connection including your public IP address which is not ideal.

To protect yourself from this it's best to use a VPN (Virtual Private Network). This encrypts your data in transit and routes it through a private server making your data unreadable to your ISP and protecting your public IP from being exposed.

I would not recommend using a free VPN service as they will likely collect your data and sell it. You want a paid service that has a no logging policy, meaning they won't store any identifiable information.

There are plenty of good options for this, personally I recommend Proton VPN, it's very stable and I trust their security and privacy. It's also really good value if you go for Proton Unlimited as you get Mail, Cloud storage, and a Password manager as well as the VPN. <https://proton.me/>