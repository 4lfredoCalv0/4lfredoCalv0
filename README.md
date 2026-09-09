# Alfredo Calvo

I build automation systems that keep small businesses running without someone
watching them.

The interesting part isn't connecting Shopify to Airtable. It's making sure the
system still works when a webhook fires twice, an API goes down, a message
arrives late, or nothing happens at all.

My work sits somewhere between automation engineering, backend development and
AI-powered applications, mostly using n8n, Airtable, Google Cloud, Next.js and
TypeScript.

---

## Selected work

### Emerald

`Next.js 14` `TypeScript` `Tailwind` `Framer Motion` `Vercel AI SDK` `Groq` `Llama 3.3 70B`

[Repository →](https://github.com/4lfredoCalv0/emerald) ·
[Live site →](https://emerald-co.vercel.app/)

An AI-first automation agency I'm building in Barranquilla, Colombia — from the
ground up, including the website, infrastructure, conversational interfaces and
the automation layer behind it.

The site runs two separate conversational assistants: a **service assistant**
that answers questions about Emerald's services across the site, and a
**booking assistant** that handles appointment requests through a dedicated
flow. Both stream through the Vercel AI SDK, on Llama 3.3 70B via Groq where
low latency matters.

The blog is MDX instead of a CMS, and form submissions go directly into Notion.
Fewer systems to maintain, fewer things that can break.

### personal-ai-os

`Claude Code` `Obsidian` `n8n` `MCP`

[Repository →](https://github.com/4lfredoCalv0/personal-ai-os)

A personal assistant built as an operating system rather than a chatbot: an
orchestrator handles scheduling and routing, an Obsidian vault is the source of
truth, and Claude Code runs as the technical executor. Nothing reaches
long-term memory without human review.

### Automation infrastructure

`n8n` `Shopify` `Airtable` `Gmail API` `Pub/Sub` `Cloud Functions`

Production workflows for an e-commerce and manufacturing operation. Airtable is
the operational source of truth, n8n handles orchestration, and Google Cloud
handles the pieces that need custom code or event-driven infrastructure. Private
infrastructure, so there's no repository to link — the shape of it:

**Gmail → Pub/Sub → Cloud Functions.** Replaced a paid Gmail automation SaaS
with two Cloud Functions. Push notifications arrive through Pub/Sub and trigger
processing immediately instead of polling every five minutes. Watch
subscriptions renew themselves before the 7-day expiration, labeling is
idempotent so messages aren't processed twice, and the old and new systems could
run simultaneously during migration without conflict.

**Affiliate automation.** End-to-end: `Application → Approval → Shopify discount
code → Commission tracking → Reconciliation → Payout`. A daily reconciliation
job compares Shopify orders against recorded commissions and recreates the
records a lost webhook would otherwise have dropped. The important part isn't
the happy path — it's what happens when the happy path fails.

**Inventory → Delivery estimates.** Container arrival and inventory data becomes
the delivery window customers see on Shopify product pages. No manual updates,
no spreadsheet-to-website copy/paste.

---

## How I build

I care less about making an automation work once and more about making it safe
to run indefinitely. The patterns I reach for, in roughly that order of
importance:

* **Idempotency** — running something twice should not create two records.
* **Reconciliation** — scheduled checks should detect what event-driven systems missed.
* **Event-driven architecture** — react to events instead of constantly polling.
* **Check-before-create** — retries should never duplicate their side effects.
* **Error routing** — failures should reach a human instead of disappearing into a log.
* **Retries with backoff** — transient failures should recover on their own.
* **Observability** — the system should make failures obvious.

Most of what I build is the machinery that notices when something didn't
happen.

## Stack

**Building** `Next.js` `React` `TypeScript` `Tailwind CSS` `Framer Motion` `Node.js`

**AI** `Vercel AI SDK` `Groq` `Llama` `Ollama`

**Automation** `n8n` `Airtable` `Shopify REST API` `Shopify GraphQL API` `Notion API`

**Cloud** `Google Cloud Functions` `Pub/Sub` `Gmail API`

**Also** `Python` · `MDX` · `REST APIs` · `Webhooks` · `OAuth`

## Currently

Building Emerald, and experimenting with ways to combine AI agents, business
automation and conventional software into systems that small businesses can
actually operate.

## About this profile

Most of my interesting work doesn't fit neatly into a public repository —
production automation lives inside private business infrastructure. So this
profile is intentionally smaller than the amount of work behind it. The
repositories here are the parts I'm able to show.

Happy to talk about any of it: **calvo.alfredo2003@gmail.com**
