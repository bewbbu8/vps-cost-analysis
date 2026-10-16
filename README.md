# affordable vps: what $1–$5 plans really cost over two years, and which one fits your workload

An affordable VPS in 2026 starts at roughly a dollar a month — but only if you're willing to pay by the year. The cheapest legitimate KVM plan the recent benchmark roundups found is RackNerd's 1GB annual promo, listed at **$11.49/year** with 2.5TB of traffic included. Everything above that floor is a negotiation: more CPU headroom, more locations, or a support team you can actually phone, each at a different price.

The catch is that sticker prices are intro rates. Hostinger's $4.99/month plan renews at $11.99. IONOS's $2 teaser expires after three months. Where "cheap" really gets decided is month thirteen, and most roundup articles mention the renewal clause once and move on. This article does the opposite: real two-year math first, then the specs, then a decision.

> **Quick verdict**
> - Just need a cheap always-on box (Wireguard, Pi-hole, a small bot, a low-traffic site)? RackNerd's annual KVM 1GB deal at about **$11.49/year**, with the promo price locked at renewal — 👉 [check RackNerd's current annual promo lineup](https://bit.ly/my-rn)
> - Need sustained CPU for a production app? Hetzner's CX22 (2 vCPU, 4GB RAM, 40GB NVMe, 20TB egress) from about €3.29/month in European datacenters.
> - Want a big-name provider at the lowest entry price? IONOS starts at $2/month with a 99.99% availability claim and a 30-day money-back window.
> - Prefer someone else to run the server? Ultahost's Basic plan is fully managed at $4.80/month with no renewal increase.

## What an affordable VPS actually gets you now

At the $1–$5 mark in 2026, a decent plan means KVM virtualization, NVMe storage, 1–2 vCPUs, and 1–4GB of RAM. That's the new baseline, and it's worth appreciating how recently it appeared: a $4/month machine today runs Nginx, a small PostgreSQL database, and a couple of Docker containers without complaint. Three years ago, that setup sat on a $20/month plan. Two things pushed the floor down — NVMe storage becoming standard at the budget tier, and AMD EPYC processors displacing older Intel chips in European datacenters while providers competed on specs.

Two vetting rules apply before you look at any specific deal. First, buy KVM only. OpenVZ-only plans can't run modern Docker, can't load custom kernels, and tend to oversell resources hardest. Reputable budget providers have mostly moved to KVM, so OpenVZ in 2026 is a red flag rather than a discount. Second, above roughly $3/month, NVMe should be standard — and it's worth checking whether that NVMe sits on a shared storage pool or is local to your instance, since local NVMe delivers noticeably lower latency for I/O-heavy work.

## The real cost: what you'll pay in year two

The monthly number on the checkout page is usually a 12–24 month intro rate, and several big names double it at renewal. Here's the math worked out, because this is the part most comparisons skip:

| Plan | First-year cost | Second-year cost |
| --- | --- | --- |
| RackNerd KVM 1GB (annual promo) | $11.49 | $11.49 (price-locked) |
| Hostinger KVM 1 (24-month term) | $119.76 (two years at intro) | $143.88 |
| IONOS VPS S+ (1-year term) | $60 (3 mo × $2, then 9 mo × $6) | $72 |
| InterServer slice | $72 | $72 ($6 guaranteed) |
| Ultahost Basic (managed) | $57.60 | $57.60 |

Look at the Hostinger row for a moment. The entry price is genuinely good — 4GB of RAM and 50GB NVMe for $4.99 on a two-year term is the best RAM-to-price ratio anyone tested at this level. But the renewal jumps to $11.99/month, one of the steepest gaps in the market. Meanwhile RackNerd price-locks its promotional purchases, a behavior one roundup verified across multiple annual renewal cycles. The entire first year of that RackNerd box costs about the same as a single month of Hostinger's renewal price. That's what a renewal clause is worth.

Add-ons are the second quiet cost. IONOS's own pricing page lists extra IPv4 addresses at $5/month each, Plesk at $6/month, and cloud backup from $0.065/GB/month — so a "$2" plan can realistically run $8 once you add a control panel, a dedicated IP, and automated backups. The same check applies at every provider: panel licenses and backup add-ons are the usual culprits. Price the full stack you actually need before comparing plans.

## RackNerd's budget deal, in detail

RackNerd's headline offer is the KVM 1GB annual promo — about **$11.49/year, roughly $0.96/month** — which makes it the cheapest legitimate KVM VPS the current roundups found. Budget promos like this drift a few cents between deal cycles (recent tests listed the tier between about $0.94 and $0.96 monthly), so treat the exact figure as a moving target that has stayed under $1/month.

| Plan | vCPU / RAM | Storage | Egress | Billing | Get it |
| --- | --- | --- | --- | --- | --- |
| KVM 1GB promo | 1 / 1 GB | 17 GB SSD | 2.5 TB | ~$11.49/yr (≈$0.96/mo) | [RackNerd annual deal](https://bit.ly/my-rn) |

Beyond the specs, you get KVM virtualization, 21 datacenter locations to choose from, and a renewal price that stays put. RackNerd's position in the market is straightforward: absolute lowest cost, US-hosted, no frills.

Now the honest part. In an independent 30-day test window, this tier posted 540 sysbench events per second, around 6,000 random 4K read IOPS, and 99.92% uptime. For context, Hetzner's CX22 — at roughly five times the price — posted about 41,000 IOPS and 1,090 events/sec in the same battery. Storage here is SSD rather than NVMe, which is partly how the price stays where it is. CPU is shared aggressively at this tier, and the roundups say so plainly.

That tradeoff is fine if your workload matches the box. Where it works well:

- Ad-blocking DNS (Pi-hole) for a household
- A Wireguard exit node
- A remote Plex setup
- Small bots, cron jobs, status pages
- A personal site with real but modest traffic

Where it doesn't: busy databases, video encoding, compile jobs, or anything where a latency spike costs you money. If that list describes your week, the cheap plan stops being cheap the first time you fight it. If the first list describes your week, the value is hard to argue with — 👉 [see RackNerd's current promo pricing and locations](https://bit.ly/my-rn).

## How the low end lines up

At the bottom of the market, providers differ most in CPU honesty, egress allowance, and locations — the sticker prices are all within a few dollars. The full picture, using tested plans and current published specs:

| Provider / plan | Price | vCPU / RAM | Storage | Egress | Standout |
| --- | --- | --- | --- | --- | --- |
| RackNerd KVM 1GB | $11.49/yr | 1 / 1 GB | 17 GB SSD | 2.5 TB | Cheapest legit KVM; locked renewals |
| Hetzner CX22 | €3.29/mo EU (~$3.60); US higher | 2 / 4 GB | 40 GB NVMe | 20 TB | Best sustained CPU per dollar; ID verification can take a day |
| IONOS VPS S+ | $2/mo for 3 mo, then $6 | 1 vCore / 2 GB | 60 GB NVMe | Unlimited (1 Gbps) | 99.99% availability; US/UK/DE/ES datacenters |
| Vultr Cloud Compute IPv6 | $2.50 | 1 / 512 MB | 10 GB NVMe | 500 GB | 32 regions; no IPv4 included |
| DigitalOcean Basic | $4 | 1 / 512 MB | 10 GB NVMe | 500 GB, then $0.01/GB | Best docs and API; 512MB runs tight |
| OVHcloud Starter | $3.50 | 1 / 2 GB | 20 GB NVMe | Unmetered 250 Mbps | Free DDoS protection; strong EU/Canada fit |
| Contabo VPS S | $6.50 (annual terms dip lower) | 4 / 8 GB | 50 GB NVMe | 32 TB | Most RAM per dollar; audible CPU contention at peak |
| BandwagonHost KVM Lite | $4.99 | 1 / 1 GB | 20 GB NVMe | 1 TB | CN2 GIA routing, best Beijing latency of the tested Western providers |
| InterServer slice | $6 | 1 / 2 GB | 30 GB SSD | 2 TB | Price guaranteed for life; slices stack linearly |

A few notes the table can't carry. Contabo's 8GB-for-the-price-of-everyone-else's-2GB is real, and a VPSBenchmarks head-to-head against Hetzner documented the catch: Contabo's six listed vCPUs share physical cores with more neighbors, so under sustained CPU load, Hetzner users often see faster actual throughput with fewer listed cores. Memory-hungry workloads — databases, large caches — can exploit Contabo's RAM honestly; CPU-bound ones should trust benchmarks over spec sheets. DigitalOcean's $4 droplet actually posted the highest sysbench score among the cheap set (1,180 events/sec), but 512MB of RAM is real-world too small for most things, and egress past 500GB bills at $0.01/GB. And if your users are in China, BandwagonHost occupies a niche nobody else at this price touches: CN2 GIA routes that beat every Western provider tested on Beijing latency.

## Which affordable VPS should you actually buy?

Match the plan to the workload — the cheapest plan that runs your stuff without fighting you is the affordable one. Some concrete rules from the verified data:

- **Background services and personal projects** → RackNerd's annual KVM promo. Year two costs the same as year one, which no intro-priced big name can say. 👉 [lock in RackNerd's annual KVM deal](https://bit.ly/my-rn)
- **A production web app with real CPU spikes** → Hetzner CX22, or IONOS VPS M+ ($5 intro, $14 after, 2 vCores / 4GB / 120GB NVMe) if you want US/UK/Germany/Spain locations and a 30-day money-back window.
- **Traffic-heavy serving** → Hetzner's 20TB or OVHcloud's unmetered 250Mbps. Think twice about 500GB-capped plans with per-GB overage.
- **Serving China traffic** → BandwagonHost's CN2 GIA plans.
- **Want managed hosting under $5** → Ultahost Basic at $4.80 with management included, or Hostinger if the AI-assisted panel appeals (budget for the renewal).
- **IPv6-only micro workers across many regions** → Vultr's $2.50 plan, if you can live without an IPv4 address.

And a short vetting checklist that applies to any provider not listed here: KVM only, NVMe above $3/month, benchmark evidence before believing a vCPU count, and overage rates read before ordering.

## FAQ

**Is a sub-$1/month VPS real, or a scam?**
Real, with conditions. RackNerd's KVM 1GB annual promo has been benchmarked at about $11.49/year on genuine KVM virtualization, and the renewal price stays locked across cycles. The compromises are shared CPU and oversold IOPS, which is exactly why it suits lightweight always-on services rather than production workloads.

**What can I actually run on 1GB of RAM?**
A Wireguard node, Pi-hole, a small bot, a status page, a lightweight personal site. A busy database or a growing Docker stack is pushing it — even DigitalOcean's $4 droplet with 512MB was flagged as real-world too small in testing. If containers are the plan, aim for 2–4GB, which puts you in IONOS VPS S+ or Hetzner CX22 territory.

**Do cheap VPS plans get more expensive at renewal?**
Many do. Hostinger's entry plan goes from $4.99 to $11.99/month. IONOS's promo months expire — VPS S+ moves from $2 to $6 after three months. Holding their price: RackNerd's promos (locked), Contabo, InterServer ($6 for life), and Ultahost's Basic plan.

**KVM or OpenVZ — does it still matter?**
Yes. OpenVZ-only plans can't run modern Docker, can't load custom kernels, and oversell hardest. KVM is the default at reputable budget providers now, so treat OpenVZ as a reason to walk away.

**How much bandwidth do I need?**
Personal services fit comfortably inside RackNerd's 2.5TB. Serving files, media, or app traffic at any scale changes the math — Hetzner's 20TB or OVHcloud's unmetered 250Mbps suddenly matter more than a $1 price difference, and DigitalOcean's $0.01/GB past 500GB adds up faster than its sticker suggests.

## Before you order

Two things to confirm at checkout, whatever you buy. First, location: RackNerd has 21 to choose from, and picking the one nearest your users costs nothing extra. Second, billing term — the headline prices on budget promos assume annual billing, so make sure the term in the cart matches the price in your head.

If your checklist ends with "cheap, KVM, locked renewal, don't need benchmark-grade CPU," the $11.49/year RackNerd deal is the easiest call in the budget VPS market right now. 👉 [check RackNerd's current annual pricing and location list](https://bit.ly/my-rn) before ordering, since promo figures drift slightly between cycles.
