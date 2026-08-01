# Booking and appointment scheduling: research and decision

Researched 2026-08-01. **Conclusion: do not build custom booking. Embed Cal.com's
free tier as a secondary CTA and move on.**

## The finding that decides it

Online self-booking is a minority behavior in home services, and gutter estimates
are structurally a bad fit for it.

| Data point | Number |
|---|---|
| Homeowners who prefer to CALL a contractor | **83%** |
| Homeowners who prefer online/app booking | **12%** |
| Phone leads vs web form conversion | Phone converts **10-15x** better |
| Homeowners who hire whoever calls back within 5 min | **78%** |

Source: CallRail 2026 home-services stats, AgentZap phone stats 2026. These are
vendor-published (call-tracking companies benefit from "calls matter"), so treat
the exact percentages as directional. The direction is consistent across sources.

**The structural problem:** a gutter estimate requires measuring the house. You
cannot quote sight-unseen. So a calendar slot is not booking a job - it is
booking a visit that still needs a qualifying phone call. A self-scheduled slot
that skips qualification can send a truck to a house that cannot be quoted
(wrong material, roof inaccessible, HOA restriction).

**Therefore: speed-to-callback beats self-scheduling for this trade.** That is
what the SMS alert and auto-text already deliver, which is why they stay first on
the upsell ladder.

## What we should do: Cal.com free tier

Best fit by a wide margin.

| | Cal.com free |
|---|---|
| Cost | **$0** |
| Booking limit | Unlimited |
| Reminders | Email **and SMS** on the free tier |
| Embed in static HTML | Yes, documented snippet |
| Our hosting cost | None |

**Verify the SMS-on-free-tier claim before promising it to a client.** Cal.com's
own pricing page states it, but it is an outlier - every competitor gates SMS
behind a paid tier. Confirm live before it appears in a pitch.

Add it as a secondary CTA next to the phone number, never replacing it. It
captures the 15-20% who will not call: after-hours browsers, and younger
homeowners who avoid phoning strangers.

**Do not charge separately for this.** It is a $0 embed. Bundle it, mention it as
included, do not build a price around it.

## Alternatives considered

| Tool | Free tier | Paid | Verdict |
|---|---|---|---|
| **Cal.com** | Unlimited bookings, email+SMS | $12/user/mo teams | **Chosen** |
| SimplyBook.me | 50 bookings/mo, widget included | $11.90/mo | Second best; SMS always costs extra ($8/100) |
| Calendly | 1 event type only, their branding | ~$10-12/seat/mo | Free tier too limited |
| Square Appointments | Free solo, email reminders | $49/mo Plus | Ties client into Square payments |
| Setmore | 4 users, 200 appts/mo, email only | ~$5-12/user/mo | SMS is paid-tier only |
| Google Calendar (personal) | 1 booking page, **no reminders** | Workspace $7/user/mo | No reminders makes it useless here |

Square, Setmore, and Zoho prices are aggregator-sourced (vendor pages did not
fetch cleanly). Verify before quoting.

## What we will NOT compete with

**Jobber** is real field-service software: scheduling, dispatch, invoicing,
job tracking.

- Core: **$29/month** (1 user) - includes online booking, no SMS reminders
- Connect: **$99/month** - adds automated SMS reminders and two-way texting

If a client wants a real job calendar with dispatching, **the right answer is to
recommend Jobber, not to build a worse version.** We are not underpricing a
mature product with a thin imitation. Saying "that's what Jobber is for" builds
more trust than pretending we can do it.

**Housecall Pro** ~$59/mo entry (aggregator-sourced). **ServiceTitan**
~$245-500/tech/month plus $5K-50K implementation - explicitly not for shops with
3 or fewer techs. Irrelevant to our segment; listed so we recognize the names.

## Two-way SMS (homeowner texts back, contractor's phone buzzes)

Two paths if this becomes a real ask:

1. **Raw Twilio** - $0.0083/message each direction, $1.15/month per number, plus
   A2P 10DLC registration. Cheap per message but requires building the forwarding
   logic. Real engineering.
2. **Off-the-shelf number** - Quo (formerly OpenPhone) $15-19/mo, or Google Voice
   ~$10/user/mo with Workspace. Buy-not-build. Runs alongside the site, not
   inside it.

Recommendation if it comes up: option 2. Not worth building a forwarding layer
for a feature one client asked for.

## No-show data - weak, flagged

Commonly cited: SMS reminders cut no-shows ~38%. **That traces to a single
healthcare study** (Klara), repeated across vendor blogs as though it were
general. Cross-industry no-show baselines run 10-30%.

**No home-services-specific no-show or SMS-effectiveness study exists.** If this
comes up in a pitch, present it as "healthcare data, probably transfers" - do not
quote 38% as a home-services number.

## Decision

1. Embed Cal.com free tier as a secondary CTA under the phone number. $0, bundled.
2. Keep phone-first. The primary CTA stays "call now" because that is what 83% do.
3. Speed-to-callback (SMS alert + auto-text) stays the paid product.
4. Recommend Jobber for anyone who needs real scheduling. Do not compete.
5. Two-way SMS only on request, and buy it rather than build it.

**Not built yet.** Per the standing rule, nothing past the website gets built
until a client pays.

Related: `MARKET-PRICING.md`, `LEAD-DELIVERY.md`.
