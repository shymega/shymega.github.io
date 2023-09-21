---
title: "My work with Planet Computers, and why: Pt 2"
date: "2023-03-13"
draft: true
---

## DISCLAIMER: As I have signed an NDA with Planet Computers, this post is of my own views, and NOT those of Planet Computers. They should not be contacted for comment.
## I am restricted in the information I can release, so please, no emails or DMs asking for information.

So, to continue from my [last post][last_post], I was talking about CoDi.

I haven't made much progress with CoDi, because I need to be able to replicate
the STM32 locally. I don't have any STM32L4R9AIIX boards, with external
flash/RAM, and a display, so I'm kinda stuck in what I can achieve.

The open-source CoDi firmware started off as `CoDirs`, - CoDi(rust/rs), and as
a workspace crate. I did consider using something like [Drone][drone] or [Tock
OS][tock], and felt that because of the niche status of the STM32 inside the
Cosmo, it would be a rather wasted effort to add support for such a specific
configuration.

So, my focus so far has been building a whole new 'suite' of CoDi software
components. This includes the bootloader, main firmware, customisable
'resources' - so language packs specific to each Android install, icons, fonts,
and of course, the component I've been focusing on the post as a basis -
`codid` - a Rust daemon that runs on all ROMs, focusing on provided a generic
interface via gRPC to CoDi.

[last_post]: https://blog.shymega.org.uk/posts/my-work-with-planet-computers-and-why-pt-1/
[drone]: https://www.drone-os.com/
[tock]: https://www.tockos.org/
