# Client sites: how these are organized

Read this before touching lead capture or spinning up a new client site.

## Current state

Two separate potential-client sites, each its own repo, each its own GitHub
Pages URL. Neither client has paid yet.

| Client | Repo | Live URL | Status |
|---|---|---|---|
| Grizzly Gutters | `grizzly-gutters-website` | https://timothyshores.github.io/grizzly-gutters-website/ | Demo, Formspree wired |
| Salt Lake Gutter Guys | `salt-lake-gutter-guys-website` | https://timothyshores.github.io/salt-lake-gutter-guys-website/ | Demo, Formspree pending |

Separate repos on purpose. **If a third gutter client lands, that is the
trigger to extract a shared template** - not before. Two sites is not enough
variance to know what actually needs to be configurable, and guessing at the
seams early creates a template that fights every new client.

Roles: Brandon owns the client relationship and presents the site. Tim owns
technical delivery - build, hosting, revisions, lead capture.

## Lead capture: Formspree

**One Formspree account on Tim's personal Gmail. One separate form per client
site.**

Each form gets:
- its own endpoint ID (`formspree.io/f/xabc1234` vs `formspree.io/f/xdef5678`)
- its own submission inbox
- its own name in the Formspree dashboard

That is the separation. Do not create a separate Formspree *account* per
client - one dashboard where every client's leads are visible is the point,
since Tim owns service delivery and needs to confirm forms are actually
firing. When a client pays and wants leads in their own inbox, add their email
as a recipient on their form. The form and account stay Tim's.

Free tier: 50 submissions/month across the whole account. Fine for two demo
sites. Watch it around client 4 or 5.

## How a submission finds the right inbox

The endpoint ID hardcoded in each repo's `index.html` **is** the link. A
submission from this site can only ever land in the form whose ID is in this
file's `<form action="...">`. Name each form after the client in the Formspree
dashboard and there is no ambiguity.

Every client repo's `index.html` carries a comment above the form naming which
Formspree form it maps to. Keep that comment accurate - it is the only place
the mapping is written down outside the Formspree dashboard itself.

## Is Formspree the right long-term vendor?

Right for now, wrong for scale. It is a form-to-email relay: no lead tracking,
no follow-up, no record a lead existed beyond an email in an inbox.

The real conversion problem for gutter contractors is **speed to lead**. A
homeowner with water pouring over a gutter calls three companies; whoever
responds first books the job. Formspree cannot text. Instant SMS-to-contractor
on form submit is both the biggest conversion lever and the natural monthly
recurring product (this is the actual pull toward GoHighLevel or similar).

Do not migrate now - two demo sites do not justify it. Revisit at 4-5 paying
clients, when recurring revenue justifies a paid platform.

## The recurring product: speed to lead

The site is a one-time $500. **Speed-to-lead automation is the recurring
revenue**, and it is what turns this from a project business into an agency.
Build it for the first paying client, not before.

Client email gets wired into their form the day they pay, so they get lead
notifications immediately. Everything below layers on top of that.

Ordered by value per unit of build effort:

1. **SMS alert to the contractor on form submit.** Name, number, job type, in
   seconds. Twilio, cents per message. This is ~80% of the value and the
   easiest piece. Pitch: know about every lead before your competitor picks up.
2. **Auto-text back to the homeowner.** "Thanks, this is Jason at Salt Lake
   Gutter Guys, I'll call you within the hour." Same cost. Psychologically the
   biggest lever - the homeowner stops calling competitors because someone
   already responded. Critical for a contractor who is on a ladder and cannot
   answer his phone.
3. **Booking link for estimate slots.** Real value, but only works if the
   contractor actually keeps a calendar. Most solo gutter guys do not. Sell
   second, and only to organized clients.
4. **Auto-call the lead. SKIP.** Technically doable, reads as spammy to a
   homeowner who just submitted a form, and it is the option that creates TCPA
   exposure. The auto-text does the same job without the legal risk.

**Constraint to know before promising a launch date:** business SMS to US
consumers requires A2P 10DLC registration. It is a form, not a blocker, but
approval takes a few days.

**Pricing shape:** $500 one-time for the site, then roughly $100-150/month for
lead alerts and response automation. The thin version (Formspree webhook plus
Twilio) costs a few dollars a month to run, which is a far better margin than
reselling GoHighLevel.

## Domains

GitHub Pages, Tim's account, free, no custom domain until a client pays.
Do not buy a domain for a prospect. When a client pays, point a domain at the
existing repo - the URL changes, nothing gets rebuilt.
