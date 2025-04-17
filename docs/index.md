# Micro Data Center Community

## What is a micro datacenter?

This is largely [Rob Gil's](https://github.com/robgil/microdatacenter) opinion if you're looking for someone to blame, but for the purposes of this project, we'll define it as the following.

> A micro datacenter is a fully functioning, ultra low power, and distributed datacenter. It contains all the functionality of a real datacenter, but small enough that you can run it off a 20A 110V outlet.

Also

> it's bare metal...

Why do I need a datacenter?

As more and more services increase their costs, build walled gardens of content, and exploit our information for profit, many are looking to move to an alternative they can trust, themselves. It isn't necessarily easy to know how to do this in a time and cost efficient manner, especially in an eco-friendly matter. But it does gain you a lot of freedoms. For many of us, it is even fun!

- Privacy and the ability to migrate off of large centralized services to minimize your footprint in surveillance capitalism.
- Lower chatty traffic between the devices on your network and them phoning home.
- Lower your monthly subscription spend.
- Own your digital content.
- Run services to support your own business.
- Small business networking.
- Run AI on your data without training someone else's.


Sure, but what is the maintenance cost? What if I have a power outage or a hardware mailfunction?

This is where having a community is valuable that goes beyond just sharing some quick tips on installation, but also shares design and strategy to mitigate issues like data loss and down time without dedicating yourself to a life of on call duty. When you inevitibly do face an outage, you have a lot of folks hanging around who have experienced much of the same, so they can help dig you out while you're in panic mode, and then cover how to avoid that same issue moving forward. 

Many of us starting this community have experience with how large corporations ensure that consumers rarely experience downtime and fortunately for you, they layed a bunch of us off, so we are ready to share this wisdom with many of you! Who knows, as we grow and develop intertwining systems as a community, we may be able to build networks akin to the [ipfs](https://en.wikipedia.org/wiki/InterPlanetary_File_System) that use trusted freinds to hold copies of your data if something goes terribly wrong. 

Why a microdatacenter?

Most folks, myself included, have always run some form of lab at home. This comes with a host of challenges and annoyances.
- Enormous power requirements for anything more than 1/2 a rack of servers
- Expensive, power hungry servers
- Old servers that are out of support, clunky, expensive to fix and upgrade, etc
- Overloading those servers with VMs
- Many folks run VMWare ESX, but that can be pricey
- Upgrades? What's that? 
  - Who actually has the funds to regularly ugprade their lab?

## Upcoming developements

This site is under heavy development, but first, why yet another homelab/selfhosted community?

Our goal is to do a better job at consolidating the tutorials, mental models, and language in the amazing and existing communities ([r/homelab](https://www.reddit.com/r/homelab/), [r/minilab](https://www.reddit.com/r/minilab/), [r/selfhosted](https://www.reddit.com/r/selfhosted/), [r/HomeServer](https://www.reddit.com/r/HomeServer/), [openminilabs](https://github.com/Wakoma/openminilab), [mini-rack](https://github.com/geerlingguy/mini-rack), [r/HomeNetworking](https://www.reddit.com/r/HomeNetworking/)) index those communities, and serve as the most ideal way to get started in this potentially large and complicated space of hosting your own services.

Some nearterm goals:

1. Simplify the existing "single" design into a getting started design that showcases a relatively cheap and affordable build, but starts to modularize the focus of various guides that build on the simple getting started guide.
1. Break out guides into different taxonomies (Hardware:Motherboard/Memory/Disk/CPU/GPUs/TPUs/Thermal/Network/Power/Disks/Rack/etc.., Ops:VMs/Containers/Managers/Hypervisor/Configuration/KVM/Netboot/etc.., Software:Storage/Git/Forejo/Certbot/ Personal Software: Nextcloud/Immich/Monero/)
1. Create a Recommendations index for technologies, people, and other stuff to watch and over time provide the ability for community driven benchmarks or showcases.
1. Build out a Discord Forum to discuss topics in a more managed way as oppossed to the Reddit design.
1. Recycle guides - initially, these guides focus on small, quiet, energy efficient builds using smaller micro servers like Raspberry Pi. This is not only pragmatic from a cost and energy savings, but supports smaller chip and dev board manufactures (especially built on open instruction sets like RISC-V). However, there is another consideration as we transition to a smaller interconnected network of nodes, and that is what do we do with servers that will inevitibly start spinning down and heading towards the landfill for children in Ghana to dissassemble? Well, we will also talk about standard homelab transformation of the most common larger systems. Although these won't be energy efficient, we as a community can also look into ways of opitmizing the most power hungry boards to something a bit closer to enable their reuse. When boards are at their end of life, we can also start to look at distributed recycling guides.

Some longterm goals:

1. Compile and provide guides on basic and intermediate Linux commands so that anyone, not just software engineers, can self-educate on the necessary understanding of systems administration.
1. Compile and provide guides on computer, network, nad security basics so that anyone hosting their services can avoid the most common pitfalls in their security model.
