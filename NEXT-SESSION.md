# Next session: open decisions

Written 2026-08-01 at session end. Everything below is undecided. Nothing here
is blocked on code - these are business calls.

## State of the world

- Two sites built, live, forms tested end to end. **$0 revenue.**
- Salt Lake Gutter Guys (Jason) is the warmer prospect. Grizzly (Josh) is waiting
  on a business partner, a week or two out.
- Brandon has both site links and the Client Tracker. **The Business Playbook was
  just sent** (or is about to be): https://claude.ai/code/artifact/276b641f-7c2a-4aea-97f0-d6d1e8e75514
- Everything researched is committed to both repos. No open research threads.

## Decision 1: how do we take money? (blocking the first sale)

**Nothing exists for this.** No Stripe, no invoicing, no payment link. If Jason
says yes tomorrow, there is no way to collect.

**This is the actual blocker on revenue and should be first next session.**

Options to weigh:
- **Stripe Payment Link** - a URL Brandon texts, client pays by card. No code, no
  site integration, works from a phone. Fees 2.9% + 30 cents, so ~$15 on $500.
- **Stripe Invoice** - emailed invoice, same fees, feels more formal, creates a
  paper record.
- **Square / PayPal** - similar, possibly familiar to a contractor.
- **Venmo / Zelle / cash** - zero fees, no record, no chargeback protection, and
  reads unprofessional on a first sale.

**Recommendation to argue next session: Stripe Payment Link.** Fastest path from
"yes" to money, works over text, and a contractor who pays by card is far more
likely to keep a monthly subscription on that same card later.

**Also undecided:** whose Stripe account, and how money gets split with Brandon
(see decision 5).

## Decision 2: who pays for the domain, and does hosting stay free?

Current documented position: **client buys the domain in their own name**
($12-15/year), we host free forever.

Unresolved:
- Do we charge a small monthly for hosting ($20-50 was floated)?
  - **Argument against:** hosting genuinely costs us $0, "no monthly fee" is our
    strongest differentiator against $99/month competitors, and a small monthly
    invites cancellation conversations for almost no revenue.
  - **Argument for:** it establishes the habit of paying us monthly, which makes
    the $100-150 lead-alert upsell an increase rather than a new purchase.
- If the client will not buy their own domain, do we buy it and bill them?
  - Risk: we eat renewals for clients who vanish, and we hold their property,
    which creates the leverage problem `ETHICS-AND-AGREEMENTS.md` warns against.

**Recommendation to argue: keep hosting free, no monthly on the website.** Sell
the monthly on lead alerts, where the value is obvious and the price is real.
"No monthly" is worth more as a sales weapon than $30/month is as revenue.

## Decision 3: is $500 the right price?

Tim's own words: "I haven't really done enough pricing research to understand how
much time am I putting into this."

**What we know** (`MARKET-PRICING.md`): local agencies $6,000-35,000. Freelancers
$3,000-8,000. Fiverr $175-1,000. Monthly shops $99/month = $1,188 year one.

**What we do not know:** how long a site actually takes Tim now that a template
exists. That number decides whether $500 is smart or a mistake.

**Do this next session:** time-box the next build. If site #3 takes two hours,
$500 is excellent. If it takes twelve, $500 is a job, not a business.

Positions worth weighing:
- **Keep $500** - it is deliberately underpriced to win the first clients and
  build proof. Raise it once there are testimonials and lead numbers.
- **Raise to $750-1,000** - still far under every real competitor, and the first
  price is the anchor for every future client.
- **Tiered** - $500 basic, more for extra pages or photography.

**Recommendation to argue: hold $500 for the first three clients**, explicitly as
an intro rate, then reprice with real lead data in hand. Say "intro rate" out
loud so raising it later is expected rather than a betrayal.

## Decision 4: what does Brandon actually quote?

Tim has not synced with Brandon on the exact offer. Brandon has been saying $500.
The Playbook now documents: $500 one time, one page, hosting free forever, small
changes free, client owns it, domain $12-15/year on their card.

**Confirm Brandon is saying the same thing.** A mismatch between his pitch and
our documentation is the fastest way to a bad first client experience - it
already happened once with "the site is already done" (documented in the
Playbook).

## Decision 5: the Tim/Brandon revenue split

**Still undefined.** Deferred deliberately, which was correct at $0.

**Settle it before the first client's money lands, not after.** Worth deciding:
split on the $500, split on the monthly (they may differ - the site is mostly
Tim's labor, the monthly is mostly Brandon's retention work), who fronts costs,
what happens if someone stops participating.

An email both agree to is enough. No lawyer, no entity, not yet.

## Build queue (only after someone pays)

In order:
1. **Call tracking** - forwarding number, counts calls. ~$1.15/month. Highest
   value because 83% of homeowners call rather than fill out the form.
2. **Visitor analytics** - free, small build.
3. **SMS alert + auto-text-back** - the $100-150/month product. Needs Formspree
   Professional ($30/month) for webhooks, plus A2P 10DLC registration.
4. **Monthly lead report** - start manual, a count and a short email.
5. **Cloudflare Pages migration** - removes the GitHub commercial-use ambiguity.
   30 min/site, free. Do it while there are few sites.

**Nothing here gets built before a client pays.** Standing rule.

## Reminders

- **Do not put "Licensed and Insured" on the SLGG site** until Jason personally
  confirms. Records show expired 11/30/2023.
- **No AI voice calling, ever.** FCC ruling, $500-1,500 per call.
  See `AI-CALLING-LEGAL.md`.
- **Re-run the cross-wiring check** after any form edit (`LEAD-DELIVERY.md`).
- Two test emails sitting in timothymshores@gmail.com can be deleted.

## Reading order for a fresh session

1. This file
2. `UNIT-ECONOMICS.md` - costs and margins
3. `MARKET-PRICING.md` - competitor and contractor economics
4. `ETHICS-AND-AGREEMENTS.md` - working agreement, lead ownership
5. `ARTIFACTS.md` - what Brandon has
