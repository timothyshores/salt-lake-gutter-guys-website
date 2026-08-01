# Unit economics: what a client actually costs us, and for how long

Written 2026-08-01. The question this answers: we charge $500 once and promise
hosting "forever" - what does forever actually cost, and when does it stop being
profitable?

## Short answer

**A $500 site costs us about $0-3/month to keep alive.** At 10 clients that is
$0-30/month total against $5,000 collected. The one-time fee is not a liability
we are quietly absorbing - it is nearly pure margin, indefinitely.

The costs that matter are not hosting. They are Tim's time, and the shared
services that only appear once we sell the monthly product.

## Per-client cost, website only (the $500 offer)

| Item | Cost | Notes |
|---|---|---|
| Hosting | **$0** | GitHub Pages today. 100 GB/month bandwidth, we use a rounding error of it |
| Lead form | **$0** | Formspree free tier, until pooled volume passes 50/month |
| SSL certificate | **$0** | Automatic |
| Deployment | **$0** | Git push, ~45 seconds |
| Domain | **$0 to us** | Client buys it in their own name, $12-15/year on their card |
| **Total recurring** | **$0/month** | |

**A website client we never hear from again costs us nothing.** That is why
"hosting forever" is a safe promise and a genuinely strong selling point.

### The one real cost: Tim's time

- Initial build: a few hours, mostly research and content
- **Each additional gutter site is cheaper than the last** - same template, same
  structure, same objections
- Small revisions: minutes
- The scaling risk is not money, it is a client who wants weekly changes. Scope
  is the thing to protect, not dollars.

## Where hosting stops being free

**Not bandwidth.** A local gutter site will not approach 100 GB/month.

**The real trigger is GitHub's terms**, which say Pages is not for running a
business. A static brochure site with no checkout is ambiguous under that clause,
nobody enforces it at this scale, but it is real once clients pay.

**Migration path, when we take it:** Cloudflare Pages. Free tier, explicitly
permits commercial use, same git-push deploy, roughly 30 minutes per site.

**Recommendation: migrate when client #1 pays.** Trivial at two sites, tedious at
fifteen. Cost stays $0.

## Formspree: the first shared cost

Free tier is **50 submissions/month across the entire account**, not per client.

| Clients | Likely monthly submissions | Plan | Cost |
|---|---|---|---|
| 1-2 | 10-40 | Free | $0 |
| 3-5 | 40-120 | Personal | $10-15/mo |
| 6-15 | 120-400 | Professional | $30/mo |

**A single busy contractor can use 20-30 alone.** Budget the $15 as soon as
client #2 pays rather than getting surprised by a silent cap.

Amortized across clients this is $2-3/client/month at worst.

## The monthly product: costs at 4 clients

From `LEAD-DELIVERY.md`, corrected:

| Item | Monthly |
|---|---|
| Twilio numbers (1/client) | $4.60 |
| SMS usage (~150 msgs, incl. carrier fees) | ~$2.45 |
| A2P 10DLC recurring campaign fee | $3-20 |
| Vercel Pro (or Cloudflare Workers at $0) | $20 or $0 |
| Formspree Professional (webhooks required) | $30 |
| **Total** | **~$60-77/month, all clients combined** |

Plus a one-time $20-65 for A2P registration.

**Against 4 clients at $125/month = $500/month revenue, that is roughly 85%
margin.**

**Worth checking before building: Cloudflare Workers instead of Vercel.**
Cloudflare's free tier does not carry Vercel's non-commercial restriction, which
would remove $20/month outright.

## Profitability by stage

| Stage | Revenue | Costs | Margin |
|---|---|---|---|
| 2 sites, unpaid (today) | $0 | $0 | - |
| 1 site sold | $500 once | $0/mo | ~100% |
| 5 sites sold | $2,500 once | $15/mo | ~99% |
| 5 sites + 3 monthly | $2,500 + $375/mo | ~$70/mo | ~81% ongoing |
| 15 sites + 10 monthly | $7,500 + $1,250/mo | ~$150/mo | ~88% ongoing |

**The business is structurally high-margin.** The constraint is sales volume and
Tim's build time, never infrastructure cost. That is the correct shape for a
two-person side business - it means a slow month costs almost nothing to survive.

## What GoHighLevel would do to these numbers

GoHighLevel at the tier that actually permits reselling is **$497/month**.

| Clients | Our cost | GHL Agency Pro | Difference |
|---|---|---|---|
| 2 (today) | $0 | $497/mo | -$497/mo |
| 5 | ~$70/mo | $497/mo | -$427/mo |
| 10 | ~$150/mo | $497/mo | -$347/mo |
| 25 | ~$300/mo | $497/mo | -$197/mo |

**Breakeven is somewhere past 40 clients** - and even then GoHighLevel only wins
if we would use enough of it to justify the switch.

**The honest counterpoint:** GHL bundles a CRM, pipelines, email marketing,
calendars, and funnels. We are comparing against the two features we would
actually use. If we ever need the full suite, the comparison changes. Today we do
not, and $497/month before any revenue is a bet against ourselves.

**Cheaper resell platforms if it ever comes up:** Centripe $99 (its $299 tier
matches GHL's $497 mechanics), DashClicks $199, Vendasta $99. All newer and less
proven.

## What we can track, and what it costs

Tim's question: how do we prove value to clients?

| Metric | How | Cost | Status |
|---|---|---|---|
| Form submissions | Formspree dashboard | $0 | **Working today** |
| Service type + urgency | Already in the form | $0 | **Working today** |
| Phone calls from the site | Call tracking number that forwards | ~$1.15/mo + ~$0.01/min | Not built |
| Page views / visitors | Analytics script | $0 (Plausible ~$9/mo if privacy-first) | Not built |
| Where visitors came from | Same analytics | $0 | Not built |

**Call tracking is the highest-value missing piece.** 83% of homeowners call
rather than fill out a form, so the channel that proves our value is the one we
currently cannot see. A report saying "14 calls and 3 form leads" is far more
convincing than "3 leads."

**Google Analytics is free but heavy and privacy-invasive.** Plausible or
Cloudflare Web Analytics are lighter; Cloudflare's is free. Either is a small
build.

**Build both after client #1 pays**, alongside the monthly product. They exist to
justify a recurring fee, so they should arrive with it.

## The one number Brandon should carry

**One gutter job nets the contractor $400-800. The website costs $500 once.**

Everything else is detail. That sentence is the sale.

Related: `MARKET-PRICING.md`, `LEAD-DELIVERY.md`, `AGENCY-PLATFORMS.md`.
