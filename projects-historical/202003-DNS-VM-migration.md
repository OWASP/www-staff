---

title: DNS and VM Migration
layout: full-width

---

# DNS and VM Migration

## Overview

The DNS, name provider, and virtual machine infrastructure currently resides on several different platforms.  In addition, the website redirection currently is at an elevated risk due to a single point of failure.  In order to consolidate our platforms and mitigate the risk, the VM infrastructure will be moved to DigitalOcean, the name provider will shift to Namecheap, and the DNS and redirect infrastructure will be moved to Cloudflare.


## Goals

1. Consolidate DNS infrastructure into a single provider as well as Domain Name Provider into a single provider
2. Migrate and consolidate VM infrastructure into one provider
3. Mitigate single source of failure and improve web performance (load times) by 3%

## Milestones

* [x] 2020-03-16, map all DNS and VM data, [Matt Tesauro]
* [x] 2020-03-20, initial single, low-importance domain moved to Cloudflare and tested, [Matt Tesauro] 
* [x] 2020-03-24, use Cloudflare as DNS provider for all domains (transfer from Rackspace), [Matt Tesauro]
* [x] 2020-03-27, use Cloudflare as CDN for owasp.org and implement redirects, [Matt Tesauro, John Morabito]
* [x] 2020-04-03, move VMs not in DigitalOcean to DigitalOcean


## Leadership

* [Harold Blankenship](mailto:harold.blankenship@owasp.com?subject=DNS%20and%20VM%20Migration)
