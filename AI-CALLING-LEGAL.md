# AI voice calling: the legal answer is no

Researched 2026-08-01. **Decision: we do not offer AI voice calling. The instant
auto-text does the same job at a fraction of the legal risk.**

This is not caution for its own sake. It is the clearest legal finding in any of
our research, and the exposure lands on us as well as the client.

## The core rule

**FCC Declaratory Ruling FCC 24-17, adopted February 8, 2024:** AI-generated and
cloned voices are "artificial" voices under the TCPA. That was a unanimous vote,
and it closed the argument that AI voice is somehow a new category outside the
statute.

Consequence: an AI voice calling a cell phone is subject to the TCPA's
artificial/prerecorded voice rules, which require **prior express written
consent** for marketing calls. A sales callback is a marketing call.

Confirmed independently by Wiley, Mayer Brown, and Wilson Sonsini - three large
firms converging on the same reading.

## Our current form does not create that consent

A "Send & Get My Free Estimate" button is not consent. Compliant TCPA consent
needs, near the phone field:

- An unchecked checkbox (never pre-checked)
- Explicit language that the person agrees to be called/texted using automated or
  AI technology
- The business name
- A statement that calls may use an artificial voice
- A statement that consent is not a condition of purchase
- Legible, unburied placement before the submit button

**Rebuilding every lead form to this standard is a real copy and engineering
change, not a settings toggle.** If a client ever wants AI voice, that work gets
quoted as its own line item.

## Penalties

- **$500 per negligent violation. Up to $1,500 per willful violation.**
- **No cap on aggregate damages.** No proof of actual harm required.
- Private right of action under 47 U.S.C. 227(b), which is the provision covering
  artificial voice. Class actions in this space settle in the tens of millions.

**The agency-specific risk:** if we design and operate the calling
infrastructure, we may be a "caller" under the TCPA and share liability. And
because we would reuse one form template across every client, a single bad
consent design becomes exposure across the entire client roster at once. That is
the part that makes this categorically different from a client's own bad decision.

## Nuances worth knowing (do not let them talk you into it)

**Fifth Circuit split, Feb 25 2026:** *Bradford v. Sovereign Pest Control* held
the TCPA's text requires only express consent, not written consent, and that the
FCC exceeded its authority with the 2012 written-consent rule (applying *Loper
Bright*). **This binds only Texas, Louisiana, and Mississippi.** Utah is in the
Tenth Circuit. Written consent still applies to us. A circuit split raises the
odds of Supreme Court review, but that has not happened.

**One-to-one consent rule is dead:** the Eleventh Circuit vacated it in
*Insurance Marketing Coalition v. FCC*, Jan 24 2025. This is deregulatory and
does not help - it only means one consent can cover multiple sellers. You still
need valid consent first.

**Is a "get a quote" form submission consent for an AI callback?** Genuinely
unresolved. No controlling case found on this exact fact pattern. Analyst
consensus leans no, because the form never discloses that an AI rather than a
human will call, and the FCC ruling carries its own identification/disclosure
requirement. **Unresolved is not permission** - it means we would be the test
case.

## State disclosure law

**California AB 2905** (effective, amends Public Utilities Code 2874): when an
autodialer places a call, the opening announcement **must disclose** that the
message uses an artificial voice. Verified against the legislature's own bill
text. Applies to any client calling into California.

**Utah SB 149 (2024), narrowed by SB 226 (2025):** disclosure required only when
a consumer **explicitly asks**, or for regulated occupations and high-risk
interactions (health, financial, legal, biometric). A gutter sales callback is
likely outside that scope. **Utah is materially lighter than California** - but
"lighter state disclosure law" does not fix the federal TCPA consent problem,
which is the actual blocker.

Utah's text was not fetched directly; it rests on secondary law-firm summaries
(Alston & Bird among them). Verify at le.utah.gov before relying on it.

## Consumer reception: bad, from the credible sources

The vendor-published "70% of consumers love AI agents" statistics are marketing
from companies selling AI agents. Discounted. What credible pollsters say:

- **Gallup:** only 27% of Americans trust businesses to use AI responsibly, down
  from 31% in 2025.
- **Pew (March 2026):** 16% think AI will have a positive societal impact; 31%
  say it does more harm than good.
- **Truecaller survey:** 80% of Americans ignore calls from unknown numbers.
- Vendor-reported but directionally believable: 44% of hang-ups on AI calls
  happen because it sounded like a bot.

No rigorous poll exists on "how do homeowners react to an AI calling them back
after a form submission." That gap is itself informative.

## Why texting is the right answer

**Text messages are not "artificial or prerecorded voice" under the TCPA.** The
Ninth Circuit has held that "voice" requires actual sound. This is appellate case
law, not a vendor talking point.

So an automated SMS reply:
- Avoids the February 2024 FCC AI-voice ruling entirely
- Falls under ordinary TCPA consent rules for texts, not the heightened
  artificial-voice tier
- Still requires consent and A2P 10DLC registration - not unregulated, just a
  materially lower tier

**It also hits the same business goal.** 78% of homeowners hire whoever responds
within five minutes. An instant text achieves that. The AI voice call adds legal
exposure without adding speed.

## Decision

1. **No AI voice calling product.** Not for Salt Lake Gutter Guys, not for anyone.
2. **Instant auto-text stays the speed-to-lead product**, as already planned.
3. If a client asks for AI calling: explain the FCC ruling plainly. "It's illegal
   without written consent your form doesn't collect, and the fine is up to
   $1,500 per call." That answer builds trust.
4. If a client insists after that, it requires a rebuilt consent form quoted
   separately, and an attorney review. Not a thing we sell off the shelf.
5. **Never build an AI dialer that calls people who did not fill out a form.**
   Not a gray area.

## One thing to fix regardless

Even for **texting**, our current form has no consent language. Before the SMS
product ships to a paying client, the form needs a consent line covering
automated texts. Small change, do it as part of the SMS build.

## Note on Air AI

Air AI, the viral "AI sales rep" product, is defunct. The FTC sued in August
2025 and settled March 2026 with an $18M judgment and a permanent ban on
marketing business opportunities.

**That case was about business-opportunity fraud - false earnings claims sold to
entrepreneurs - not about AI voice technology being illegal.** Do not repeat the
mischaracterization circulating in competitor blogs. The TCPA analysis above is
the real reason we say no.

Related: `ETHICS-AND-AGREEMENTS.md`, `LEAD-DELIVERY.md`, `BOOKING-RESEARCH.md`.
