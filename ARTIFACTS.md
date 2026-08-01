# Artifacts: what exists and who has it

Living index of the Brandon-facing web pages we've published. **Update this
whenever an artifact is created or its URL changes.**

Artifacts update in place - editing one and republishing keeps the same URL, so
a link Brandon already has always shows the current version. **Only send a new
link when a genuinely new artifact is created.**

## Current artifacts

| # | Name | URL | Audience | Brandon has it? |
|---|---|---|---|---|
| 1 | **Client Tracker** | https://claude.ai/code/artifact/70fe4605-e8f6-4f37-b214-e961b617b595 | Brandon | **Yes** - sent 2026-08-01 |
| 2 | **The Business Playbook** | https://claude.ai/code/artifact/276b641f-7c2a-4aea-97f0-d6d1e8e75514 | Brandon | **NOT SENT** - send this |

### 1. Client Tracker
Per-client status. Salt Lake Gutter Guys and Grizzly Gutters: what's done, what's
blocked, what to send. Includes the 9 questions Brandon asks each client, how to
present the site, and the hosting/domain explanation in plain language.

**Changes as clients progress.** Brandon should re-check it, not re-request it.

### 2. The Business Playbook
General business strategy, not client-specific. What a gutter contractor earns
per job, what he already pays per lead on Angi/Thumbtack, our pricing and why it
holds up, what Podium and GoHighLevel actually are, the 90-day churn cliff, and
the rules we don't break.

**Created 2026-08-01 by splitting the general content out of the Client
Tracker.** Brandon has never seen this URL.

## Live client sites (not artifacts, but the other links Brandon sends)

| Site | URL |
|---|---|
| Salt Lake Gutter Guys | https://timothyshores.github.io/salt-lake-gutter-guys-website/ |
| Grizzly Gutters | https://timothyshores.github.io/grizzly-gutters-website/ |

These auto-deploy on push, roughly 45 seconds. **The URL never changes**, so
Brandon never needs a re-send after a site edit.

## Rules

- **One artifact per audience-and-purpose.** Don't fragment; a third artifact
  needs a real reason.
- **Editing beats creating.** Same URL, no re-send, no version confusion.
- **Record the send date** in the table above when Brandon gets a new link.
- Artifacts are private until shared. Brandon can view a shared link; he cannot
  edit.

## Source files

Artifacts are published from local HTML. To edit, change the file and republish
to the same path.

| Artifact | Source file |
|---|---|
| Client Tracker | `~/Documents/Code/grizzly-gutters-website/brandon-tracker.html` |
| Business Playbook | `~/Documents/Code/grizzly-gutters-website/business-playbook.html` |

Both source files are committed to the `grizzly-gutters-website` repo, so they
survive session end. To edit an artifact: change the file, then republish to the
same path so the URL is preserved.
