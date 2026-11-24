# Japan VPS Hosting: How Fast Is Tokyo, How Much Transfer Do You Need, and Which Plan Is Enough? (Full Plan Table)

Evoxt sells a Tokyo virtual machine from **$2.99/month**, and it charges the same rate for Japan as it does for its US and UK locations. The **$5.99 VM-1** (1 core, 2 GB RAM, 20 GB disk, 1 TB transfer) is the plan most people searching for Japan VPS hosting should look at first.

Tokyo is worth the trouble because of where it sits on the map. Latency tables published on Tokyo VPS product pages typically show Seoul under 30 ms, Shanghai under 50 ms, Hong Kong under 55 ms and Singapore under 75 ms, with the US west coast at roughly 100–120 ms. One box in Tokyo covers Japan, Korea, Taiwan and the coastal Chinese market without a second deployment.

What follows is the full Evoxt price list, how its transfer allowance actually behaves when you exceed it, what the offer leaves out, and the one question no provider's sales page will answer for you: whether the IP address you receive is treated as Japanese by the services you care about.

## The quick version

> **Most readers:** VM-1 at **$5.99/month**. 1 core, 2 GB RAM, 20 GB disk, 1 TB monthly transfer. Enough for a small site, a Discord or Telegram bot, an API backend, or a WireGuard server for a handful of people.
>
> **Testing or a static page:** VM-0.5 at **$2.99/month** (512 MB, 5 GB disk, 500 GB transfer). Cheap enough to use as a throwaway.
>
> **Containers, a database, or a few client sites:** VM-2 at **$11.99/month** gives you 2 cores, 4 GB RAM, 30 GB disk and 2 TB transfer.

👉 [Deploy the VM-1 in Tokyo for $5.99/month](https://bit.ly/EvoXt)

## All Evoxt plans, Tokyo pricing

Every plan below is available in Tokyo at the price shown. All cores are listed as "up to 6.0 GHz", every plan includes weekly backups, and billing runs monthly up to three years.

| Plan | vCPU / RAM | Disk | Monthly transfer | Price (USD/month) | Order |
| --- | --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB | 5 GB | 500 GB | $2.99 | [ Deploy VM-0.5](https://bit.ly/EvoXt) |
| VM-0.75 | 1 core / 1 GB | 10 GB | 750 GB | $4.99 | [ Deploy VM-0.75](https://bit.ly/EvoXt) |
| VM-1 | 1 core / 2 GB | 20 GB | 1 TB | $5.99 | [ Deploy VM-1](https://bit.ly/EvoXt) |
| VM-1.5 | 2 cores / 2 GB | 20 GB | 1.5 TB | $6.95 | [ Deploy VM-1.5](https://bit.ly/EvoXt) |
| VM-2 | 2 cores / 4 GB | 30 GB | 2 TB | $11.99 | [ Deploy VM-2](https://bit.ly/EvoXt) |
| VM-3 | 4 cores / 4 GB | 30 GB | 3 TB | $14.99 | [ Deploy VM-3](https://bit.ly/EvoXt) |
| VM-4 | 4 cores / 8 GB | 60 GB | 4 TB | $23.99 | [ Deploy VM-4](https://bit.ly/EvoXt) |
| VM-6 | 8 cores / 8 GB | 60 GB | 5 TB | $29.99 | [ Deploy VM-6](https://bit.ly/EvoXt) |
| VM-8 | 8 cores / 16 GB | 80 GB | 6 TB | $47.99 | [ Deploy VM-8](https://bit.ly/EvoXt) |
| VM-12 | 16 cores / 16 GB | 80 GB | 8 TB | $60.95 | [ Deploy VM-12](https://bit.ly/EvoXt) |
| VM-16 | 16 cores / 32 GB | 100 GB | 10 TB | $95.99 | [ Deploy VM-16](https://bit.ly/EvoXt) |

The pricing page lists Tokyo alongside the US, UK, Canada, Germany, Poland, the Netherlands, Malaysia and Australia. Same plan names, same specs, same numbers.

## Evoxt doesn't charge a Japan premium

This is rarer than it sounds. Plenty of providers price Asian locations above their European ones, or keep the price and quietly halve the traffic allowance. Evoxt does the second thing in some regions — a community review write-up notes that its Hong Kong, Osaka and Malaysia Premium locations keep the same headline price but cut monthly transfer roughly in half.

Tokyo is not one of those. VM-1 in Tokyo gets the same 1 TB as VM-1 in Frankfurt, and matching third-party listings of the plan line-up show identical USD prices across Tokyo, the US, the UK and Malaysia.

That matters if you're choosing between Tokyo and Osaka. Osaka looks like the cheaper Japanese option until you notice the transfer difference, and for most workloads transfer is the constraint you hit first on a small box.

## Latency depends on the route, not the city

Tokyo's advantage comes from submarine cable landings and dense peering, not from being physically close to your users. The FASTER and PC-1 cables run from Japan to the Chinese mainland, and the Equinix Tokyo campus operates carrier-neutral peering with the major Japanese ISPs, which is what keeps traffic from detouring through Hong Kong or Singapore before it reaches a Japanese eyeball.

Evoxt doesn't publish its Tokyo upstream carriers or the port speed attached to each plan. That's a gap you can work around rather than a dealbreaker: run a traceroute and a ping test from the networks your users actually sit on during the first week, while you're still on monthly billing and can leave after one month without losing a prepaid year.

If your audience is mostly in Korea, a Seoul box will beat Tokyo. Taiwan and the Philippines are usually better served from Hong Kong, Southeast Asia from Singapore. Tokyo wins when Japan is the primary market or when you need one node for all of Northeast Asia.

## Transfer: allowance, then throttle

Evoxt's bandwidth model is an allowance followed by throttling. Each VM gets a monthly transfer figure, and once you pass it the connection slows rather than generating an overage invoice. VPSBenchmarks' host profile describes Evoxt as not charging for bandwidth, with a free allowance of about 2 TB/month on a 2-core, 4 GB instance.

If throttling isn't acceptable, extra transfer is sold separately at **$3/TB** on standard regions, $12/TB and $24/TB on the premium tiers. Tokyo sits in the standard tier, so $3/TB applies.

Compare the four models you'll run into while shopping, because they behave very differently under load:

- **Allowance then throttle** (Evoxt): your site slows, your bill doesn't move.
- **Unlimited at a port cap** (KernelHost's Tokyo Edge plans, from €23.99/month on a 2026-11-02 page): no data cap and no per-TB charge, with the uplink held to 1 Gbps.
- **Plan quota plus a shared pool** (EDIS Global's Tokyo plans at 1–4 TB each, plus a 100 GB starter credit that never expires, per its 2026-10-28 page): you can move unused traffic between machines.
- **Per-plan hard quota** (Unihost lists 30 TB/month per LVP-S plan, page dated 2025-05-23).
- **Inbound free, outbound metered** (HOSTKEY's Japan page, undated, sells traffic as a separate plan).

A 1 TB allowance on VM-1 is roughly 30 GB a day. A brochure site or an API will not come near it. Video, mirrors and large file distribution will.

## The Japanese IP question

Nobody's sales page settles this, so treat it as a pre-purchase check rather than an assumption.

Providers split on it. KernelHost states plainly that its IPv4 addresses come from the Tokyo data centre network but that geolocation databases decide country on their own, and it doesn't promise a specific result. Unihost, on a 2025 page, claims every plan includes a dedicated Japanese IP usable for Google.co.jp and domestic payment gateways. Those are two very different commitments.

This matters if you're hosting a Japanese storefront, registering with a payment processor that filters on IP country, or chasing Japanese-language search visibility. Before you migrate anything, open a ticket and ask what happens if the IP geolocates to the wrong country, and test the address you're assigned with an IP geolocation lookup and a looking glass before you point DNS at it.

One related detail from VPSBenchmarks' feature table: Evoxt does not offer reverse DNS. If you plan to run a mail server from the box, that's a blocker, not a nuisance.

## What's included, and what isn't

Included on every plan, per VPSBenchmarks' host profile and Evoxt's own pricing page: KVM isolation, IPv6 addresses, private networking between your VMs, an enterprise Layer 3 firewall with per-VM port rules, rescue mode, VNC access, a REST API, usage charts for CPU, bandwidth, RAM and storage, and weekly offsite backups at no extra cost.

Not included or not offered: DDoS protection (the profile lists none, which is unusual for this price bracket), hourly billing, reverse DNS, and a mainstream control panel — Evoxt runs its own console rather than cPanel or Plesk, so anything you'd normally do in WHM happens over SSH or through the API.

Two things worth knowing before you commit money. Evoxt was founded in 2020, so it has a shorter operational record than the decade-old names it competes with, and a review roundup cites support tickets stretching to 48 hours at peak times plus at least one publicly documented refund dispute. Neither is disqualifying at $5.99/month, but they're reasons not to prepay three years on day one. Start monthly, see how the box and the support behave, then extend.

Evoxt also hides the CPU model, which is an odd choice for a company that sells on clock speed. Its own stated position is that frequencies are at least 3.5 GHz, with the pricing page advertising up to 6.0 GHz.

👉 [See the current Tokyo plan list and deploy a VM-2](https://bit.ly/EvoXt)

## Growing without changing plans

You can add individual resources instead of jumping a tier: extra vCores at **$3/month each**, extra RAM at **$2/GB/month**, extra IPv4 addresses at **$3/month each**, and additional transfer at **$3/TB**. Upgrades are handled from the admin console and keep your existing installation.

That pricing changes the maths on the middle of the table. Going from VM-2 (2 cores, 4 GB) to VM-3 (4 cores, 4 GB) costs $3/month, which is exactly what two add-on cores cost. If you need RAM instead, VM-2 plus 4 GB of add-on RAM lands at $19.99 versus $23.99 for VM-4's 8 GB. Compare the add-on route against the next tier before you upgrade out of habit.

Billing is prepaid, monthly up to three years, and you can top up account credits and let the system apply them to future invoices. Payment methods listed are credit card, PayPal and Bitcoin.

## How the price compares with other Tokyo options

Published Tokyo pricing from other providers, for context:

- **EDIS Global** starts at €7.99/month for 1 GB RAM, 15 GB SSD and 1 TB traffic (page dated 2026-10-28).
- **KernelHost** starts at €23.99/month for its unlimited-traffic Tokyo line with a 1 Gbps uplink (page dated 2026-11-02).
- **Unihost** lists €22.35/month for 8 vCores, 24 GB RAM, 300 GB SSD and 30 TB traffic (page dated 2025-05-23, so treat the figure as dated).

Evoxt's VM-1 at $5.99 gives 2 GB RAM and 1 TB transfer, and VM-4 at $23.99 gives 4 cores, 8 GB RAM and 4 TB. Currency, VAT treatment and included features differ across all of these, so don't read the euro and dollar figures as a straight ranking. What the comparison does show is that Evoxt's entry price sits well below the European providers' Tokyo entry points, and its high-end plans are competitive rather than dominant.

Where the others have an edge: KernelHost and EDIS Global publish their Tokyo facility and network relationships; Evoxt doesn't. If you need documented upstream carriers for a procurement review, that's a real difference.

## Picking a plan

Static site, a blog, a small bot, a personal VPN for two or three devices: VM-0.5 or VM-0.75. The 512 MB plan runs a lean Linux install fine; it will not run a database and a web server comfortably.

One production site with modest traffic, an API backend, a game server for a small group: VM-1. This is the plan where the price-to-spec ratio sits best, and 1 TB is more transfer than most sites use in a month.

Multiple containers, a database you actually query, a handful of small client sites: VM-2 or VM-3, depending on whether you're short on RAM or cores. Add-on pricing means you can start at VM-2 and buy 4 GB of RAM for $8/month instead of stepping up a tier.

Three things to confirm before you pay: whether the IP you're assigned geolocates to Japan, what your throughput looks like after the monthly allowance is used up, and what the cancellation terms are if you prepay for a year or longer. The first two you can test inside a month of monthly billing.

👉 [Start with the $2.99 Tokyo VM and test the route yourself](https://bit.ly/EvoXt)
