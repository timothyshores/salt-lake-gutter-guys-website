# Payments: how we actually collect $500

Written 2026-08-01. **Nothing here is set up yet.** This is the blocker on
revenue: two sites are live and neither can take money.

## The decision

**Stripe Payment Link.** A URL Brandon texts, client pays by card on their phone,
funds land in Tim's bank in ~2 days. No code, no integration, no maintenance.

| | Stripe Link | Stripe Invoice | Venmo / Zelle |
|---|---|---|---|
| Fee on $500 | ~$15 | ~$15 | $0 |
| Works over text | Yes | Email only | Yes |
| Card on file for monthly later | **Yes** | Yes | **No** |
| Paper trail / receipt | Yes | Yes | No |
| Chargeback exposure | Yes | Yes | No |
| Reads professional | Yes | Yes | No |

**Why the $15 is worth paying:** the monthly lead-alert product ($100-150/mo) is
the real business. A card already on file turns that into an upgrade instead of a
fresh ask every month. Venmo cannot do recurring billing at all.

**The honest counterargument:** at 10 clients that is $150 of pure fee. If the
monthly product never ships, Venmo would have been the right call. Accepting that
risk deliberately, because the monthly is the whole thesis.

**Chargeback note:** a card payment can be reversed for ~120 days. Low risk on a
delivered website with an email trail, but it is not zero, and Venmo does not
have it. Keep the "here's your live site" confirmation email as the paper trail.

## Terms

- **Full $500 up front**, before the site points at the client's domain.
- Site stays on our GitHub URL until payment clears. That is the leverage - no
  invoice chasing, nothing to repossess.
- If a client insists on 50/50: push back once, then take it, but launch only on
  final payment.
- **Brandon never touches money.** No checks, no cash, no Venmo to his personal
  account. One account, one record.

## Setup (Tim does this - account creation and card entry are his, not Claude's)

1. **stripe.com** -> Start now. Business type: Individual / Sole proprietor is
   fine to start. No LLC needed to accept payments.
2. Provide SSN (or EIN if one exists), address, and the bank account for payouts.
   ~10 minutes. Activation is usually instant, occasionally a day.
3. Dashboard -> **Product catalog** -> add product:
   - Name: `One-Page Website`
   - Description: `One-page business website, hosted, with lead form. One-time.`
   - Price: `$500.00`, **One time**
4. On that product -> **Create payment link**. Turn on:
   - Collect customer name, email, **and phone**
   - Add a custom field: `Business name`
   - Custom message after payment: `Thanks! Your site goes live within 24 hours.`
5. Copy the URL. It looks like `buy.stripe.com/xxxxx`. **Reusable** - the same
   link works for every client, no need to generate a new one per sale.
6. Send the URL to Brandon. Save it in `ARTIFACTS.md`.

**Optional later:** a second $250 link for a discounted or partial deal, and a
recurring $125/month link once the lead-alert product exists.

## The text Brandon sends

Short, no attachments, no PDF:

> Hey [name] - here's the link to get the site live:
> [link]
> $500 one time, that's everything. Once it's paid I'll have it pointed at your
> domain today. Any questions just call me.

**After payment clears**, Tim gets a Stripe email. Then:
1. Add the client's email as a Formspree recipient (`LEAD-DELIVERY.md`, option 1).
2. Point the domain, or confirm the GitHub URL is what they want.
3. Send the "you're live" email. That email is the delivery record.

## Open: how Brandon gets paid

**Unresolved and it matters.** If everything lands in Tim's Stripe:

- Tim receives a 1099-K from Stripe for the **full** amount and owes tax on all
  of it unless Brandon's cut is documented as an expense.
- Paying Brandon as a contractor means tracking payments and issuing a 1099-NEC
  if he passes $600 in a year. He will, quickly.
- Cleanest at this size: Tim's Stripe collects, Tim pays Brandon per sale, both
  keep a shared sheet of who was paid what.

**Settle the split before the first payment lands, not after.** See decision 5 in
`NEXT-SESSION.md`. A one-page email both parties agree to is sufficient. No
lawyer, no LLC, not yet.

**Worth a real accountant conversation once revenue exists** - this is a tax
question, not a technical one, and the answer changes if the split is large.

Related: `NEXT-SESSION.md`, `UNIT-ECONOMICS.md`, `ETHICS-AND-AGREEMENTS.md`.
