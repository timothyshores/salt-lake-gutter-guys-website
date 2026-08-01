# Lead delivery: where a submitted form actually goes

How lead routing works today, what the options are when a client pays, and what
each costs. Researched 2026-08-01.

## Current state (verified 2026-08-01)

Both forms tested end to end with live submissions. Emails delivered.

| Site | Endpoint | Delivers to |
|---|---|---|
| Salt Lake Gutter Guys | `xnjekoqw` | timothymshores@gmail.com |
| Grizzly Gutters | `xbdnwlbz` | timothymshores@gmail.com |

**Isolation is structural, not configured.** The endpoint is hardcoded in each
repo's `index.html`. There is no shared routing layer, no lookup table, no
config that could mismatch. A submission from a page can only reach the endpoint
written into that page.

### Cross-wiring check - run after ANY edit to a form

The failure mode that matters once clients pay: contractor A receives
contractor B's leads. This catches it.

```bash
A=$(grep -o 'formspree.io/f/[a-z]*' ~/Documents/Code/salt-lake-gutter-guys-website/index.html | sort -u)
B=$(grep -o 'formspree.io/f/[a-z]*' ~/Documents/Code/grizzly-gutters-website/index.html | sort -u)
[ "$A" = "$B" ] && echo "FAIL: same endpoint in both sites" || echo "PASS: distinct"
```

Verified passing 2026-08-01. Each test email also carried its own site's unique
field set (SLGG has `service` and `timing`; Grizzly does not), which
independently confirms no crossover.

## Option 1: add the client's email as a recipient (free, do this first)

Formspree lets a form send to multiple addresses. In the form's settings, add
the client's email alongside Tim's.

- **Cost:** $0. Free tier allows 2 linked emails.
- **Result:** client gets every lead; Tim keeps a copy to confirm delivery is
  actually working.
- **Do this the day a client pays.** No code change, no deploy.

**Keep Tim on the recipient list.** If a client says "I never got that lead,"
the copy in Tim's inbox is the only way to prove the system worked. Do not
remove it to be polite.

## Option 2: Gmail forwarding (free, avoid)

Tim could auto-forward client leads from his own inbox with a Gmail filter.

**Don't.** It puts Tim's personal inbox in the delivery path for a client's
business-critical leads. If Gmail flags something, or Tim changes a filter, a
contractor silently stops getting work. Option 1 does the same thing without the
single point of failure.

## Option 3: SMS to the contractor (the actual product)

The recurring revenue. Formspree cannot send SMS itself - it only relays to
email or fires a webhook. So the build is:

```
form submit -> Formspree webhook -> small serverless function -> Twilio -> contractor's phone
```

- **Formspree side:** webhooks require the **Professional plan ($30/month)**.
  This is an account-level cost, not per-client, so it is shared across every
  client once one is paying for it.
- **Twilio side:** $0.0083 per message each direction, plus carrier surcharges
  around $0.0035-0.0045. Call it roughly a penny per text.
- **One-time A2P 10DLC registration:** ~$4.50 brand + ~$41.50 vetting + ~$15
  campaign. There is also a recurring monthly carrier campaign fee that was
  **not confirmed** - verify before quoting a client a number.
- **The function:** Cloudflare Workers or Vercel free tier handles this volume
  at $0.

**Corrected run cost at 3-5 clients: about $40-57/month**, not the $30-40 first
estimated. Two line items were missed:

| Line item | Monthly |
|---|---|
| Twilio numbers (1 per client, 4 clients) | $4.60 |
| SMS usage (~150 msgs, incl. carrier fees) | ~$2.45 |
| A2P 10DLC recurring campaign fee | $3-20 |
| **Vercel Pro** (see below) | $20.00 |
| Formspree (Personal tier once pooled volume passes 50) | $10.00 |
| **Total** | **~$40-57/month** |

Plus a one-time setup spike of roughly $20-65 for A2P brand and campaign
registration.

**The miss that mattered: Vercel's free Hobby tier is restricted to
personal, non-commercial projects.** Running client lead alerts on it violates
their terms. Vercel Pro is $20/month and covers the whole agency, but it alone is
most of the original estimate. Cloudflare Workers is the alternative worth
checking - its free tier does not carry the same non-commercial restriction.

**Second miss: A2P 10DLC has a recurring monthly campaign fee**, not just the
one-time registration previously noted.

Still excellent margin at $100-150/month per client. Just not as free as it first
looked, and worth knowing before quoting.

**Where it breaks:** SMS volume is never the problem (10x the messages is only
~$25/month). The step-functions are Formspree tier boundaries, a second A2P
campaign if marketing and transactional messages need separate registration, and
per-client phone numbers at $1.15 each. Past ~10 clients this lands at $80-150/mo
before usage, which is the point where a bundled platform deserves a real
comparison against DIY.

## Option 4: auto-text back to the homeowner (highest conversion value)

Same webhook, one extra Twilio call: "Thanks, this is Jason at Salt Lake Gutter
Guys, I'll call you within the hour."

This is psychologically the biggest lever in the whole stack. A homeowner with
water pouring over a gutter calls three companies. The one that responds first
books the job. An instant auto-text stops them from continuing down the list.

Marginal cost: another penny. Build it in the same bundle as option 3.

## Option 5: auto-call the lead - SKIP

Technically easy, reads as spam to someone who just filled out a form, and it is
the piece that creates TCPA exposure. The auto-text accomplishes the same goal
without the legal risk. Decided against; do not revisit.

## Recommended sequence

1. **Today, free:** leads go to Tim. Already working.
2. **Day client #1 pays:** add their email as a recipient. Free, 2 minutes.
3. **After the first monthly subscriber:** build options 3 and 4 together as one
   bundle. Upgrade Formspree to Professional at that point, not before.
4. **Never:** option 5.

Nothing past step 2 gets built until someone is actually paying for it.

## Formspree plan ladder (for reference)

| Plan | Price | Submissions/month | Why upgrade |
|---|---|---|---|
| Free | $0 | 50 account-wide | Current |
| Personal | $15/mo | 200 | Volume only |
| Professional | $30/mo | 2,000 | **Webhooks** - required for SMS |
| Business | $90/mo | 20,000 | Not needed at this scale |

Note the free tier's 50/month is **account-wide across every client**, not per
form. A single busy contractor can use 20-30 alone.

Related: `CLIENT-SITES.md` (architecture), `MARKET-PRICING.md` (what
competitors charge per lead).
