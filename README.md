# k3s Homelab

Configs and documentation for my homelab's k3s cluster

## Why would you run k8s at home?

- I had a hosted "lab" in digital ocean. It was expensive. I have lots of compute sitting around at home so thought I'd set a cluster up from scratch
- I'm interested in gitops and creating a fully IaaC powered environment; Ideally I could redeploy my homelabe with nothing more than a few bare vms and deploy commands.
- I want to spend more time in kubernetes and build my skills in deploying self-healing and resilient application infrastructure.

## What does your current setup look like?

Current hosts are as follows:

| Host Name                 | Description                         |
| ------------------------- | ----------------------------------- |
| k8s-lbs-01.machon.local   | nginx load balancer for api servers |
| k8s-cntl-01.machon.local  | k8s control plane / api server 1    |
| k8s-cntl-02.machon.local  | k8s control plane / api server 2    |
| k8s-wrkr-01.machon.local  | k8s worker node server 1            |
| k8s-wrkr-02.machon.local  | k8s worker node server 2            |

This setup allows for a good chunk bit resiliency; ideally however I would have a fully redundant load balancer in front of my k8s api servers / control planes. 
Most of these nodes are split across different machines. Some run on bare metal x86 hosts and others are run via vm's on my unraid nas.
