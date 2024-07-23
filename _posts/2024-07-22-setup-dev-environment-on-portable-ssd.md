---
title: Setting Up Your Development Environment on a Portable SSD
categories: [Dev]
tags: [dev-environment]
---

Now that I'm getting serious about developing my freelancing business and working on side projects, I've decided I need to stop procrastinating and setup a functional development environment on my laptop.

I've developed software as part of my day job almost exclusively in RHEL/Rocky linux VMs, so I want to continue in that same vein. I'm most comfortable in linux, these days. However, I want a dedicated linux partition rather than adding that extra layer of virtualization, and I've always preferred Ubuntu over RHEL, so that'll be my OS of choice.

## Dual-boot Windows and Ubuntu

In the past, I've dual-booted Windows and Ubuntu on my desktop, and that works great... when I have access to 2 multi-terrabyte drives. My surface pro has 256GB. I could get my drive replaced, but I'm lazy and I'd rather not if I can avoid it.

## Ditch Windows Entirely

I also really enjoy my Surface Pro tablet's features that make sketching and note-taking a breeze, so replacing Windows entirely isn't on the table either.

## Windows Subsystem For Linux (WSL) - Close, But No Cigar

WSL has made large strides since I first tried it back in 2016 or 2017 (has it really been that long???). I've used it plenty of times throughout the years, and it continues to get better. The default OS is Ubuntu, so with it we can install anything we'd need (development libraries, docker/podman packages, etc.).

However, there are still a couple key issues that keep me from going all in. The main one being native UI development compatibility issues.

### Native UI Compatibility

Since we're developing in a linux subsystem, but the native UI is actually going to run in Windows, it leads to some unforeseen issues when you want to use any OS-specific packages. I've tried this a few times with python and things like [pywinauto](https://pywinauto.readthedocs.io/en/latest/) and it always causes problems.

### VPN and other Networking Issues

Anybody who knows me also knows that I **hate** networking with a passion. I know enough to be dangerous, but the last thing I want to do when trying to write some software is mess around with networks and multicast routes. Now, accessing the WSL LAN has become much easier, and it can be found with a quick `ipconfig` command, but I still have occassional problems accessing data behind VPNs. I can hack it by messing with interface metric priorities, but I want my environment to follow the KISS principle. I want to minimize the amount of miscellaneous distractions, and mucking around 

## Final Solution - Linux On A Portable SSD

Instead, I bought one of these handy-dandy [1TB portable SSDs](https://a.co/d/btbaTXC) (on sale for $90 at the time of writing) and installed a bootable Ubuntu partition on it. Whenever I want my Ubuntu OS, I simply plug in my drive and start it up. Ubuntu puts itself at the top of the boot order by default, so there's no need to manually touch the BIOS. Whenever the drive is removed, Windows starts up just as before. It's as close to dual-booting as I can get, and the size of this portable SSD makes it incredibly viable. Speed-wise, it's just an extra few seconds, max. I'd say that's an easy pill to swallow.

### Hardware Compatibility Trade-off

With Ubuntu's fantastic hardware interoperability, I can plug my development environment in basically wherever I go and have very little problems. I didn't have to install any proprietary drivers and everything except my pen and touchscreen work right out-of-the-box. Since I plan on using Windows when I need those features and SSDs make this a fast switching process, I have no problem with this arrangement. It gives me the added versatility of plugging the portable SSD into my desktop when I need to do more intensive builds or utilize my GPU. I could also plug it into a family member's machine in a pinch.

## Conclusion

I plan on providing an update to this in the future as I settle in to this new routine. I'd love to hear from you all about suggestions on making this better or other options that I over-looked!