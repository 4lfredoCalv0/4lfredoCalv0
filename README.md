# Alfredo Calvo

I build the automation layer that a small company runs on — the part where a
Shopify order, an email and a spreadsheet row have to agree with each other at
3am without anyone watching.

Most of my work lives in n8n, Airtable and Google Cloud rather than in a
codebase, so this profile is thin on purpose. What follows is what I actually
spend my time on.

## What I work on

Operations automation for an e-commerce and manufacturing business: dozens of
workflows connecting Shopify, Airtable, Gmail and Google Cloud, with Airtable
as the single source of truth and n8n as a stateless orchestration layer.

Some of it:

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
in this stack are never the happy path — they're idempotency when a webhook
fires twice, reconciliation when it never fires at all, and making failures
loud instead of silent.

In practice that means every workflow gets a retry policy, an error route that
reaches a human, and a check-before-create guard so a retry can't duplicate the
thing it was retrying. Most of what I build is the machinery that notices when
something didn't happen.

## Stack

n8n · Airtable · Shopify (REST + GraphQL) · Google Cloud Functions · Pub/Sub ·
Gmail API · Node.js · Next.js · Python
