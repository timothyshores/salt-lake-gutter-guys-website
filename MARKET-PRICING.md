# Market pricing and cost structure

Researched 2026-08-01. Refresh if it goes stale past ~6 months. Vendor pricing
pages are authoritative for their own prices; everything else is noted.

## What competitors charge for a small-business brochure site

| Provider type | 2026 range | Confidence |
|---|---|---|
| Fiverr | $175-1,000 | Fiverr's own guide |
| Upwork | ~$800 average; 32% of jobs $1,000+ | Third-party analysis |
| Experienced freelancer | $50-150/hr; 5-page site $3,000-8,000 | Third-party |
| Small local agency | $6,000-35,000 one-time, usually plus retainer; template work clusters $8,000-15,000 | Third-party |
| Wix / Squarespace / GoDaddy DIY | ~$10-20/month | Aggregators only - vendor pages are JS-rendered and would not fetch |
| Flat-monthly "site in a box" | $99/month is the consistent anchor ($1,188 year one) | Multiple vendor pages |

**Our position: $500 one-time, no monthly, client owns it.** Cheapest real option
on the list by a wide margin. That is deliberate - undercut on price, win on
volume, build a client base. AI-assisted build is what makes the margin work at
that price.

**Weakly sourced, flagged:** the claim that AI has pushed commodity web work down
20-35% since 2025 could not be tied to a named industry survey. Directionally
consistent across commentary, but do not quote it as fact.

## Our actual costs

| Line item | Cost | Notes |
|---|---|---|
| GitHub Pages hosting | $0 | 100 GB/month soft bandwidth limit, 1 GB site size, 10 builds/hour soft limit |
| Formspree free tier | $0 | 50 submissions/month **account-wide**, not per form |
| Formspree Personal | $15/month | 200 submissions/month |
| Formspree Professional | $30/month | 2,000 submissions/month |
| Custom domain | $12-15/year | Only when a client wants one |
| Twilio SMS | $0.0083/message each direction | Plus carrier surcharges ~$0.0035-0.0045 outbound |
| A2P 10DLC registration | ~$4.50 brand + ~$41.50 vetting + ~$15 campaign, one-time | A recurring monthly carrier campaign fee also exists and was **not** confirmed - verify before quoting |

At two demo sites the run cost is literally $0. On a $500 site nearly all of it
is margin; the real cost is Tim's time, so protect scope rather than price.

## Formspree scaling trigger

Free tier is 50 submissions/month across the entire account. Two live demo sites
will not approach it. **Revisit at roughly 4-5 paying clients** - a single busy
contractor site can pull 20-30 leads/month on its own.

## GitHub Pages: the commercial-use question

GitHub's terms say Pages "is not intended for or allowed to be used as a free
web-hosting service to run your online business, e-commerce site, or any other
website that is primarily directed at either facilitating commercial transactions
or providing commercial software as a service."

**Read:** a static brochure site for a local contractor - no checkout, no
transactions, no SaaS - sits in an ambiguous zone the clause does not clearly
address. It targets storefronts and SaaS products, not informational sites.

**This is an interpretation, not a GitHub-confirmed exemption.** Nobody enforces
this against small local brochure sites and we are far from every technical
limit. But it is a real, if low, risk once paying clients are involved.

**Decision needed once client #1 pays** (Tim's call, not urgent):
- Stay on Pages. Free, zero migration, small unenforced-terms risk.
- Move to Cloudflare Pages or Netlify. Free tier on both, explicitly permits
  commercial use, same git-push deploy, ~30 minutes to migrate per site.

Recommendation: **move to Cloudflare Pages when the first client pays.** Same
price ($0), removes the terms question entirely, and the migration is trivial
while there are only a few sites. Doing it later with fifteen sites is the
version that hurts.

## Competitor pricing on the monthly upsell

- **Podium** (closest match to lead alerts + SMS + reviews + GBP): list is
  $399/1,199 Core through Enterprise, but real all-in for a single-location small
  business is **$450-800/month** after 10DLC fees, extra numbers, AI add-on, and
  a $500 one-time setup. Podium does not publish pricing; third-party reported.
- **GoHighLevel** (vendor page, confirmed): Starter $97/month, Unlimited
  $297/month, Agency Pro $497/month. This is an *agency* cost, paid before any
  client signs.

**Our $100-150/month is well under both**, with a per-client run cost of a few
dollars. That gap is the business.

Related: `CLIENT-SITES.md` for architecture, `BRANDON-CONTEXT.md` for how to
frame any of this to Brandon.
