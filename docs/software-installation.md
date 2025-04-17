# Software Installation and Configuration

## Server Management and Imaging
[Tinkerbell](https://tinkerbell.org/) is an automated DHCP, NETBOOT, and PXE physical host provisioning service. To keep costs down, you can run this on your desktop in VMs initially. You can also run it on some of your nodes if you have a multi purpose node (something like a shared DHCP, DNS, Tinkerbell, image store, etc)

## Routing
[FRRouting](https://frrouting.org/) is an Open Source routing stack. This is the stack I would recommend for any home lab. This can be run on any linux host and is substantially cheaper than buying or re-using some purpose build switch or router. The goal of this project is to learn the internals, so running FRR is a good way to familiarize yourself with networking protocols. 

As we delve in to more detail, FRR becoming increasingly important to learn cloud networking concepts. I'm not talking about simple concepts like IGWs or VPC Route Tables. I mean the underpinning of VPCs in general. In a later article, I'll describe how you can create your own VPC networking with eVPN and VXLAN using FRRouting. This is the basis for undestanding multi tenant network architecture (hint, it's all encapsulated in the datacenter). 

### Public IP Space 
So you want to learn IPv6? Well, you could get your own ASN and IP space for about $1000.
- ASN: 500$
- /36 IPv6: 500$

_/36 is the smallest ARIN will allocate at the time of writing_

Seems a little steep for most home SREs. But imagine all the money you'll save in not buying rackmount servers or powering them. 

With the routing setup and OpenSwitch, you can advertise your IP space through a provider like Equinix Metal (ask me how I know). You'll be able to have your own publicly routable IPv6 space. You can also use AWS BYOIP and [TransitGateway Connect](https://aws.amazon.com/about-aws/whats-new/2020/12/introducing-aws-transit-gateway-connect-to-simplify-sd-wan-branch-connectivity/)

If you're more adventurous, have a bottomless wallet, or already have IPv4 space, you can do that too. 

### Accessing Your Microdatacenter (no static addressing from your home ISP)
You can use either wireguard or IPSec up to an Equinix Metal host or to AWS (or any other provider that can handle BGP)

## Elastic IPs
Elastic IPs, which you may be familar with from AWS. What this really is is just a public IP that is NAT'd to an ENI/Private IP. How do you achieve this in your microdatacenter? We don't have fancy network cards that offload this, so in order to do this, it's as simple as running BGP on every node. 

For kubernetes workloads, we'll use Cilium to advertise the public IP (Elastic IP) via BGP to the core network and out to the internet (if you're doing public peering)


## Firewall
Firewalls we'll keep simple to understand them. No, we're not going to use PFSense for these exercises. We'll do it the hard way for the purposes of learning. 

nftables, bpfilter, iptables, etc

## k8s
Kubernetes has always been a bit of a struggle in home labs. It's annoying running every service and having enough infrastructure to do so. The balance I've found is utilizing [k3s](https://k3s.io/)

This has support for things like Cilium, which ties in nicely to the routing stack. 

## Distributed Storage
How do you do persistent storage? What can you use for shared storage and object stores? 

[minio](https://min.io/) is the simplest to manage and utilize. It has an S3 like API and is a lot less work than other tools like GlusterFS and Ceph. 
