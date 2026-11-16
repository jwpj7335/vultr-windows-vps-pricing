# Windows Virtual Server Hosting: What Vultr's $300 Credit Covers, Why the Windows License Bills Separately, and Which Plan Fits Your Workload (Full Price Table)

Vultr's Cloud Compute cards start at **$10/month** for 1 vCPU, 2 GB RAM and 55 GB of storage, but those numbers are the Linux price. A Windows image adds a license fee on top, and Vultr does not print that fee on the plan card; its own Windows page lists every version with a "(+ License Fee)" tag and states that "Windows license costs vary based on compute plan selection." Budget for the base price plus a license line you will only see at the deploy screen.

That single fact reshapes most of the shopping advice you will read about Windows virtual server hosting, because nearly every comparison table quotes the base price and stops there. Below: the full Cloud Compute price list, what the $300 credit is actually worth once the 30-day clock starts, how to size a box for RDP, .NET and SQL Server, and where Vultr sits against Contabo, OVHcloud, Atlantic.Net and Liquid Web on real cost.

> **Most readers should start with the 4 vCPU / 8 GB Cloud Compute plan at $40/month base plus the Windows license fee.** It runs one or two RDP sessions, a small .NET application and a light database without starving. Take the 2 vCPU / 4 GB at $20/month only if a single person connects and nothing heavy runs in the background. Go to 8 vCPU / 32 GB at $160/month when the database lives on the same box.
> 👉 [See the Windows image list and license terms on Vultr](https://www.vultr.com/servers/windows?ref=9738262-9J)

## Vultr Windows-capable plans and prices

These are the base compute prices from Vultr's Cloud Compute lines, billed hourly with a monthly cap. The Windows license is extra on every row. Vultr also sells High Frequency, Optimized (General Purpose, CPU, Memory, Storage) and Cloud GPU families; entry prices for those sit well above the Cloud Compute line and were not confirmable on Vultr's own pricing page during this review, so they are not in the table.

| Plan (vCPU / RAM / storage) | Monthly cap | Hourly (monthly ÷ 672) | Windows license | Deploy |
| --- | --- | --- | --- | --- |
| 1 vCPU / 2 GB / 55 GB SSD | $10 | $0.0149 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 2 vCPU / 2 GB / 65 GB SSD | $15 | $0.0223 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 2 vCPU / 4 GB / 80 GB SSD | $20 | $0.0298 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 4 vCPU / 8 GB / 160 GB SSD | $40 | $0.0595 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 6 vCPU / 16 GB / 320 GB SSD | $80 | $0.1190 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 8 vCPU / 32 GB / 640 GB SSD | $160 | $0.2381 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 16 vCPU / 64 GB / 1,280 GB SSD | $320 | $0.4762 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 24 vCPU / 96 GB / 1,600 GB SSD | $640 | $0.9524 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 4 vCPU / 8 GB / 180 GB NVMe (High Performance) | $48 | $0.0714 | + fee | [Deploy](https://www.vultr.com/servers/windows?ref=9738262-9J) |

Two things the table does not show. Bandwidth is metered per plan, not pooled: the 4 vCPU / 8 GB plan carries a 4,096 GB allowance. And the hourly figure is the monthly cap divided by 672 hours, which is the divisor Vultr's billing documentation uses; the public API reports a slightly lower hourly number because it divides by 730. Whichever figure you see, the monthly cap wins once an instance runs all month.

Images cover Windows Server 2016 through 2025 in Standard and Datacenter, Core or GUI, across 34 cloud data center regions. Vultr provisions the license for you and does not accept a license you already own, so there is no bring-your-own-Enterprise-Agreement route to cut the fee.

## Why Windows costs more than Linux, in numbers

Two independent providers quantify the premium, and they land in the same place.

Atlantic.Net publishes both columns side by side. Its G3.2GB plan (2 GB RAM, 1 vCPU, 50 GB, 3 TB) is $8.00/month on Linux and $15.50/month on Windows. At the larger end, M2.64GB is $200 on Linux and $397.50 on Windows. Same hardware, roughly **1.9 to 2 times the price** for the Windows image, and the company attributes the gap to Microsoft licensing.

Contabo frames it as a line item: it advertises "a Windows license for €4.99 a month" as the reason its Windows Server plans sit so close to its Linux plans. Its Windows Cloud VPS 4 (4 vCPU, 8 GB RAM, 100 GB SSD) lists at €4.40/month for the first 24 months against a €5.50 regular price.

Put those together and the practical rule is: whatever a Windows VPS costs, somewhere between a third and half of it can be operating system. That matters when you compare a $10 plan to a $15 plan, because the delta is often almost entirely license.

At Vultr the license amount is not published. A third-party analysis of its pricing estimates about **$16 per vCPU-month**, meaning roughly +$16/month on the $10 plan and +$128/month on the $160 plan. Treat that as an estimate to sanity-check your budget, not a quote. The authoritative number appears in the deploy flow for the specific plan you pick, and it is worth opening the deploy screen for two or three candidate sizes before you decide.

## What the $300 credit actually buys

The code is real and it is on Vultr's own coupons page: **FLY300VULTR** gives $300 in promotional credit to new customers. Three conditions decide whether it is useful to you.

1. **It expires 30 days after signup**, not 30 days after first use.
2. **It applies to select products only**, and cannot be combined with other offers on that page (there are also $200, $250 and a deposit-match code worth up to $100).
3. **New customers only**, and when the credit runs out Vultr switches to your linked payment method automatically.

So the real question is not how many months $300 covers but how much Windows compute you can burn in 30 days. Run the arithmetic on the base price plus the estimated license:

- Two 4 vCPU / 8 GB Windows boxes, roughly $107/month each once a ~$64 license is added, consume about $214 of the credit over 30 days. A third box fits only if you destroy it early.
- One 8 vCPU / 32 GB box at $160 base plus an estimated ~$128 license comes to about **$288 for the 30 days**, which is almost exactly the whole credit.
- A 16 vCPU / 64 GB box blows past $300 before the month is out, license included.

If your goal is to benchmark a .NET build, test a migration or run a short load test, $300 is generous. If you were hoping to run a production Windows box free for three months, the 30-day clock says no. Deprovision test instances before day 30 rather than after.

👉 [Register with code FLY300VULTR and read the current credit terms](https://www.vultr.com/coupons?ref=9738262-9J)

## The billing detail that costs people money

Vultr bills by the hour with a monthly cap, and the minimum billing unit is one hour. That part is standard. The trap is what happens when you stop an instance: **a powered-off server is still billed at the running rate.** You stop paying when you destroy it. Anyone used to a hypervisor where "off" means "cheap" will lose a month of credit to a machine they thought was idle.

👉 [Open the deploy screen and check the license line for your plan size](https://www.vultr.com/servers/windows?ref=9738262-9J)

## Real total cost: three ways providers hide the number

Promotional pricing is where Windows VPS comparisons go wrong, and the fix is to convert every offer into a three-year figure.

**Contabo, first 24 months.** The Windows Cloud VPS 6 (6 vCPU, 12 GB RAM, 200 GB SSD or 100 GB NVMe) is €6.00/month for the first 24 months against €7.50 regular. Two years at the promo rate is €144; from month 25 you pay €7.50, or €90 a year. Three-year total: about €234, versus €270 if you had paid the regular rate throughout. The discount is real but modest, and the price you budget for year three is the €7.50 figure, not €6.00.

**Liquid Web, two years up front.** Its 8 GB plan (4 vCPU, 240 GB, 5 TB) is $142.80/month "with a 2-year plan," which means **$3,427.20 charged today** for 24 months at 15% off. That is a committed payment, not a monthly bill, and the page does not state the rate after renewal. In exchange you get Plesk Obsidian, 100 GB of Acronis backup, DDoS protection and a choice of managed tiers, which is why the number is 20 times Contabo's.

**Vultr, hourly.** Nothing is locked and nothing is discounted. You pay the base rate plus license for as long as the instance exists, and you can destroy it the same afternoon. That flexibility is worth real money if your workload is bursty; it is worth nothing if the box runs 24/7 for three years, where a prepaid deal wins on price.

## Sizing by workload

**One remote desktop, one user, one Windows application.** 2 vCPU / 4 GB at $20/month base is the honest floor, and it is enough for an accountant's desktop, a single MetaTrader terminal or a line-of-business client. Move to 4 vCPU / 8 GB if a second person connects at the same time or the app keeps a large dataset in memory.

**A .NET or SQL Server production app.** Start at 4 vCPU / 8 GB rather than the smallest plan. Windows itself idles at 1.5 to 2 GB, and a database engine takes the rest quickly. The Vultr images are operating system images only; you install and license SQL Server yourself, and that cost sits outside everything in this article. When the working set stops fitting, jump to 8 vCPU / 32 GB at $160 base, which also brings 640 GB of storage.

**Multiple sites, or trading software running continuously.** 8 vCPU / 32 GB, and check the bandwidth allowance against your traffic before you order. Trading terminals are latency-sensitive enough that the region choice matters more than the plan choice; with 34 regions, pick the one nearest the broker's servers rather than the one nearest you.

Disk is the other sizing input people skip. Windows Server plus updates plus a database file eats 60 GB before you have added anything of your own, so the 55 GB entry plan is a test environment, not a production host.

## How Vultr compares with four other Windows VPS providers

Prices below are as listed on each provider's own pages during this review; the Contabo and OVHcloud pages carried no visible date, the Atlantic.Net page was dated 24 March 2023 and the Liquid Web page 20 February 2024. EUR and USD are not converted, and none of these should be read as a current quote without checking.

| Provider | Cheapest Windows option listed | What it includes | Best for |
| --- | --- | --- | --- |
| Vultr | $10/mo base, 1 vCPU / 2 GB / 55 GB, plus license | Hourly billing, 34 regions, 2016–2025 images | Short-lived or scaling workloads |
| OVHcloud | From $8.50/mo, VPS-2, 4 vCore / 8 GB / 75 GB NVMe | Daily backup, unlimited traffic (not in APAC), 99.9% SLA | Fixed monthly cost with backups included |
| Contabo | €4.40/mo for 24 months (€5.50 regular), 4 vCPU / 8 GB / 100 GB | Unlimited traffic, snapshots, 11 locations | Long-running boxes on a tight budget |
| Atlantic.Net | $15.00/mo Windows | License in the price, 8 data centers, 100% uptime SLA | Buyers who want one line item, no license math |
| Liquid Web | $119/mo, 2 vCPU / 4 GB / 80 GB, on a 2-year plan | Plesk, 100 GB backup, DDoS protection, managed options | Teams that want the host doing the administration |

Two notes. OVHcloud's page labels each plan "2027" without explaining what that refers to, so do not read it as a contract end date or a promo deadline. And Liquid Web's page contradicts itself on the Windows version, showing 2025 on the plan card and 2022 in the features section, so do not order on the strength of that detail.

Where each one wins: OVHcloud if you want backups bundled and a flat monthly figure; Contabo if the box runs for years and you can live with the renewal step-up; Atlantic.Net if you refuse to do license arithmetic; Liquid Web if unmanaged Windows administration is the actual problem you are buying your way out of.

## Before you order

- Open the deploy screen for your chosen size and read the license fee. It varies by plan and nothing else publishes it.
- Destroy test instances instead of stopping them, or they keep billing.
- Put a calendar reminder on day 27 of the credit window and remove anything you do not intend to keep paying for.
- Confirm the region matches your users or your broker, not your office.
- Choose Windows Server 2022 or 2025 unless an application forces 2016 or 2019.

The selection rule, short: one RDP user and one app means 2 vCPU / 4 GB; a small team, a .NET site or a database means 4 vCPU / 8 GB; a database on the same box as the app means 8 vCPU / 32 GB. Anything larger, price the license first, because at 16 vCPU the estimated license alone runs near $256/month.

👉 [Start with the 4 vCPU / 8 GB Windows plan and confirm the license at checkout](https://www.vultr.com/servers/windows?ref=9738262-9J)
