---
title: "My work with Planet Computers, and why: Pt 1"
date: "2023-03-07"
draft: true
---

## DISCLAIMER: As I have now signed an NDA with Planet Computers, this post is of my own views, and NOT those of Planet Computers. They should not be contacted for comment.
## I am restricted in the information I can release, so please, no emails or DMs asking for information.

I thought, in light of the new "Planet Embedded" XR-series that has been recently launched, it might be a good idea for me to explain my affiliation with the company behind it, the Gemini PDA, Cosmo Communicator, and their latest phone (but sadly not the latest SoC; this is a blessing in a way, more in future posts), Astro Slide 5G Transformer.

To begin this post, I think it necessary to explain where my work with Planet started. It started shortly after I received my Cosmo Communicator via IndieGoGo (one of my first crowdfunding campaigns). I was very curious about CoDi, and there wasn't much information surrounding the system driving it. I had already observed many deficiencies with CoDi, and had worked it out it was over UART. But UART is slow, and this, I felt, was the reason behind the slow - what turned out to be XMODEM - update process on the bootloader.

I was trying my best to contact the development team behind CoDi and only reached Customer Care. By lucky chance, I managed to get hold of the brilliant Davide Guidi, with whom we communicated over email before moving to IM. NDA wasn't signed then, as I don't think I was trusted enough (In fact, it's only in Feb 2023 I managed to get access to the Astro Slide BSP), so access to the CoDi sources wasn't an option.

Davide and I communicated extensively, and I met Dr Janko and the CoDi developer plus Davide over a Zoom call, which was productive. Davide was an integral driving force behind Planet Computers, who had a vision, and tried hard to help the community.

I seem to recall he was the one who released the initial SailfishOS build to the community, with help from Nikita (for those who don't know, Adam Boardman, Nikita (NotKit/TheKit) and I are the main *active* community developers), which was basic and hasn't seen much love since he [Davide] left.

Davide worked on the `codi-app` repository which was moved to the Gemian organisation, and I forked it since then, to use proper Python techniques, which will hopefully - if Adam and Nikita approve - be merged into Gemian, and maybe we can replace `codi-app` with the CoDi daemon `codid`, my Rust version.

But that's a digression. I suppose the next logical step I had with CoDi was because the design partner and a proprietary GUI library are involved with the codebase, it made sense to replace the firmware on the STM32L4R9AIIX with an open-source version. But the question was, which language? I was aware of the issues on CoDi with transliteration encoding, which would be a major factor if I chose to use something like C, or C++.

I settled on Rust, with a built-from-the-ground-up, minimal real-time interrupt-driven microkernel, which felt like the best language and design, as it would save battery, be secure against exploits, ensure memory-safety, and support Unicode (specifically, UTF-8) from the start, meaning snazzy emojis on CoDi! Just kidding. Maybe. I'm not too fond of Emojis, but the UTF-8 support was there, and we could choose to have emojis on CoDi.

This blog post is getting a little long now, and I've been on holiday in Geneva. As I write this and sign off, I'm on a plane back home, which was close to being cancelled today (7th of March 2023), due to the French strikes.

I will leave the blog post here, as it's a bit cramped on the plane.

Au revoir!
