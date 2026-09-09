# Alfredo Calvo

I build the automation layer that a small company runs on — the part where a
Shopify order, an email and a spreadsheet row have to agree with each other at
3am without anyone watching.

Most of that work lives in n8n, Airtable and Google Cloud rather than in a
codebase, so this profile is lighter than the hours behind it. The one thing
you can click through is Emerald.

## Emerald

An AI-first agency I'm building in Barranquilla, Colombia — and the site that
sells it, which I designed and wrote.

[**emerald**](https://github.com/4lfredoCalv0/emerald) ·
[live](https://emerald-co.vercel.app)

Next.js 14 with two conversational assistants on separate endpoints: one
answers questions about services anywhere on the site, the other handles
booking. Both stream through the Vercel AI SDK on Llama 3.3 70B via Groq,
picked for latency — a chat widget that takes three seconds to start answering
gets closed. The blog is MDX files with no CMS behind it, and form submissions
land in Notion, so there is no admin panel to maintain.

## Operations automation

For an e-commerce and manufacturing business: dozens of workflows connecting
Shopify, Airtable, Gmail and Google Cloud, with Airtable as the single source
of truth and n8n as a stateless orchestration layer.

- **Replaced a paid Gmail SaaS with two Cloud Functions.** Gmail push
  notifications over Pub/Sub label shared inboxes the instant mail arrives,
  instead of polling every five minutes. Watch subscriptions renew themselves
  before Gmail's 7-day expiry. The labeling step is idempotent, so the old
  system and the new one could run side by side during migration without ever
  double-labeling a message.

- **An affiliate program that runs itself.** Application intake, Shopify
  discount-code provisioning, per-product commission rules, and a payout
  pipeline. A daily job reconciles Shopify orders against recorded commissions
  and recreates the ones a dropped webhook would otherwise have lost.

- **Delivery estimates published from inventory.** Container arrival data turns
  into the delivery window a customer sees on the product page, without anyone
  editing it by hand.

## What I'm actually good at

Making no-code tools behave like production systems. The interesting problems
in that stack are never the happy path — they're idempotency when a webhook
fires twice, reconciliation when it never fires at all, and making failures
loud instead of silent.

In practice that means every workflow gets a retry policy, an error route that
reaches a human, and a check-before-create guard so a retry can't duplicate the
thing it was retrying. Most of what I build is the machinery that notices when
something didn't happen.

## Stack

**Building:** Next.js · React · TypeScript · Tailwind · Framer Motion ·
Vercel AI SDK
**Automating:** n8n · Airtable · Shopify (REST + GraphQL) · Google Cloud
Functions · Pub/Sub · Gmail API
**Also:** Node.js · Python · Notion API
