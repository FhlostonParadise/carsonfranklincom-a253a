---
title: Casa de Franklin - Logical Layout
subtitle: Doesn't Everyone Do This?
date: '2021-05-14'
thumb_img_alt: network
content_img_alt: network
seo:
  title: Casa de Franklin - Logical Layout
  description: Some of my client's have far less complex networks...
  tags: []
  robots:
    - all
  extra: []
  type: stackbit_page_meta
layout: post
thumb_img_path: images/energetic-mustard.png
content_img_path: images/energetic-mustard.png
excerpt: >-
  A breakdown of the systems I use for my home network. It's more than you might
  think.... 
---
## Some Background

As I started adding bits of technology to my home network I started to realize it was looking more and more like a network I might encounter at a client's office. I decided that if that was the case, I should document it in the same way. I'm glad I did. I've completely rebuilt it quite a few times, and having the documentation on each service with notes on why things were setup a certain way saved me a lot of time. Here is the latest iteration of it with some specific details redacted.

![](/images/energetic-mustard.png)



# The 60,000 ft. View

*   I am currently using Proxmox as the Hypervisor for the servers setup at home. This was mainly for educational reasons. I had not used the software in a professional capacity yet (I normally work with VMWare exclusively). I like it, but for my next build I will be going back to VMWare. I find myself spending more time figuring out tasks in Proxmox that I know like clockwork in VMWare. Normally this isn't a big problem, but these days my time to work on stuff at home is limited. I think I'll continue to use Proxmox for a development environment at home, but since I've started using the over all system to actually keep things alive (Fish and Coral!), I need to treat it with that level of importance.

*   Cloudflare - I'm using cloudflare's free SSL and DNS service to handle all of my DNS (including this site). It also functions as a proxy to hide the public IP's of the services I host at home.

*   Digital Ocean - I run a single VPS at Digital Ocean that handles services I don't want to risk being interrupted when I may not be at home. Things like Bitwarden RS (now Vaultwarden) I use regardless of where I am, I don't want to be unable to access my passwords and logins if I am away and the system goes down. The servers I have at home are great, and haven't had any issues, but I feel more comfortable with some infrastructure managed externally.

*   Traefik - Huge fan of this software. It was not a walk in the park to learn and configure correctly, but it really paid off. I don't know if I would recommend it to someone just getting into the self-hosted / home automation world unless they have some serious time to learn it.

*   Docker - Wrapping as much as I can into a containerized system like docker makes it very simple for me to rebuild things in the event they do down. In a world of microservices, docker seems like a great fit. I think the next rebuild may be a dive into Kubernetes. 
