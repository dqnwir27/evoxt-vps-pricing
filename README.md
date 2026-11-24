# Cheap High Performance VPS: How Much Does Evoxt Cost, Which Plan Fits a WordPress Site or Discord Bot, and Where the 40% Code Stops Working (Full Plan Table)

Evoxt's VM-1 comes to about **$3.59/month** with its 40% recurring code: 1 core, 2 GB RAM, 20 GB storage, 1 TB of transfer, and weekly offsite backups included. That is the plan most people searching for a cheap high performance VPS actually end up wanting. The $2.99 headline on the site belongs to a smaller box (VM-0.5, 512 MB RAM), and that plan does not accept the percentage discount at all.

What follows is the full 11-plan price table from Evoxt's pricing page, the one upgrade step in it that costs almost nothing, what the "6.0 GHz" figure really means, and how to choose between the standard and premium regions before you pay.

> **Quick pick:** VM-1 with a 40% recurring code, roughly **$3.59/mo**, for a single WordPress site, a database-backed app, a Discord bot, or a small Minecraft server. If you expect to be short on CPU rather than RAM, VM-1.5 is $0.96 more at list price (about $0.58 after the code) and doubles the core count.
>
> 👉 [Check the current Evoxt plan lineup and deploy VM-1](https://bit.ly/EvoXt)

## All Evoxt plans, side by side

Prices below are monthly list prices from Evoxt's own pricing page. The discounted column is simple arithmetic at 40% off, not a quoted figure, so treat it as an estimate until the code validates at checkout.

| Plan | vCPU / RAM / Storage | Monthly transfer | List price | With 40% code* | Order |
| --- | --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB / 5 GB | 500 GB | $2.99 | not eligible | [Order](https://bit.ly/EvoXt) |
| VM-0.75 | 1 core / 1 GB / 10 GB | 750 GB | $4.99 | not eligible | [Order](https://bit.ly/EvoXt) |
| VM-1 | 1 core / 2 GB / 20 GB | 1,000 GB | $5.99 | ~$3.59 | [Order](https://bit.ly/EvoXt) |
| VM-1.5 | 2 cores / 2 GB / 20 GB | 1,500 GB | $6.95 | ~$4.17 | [Order](https://bit.ly/EvoXt) |
| VM-2 | 2 cores / 4 GB / 30 GB | 2,000 GB | $11.99 | ~$7.19 | [Order](https://bit.ly/EvoXt) |
| VM-3 | 4 cores / 4 GB / 30 GB | 3,000 GB | $14.99 | ~$8.99 | [Order](https://bit.ly/EvoXt) |
| VM-4 | 4 cores / 8 GB / 60 GB | 4,000 GB | $23.99 | ~$14.39 | [Order](https://bit.ly/EvoXt) |
| VM-6 | 8 cores / 8 GB / 60 GB | 5,000 GB | $29.99 | ~$17.99 | [Order](https://bit.ly/EvoXt) |
| VM-8 | 8 cores / 16 GB / 80 GB | 6,000 GB | $47.99 | ~$28.79 | [Order](https://bit.ly/EvoXt) |
| VM-12 | 16 cores / 16 GB / 80 GB | 8,000 GB | $60.95 | ~$36.57 | [Order](https://bit.ly/EvoXt) |
| VM-16 | 16 cores / 32 GB / 100 GB | 10 TB | $95.99 | ~$57.59 | [Order](https://bit.ly/EvoXt) |

\*Every plan on the page is listed with the same "up to 6.0 GHz" CPU ceiling. Billing runs monthly up to a 3-year prepay, and account credits can be topped up and applied to future invoices.

Individual resources can be added without switching plans, and an extra IPv4 address is $3/month.

## The cheapest upgrade in the table, and why most people miss it

Look at VM-1 and VM-1.5 next to each other. For **$0.96 more per month** you get a second core and 500 GB more transfer, with RAM and storage unchanged. At the discounted rate that gap is roughly 58 cents.

The same pattern repeats further up. VM-2 to VM-3 adds two cores for $3.00 and keeps 4 GB of RAM. VM-4 to VM-6 adds four cores for $6.00 and keeps 8 GB. Stepping up in cores alone is cheap on this pricing page. Stepping up in RAM is not: VM-2 to VM-4 doubles both cores and memory and adds $12.00.

That gives you a usable rule. If your bottleneck is CPU queueing (PHP workers backing up, bot commands lagging, cron jobs colliding), take the core-heavy step at the same RAM level. If your bottleneck is memory (MySQL buffer pool, too many PHP-FPM children, a Java server), you have to pay for the RAM step and the cores come along for the ride.

## "6.0 GHz" is a turbo figure, and the base clock is the number that matters more

Evoxt's pricing page advertises "up to 6.0 GHz" CPU frequency. In its own description to VPSBenchmarks, the company phrases it as CPUs running "at least 3.5 GHz and above." Read together, that means a base clock of 3.5 GHz or better, with 6.0 GHz as a turbo peak on bursts. No provider guarantees a sustained turbo clock on shared hardware, and Evoxt does not publish one.

Why care about the distinction at all? Because a large share of cheap VPS workloads are effectively single-threaded. A WordPress page render, a MySQL query that cannot be parallelized, a Discord bot event loop, Minecraft's main tick loop: each of these mostly waits on one fast core rather than spreading across eight slow ones. Mainstream cloud instances from the large providers sit in the 2.2–2.4 GHz range according to a review page tracking Evoxt's positioning, so a 3.5 GHz-plus base is a real step up for that kind of work.

Storage is the other half of the performance question, and here you should ask before assuming. Published comparisons put SATA/SAS SSD tiers at roughly 550 MB/s ceiling, while NVMe over PCIe reaches 3,000–7,500 MB/s with far higher IOPS. Evoxt's pricing page lists storage capacity only, without naming the media type. If database I/O is why you are shopping, confirm the storage type with support before you order rather than trusting a review that says NVMe.

## Promo codes: three limits that decide whether you get the discount

Three codes circulate for Evoxt, all described as **40% recurring** (applied to every billing cycle, not just the first invoice): `EVOXT595`, `AFF1129-hostspot`, and `BHW595`. All three are documented as valid on VM-1 and above.

Three restrictions matter more than the code itself:

1. **One code per order.** You cannot stack two of them.
2. **VM-1 is the floor.** VM-0.5 at $2.99 and VM-0.75 at $4.99 do not qualify, so the "$2.99 with 40% off" combination people imagine does not exist.
3. **You must click Validate.** On the checkout page, paste the code into the "Promotional Code" field and hit Validate. The discount is applied to the total only after that step succeeds.

The last public verification date I can find for these codes is early 2026, which is a long way from today. Validate before paying, and if one code fails, try the next.

What the discount is worth in real money: VM-1 at list price runs $71.88 for twelve months. At $3.59 it runs about $43.08, a saving near $28.80 in year one. Because the discount is recurring, year two starts from the same $3.59 rather than snapping back to $5.99.

👉 [Open the Evoxt checkout and validate a 40% code on VM-1](https://bit.ly/EvoXt)

## Standard or premium region: the choice changes your bandwidth budget

Evoxt divides locations into standard and premium groups. The standard group (US, UK, Canada, EU, Tokyo, Malaysia, Australia) gets more generous transfer allowances. The premium group (Hong Kong, Osaka, Malaysia Premium) gets slightly less transfer but optimized routing, which is the point if your users are in Asia.

The pricing page makes the cost of that difference explicit through additional transfer pricing: **$3/TB on Standard, $12/TB on Premium, $24/TB on Premium Plus**. If you are pushing several terabytes a month, running that in a premium location costs four to eight times more per extra terabyte than in a standard one. Bandwidth-heavy projects belong in standard regions; latency-sensitive projects belong where the routing is good.

For China-facing traffic, a review page states the Hong Kong node routes over CN2, which would be a meaningful advantage over a US-west box for mainland visitors. For Southeast Asia, the Malaysia, Indonesia, and Hong Kong nodes connect to local internet exchanges (MyIX, JKT-IX) and peer directly with local ISPs, Cloudflare, and Google. Both claims come from a third-party review rather than Evoxt's own documentation, so if CN2 routing is your entire reason for picking Hong Kong, ask support to confirm it for the specific plan you are buying.

VPSBenchmarks counts 18 data centers across 4 continents, spanning Los Angeles, New York, Montreal, London, Paris, Amsterdam, Frankfurt, Warsaw, Zurich, Kuala Lumpur, Jakarta, Sydney, Hong Kong, Seoul, Osaka, and Tokyo.

## What every plan includes, regardless of size

Weekly offsite backups run automatically on every VM and are free by default, which is genuinely uncommon at this price level. Also standard across the range: dashboard firewall rules, VNC console access, private IPs between your own VMs, server cloning, sub-accounts with separate permission levels, API access, and 1-click application templates including WordPress with LiteSpeed, Docker, and Nextcloud. You can run Linux or Windows.

Payment methods include credit cards, PayPal, and cryptocurrency (Bitcoin, Litecoin, Ethereum, USDT). VPSBenchmarks notes there is no hourly billing and no DDoS protection, both worth knowing before you sign up rather than after.

## Who should not buy Evoxt

**Heavy parallel workloads.** Video encoding farms, large CI runners, parallel ML jobs. VM-12 and VM-16 exist with 16 cores, but if you genuinely need dozens of dedicated cores, shared high-clock vCPUs are the wrong shape and you should be pricing dedicated servers instead.

**Production systems with a sub-hour support SLA.** Reviewers consistently praise server performance and call the control panel clean and intuitive, while flagging billing-related tickets (subscriptions, transfer questions) as slow to answer. A service that needs a 15-minute response guarantee should not be built here.

**Anyone who needs DDoS protection, hourly billing, or reverse DNS.** None of those are offered, per VPSBenchmarks' feature audit. No refund terms or free trial are published on the pricing page either; one affiliate guide claims a 24-hour refund window, but I could not confirm that on Evoxt's own pages, so treat it as unverified and ask before paying.

For context on where $3.59 lands: a 2026 vendor comparison puts performance-tier VPS plans typically in the **$5–24/month** range, with Hetzner around $5–15, Vultr and DigitalOcean around $6–24, Linode around $5–24, and OVHcloud around $6–20. Those are approximate starting points that shift with region, billing term, and promotions.

## The final call

Match the plan to the job rather than to the price tag:

- **One site, one bot, one small game server, or a staging box** → VM-1 at ~$3.59. Start here; upgrade later if load demands it.
- **CPU-bound but memory-light** (multiple PHP workers, a busy bot, compile jobs) → VM-1.5 at ~$4.17, or VM-3 at ~$8.99 once 4 GB is enough.
- **Two to four sites plus a real database** → VM-2 at ~$7.19, moving to VM-4 at ~$14.39 when 4 GB stops being enough.
- **Dozens of small sites or a memory-hungry Java workload** → VM-8 and up.
- **Parallel rendering, CI, or anything needing dedicated cores** → look at dedicated servers, not this table.

Two things to confirm at checkout before you pay: that the promo code validates and shows the recurring 40%, and which region tier your chosen location belongs to, since that sets your transfer ceiling and the price of extra bandwidth.

👉 [Deploy an Evoxt VPS and apply the 40% recurring code at checkout](https://bit.ly/EvoXt)
