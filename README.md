# Alfredo Calvo

**AI & Automation Engineer**

I build AI-powered automation systems for businesses — from event-driven backend
infrastructure to the interfaces people actually use.

The interesting part isn't connecting Shopify to Airtable. It's making sure the
system still works when a webhook fires twice, an API goes down, a message
arrives late, or nothing happens at all.

I work at the intersection of automation engineering, backend development and
AI-powered applications, mostly using n8n, Google Cloud, Next.js and TypeScript.

---

## Selected work

### Emerald

`Next.js 14` `TypeScript` `Tailwind` `Vercel AI SDK` `Streaming` `Groq` `MDX`

[Repository →](https://github.com/4lfredoCalv0/emerald) ·
[Live site →](https://emerald-co.vercel.app/)

An AI-first automation agency I'm building from the ground up, including the
website, infrastructure, conversational interfaces and automation layer behind
it.

The site runs two separate conversational assistants: a service assistant that
answers questions about Emerald's services, and a booking assistant that turns a
conversation into a completed booking — writing the lead to Notion and
triggering the notification without leaving the chat. Both stream through the
Vercel AI SDK, using Llama 3.3 70B via Groq where low latency matters.

The blog uses MDX instead of a CMS, and form submissions go directly into
Notion. Fewer systems to maintain, fewer things that can break.

### personal-ai-os

`Claude Code` `Obsidian` `n8n` `MCP`

[Repository →](https://github.com/4lfredoCalv0/personal-ai-os)

A personal assistant built as an operating system rather than a chatbot. Claude
Code is the agent, an Obsidian vault is the source of truth, and n8n runs what
has to happen unattended. Nothing reaches long-term memory without human review.

### Automation infrastructure

`n8n` `Shopify` `Airtable` `Gmail API` `Pub/Sub` `Google Cloud Functions`

Production workflows for an e-commerce and manufacturing operation. Airtable is
the operational source of truth, n8n handles orchestration, and Google Cloud
handles the pieces that need custom code or event-driven infrastructure.

**Gmail → Pub/Sub → Cloud Functions.** Replaced a paid Gmail automation SaaS
with two Cloud Functions. Push notifications trigger processing immediately
instead of polling every five minutes. Watch subscriptions renew automatically
before expiration, and idempotent labeling prevents duplicate processing.

**Affiliate automation.**
`Application → Approval → Shopify discount → Commission tracking → Reconciliation → Payout`
A daily reconciliation job compares Shopify orders against recorded commissions
and recreates the records a lost webhook would otherwise have dropped.

**Inventory → Delivery estimates.** Container arrival and inventory data becomes
the delivery window customers see on Shopify product pages. No manual updates,
no spreadsheet-to-website copy/paste.

---

## How I build

I care less about making an automation work once and more about making it safe
to run indefinitely. The patterns I reach for:

* **Idempotency** — running something twice should not create two records. In
  practice that means checking before creating, so a retry can't duplicate its
  own side effects.
* **Event-driven architecture** — react to events instead of constantly polling.
* **Reconciliation** — scheduled checks should detect what event-driven systems
  missed.
* **Retries with backoff** — transient failures should recover automatically.
* **Error routing** — failures should reach a human instead of disappearing into
  a log.
* **Observability** — the system should make failures obvious.

**Most of what I build is the machinery that notices when something didn't
happen.**

## Stack

**Building** `Next.js` `React` `TypeScript` `Tailwind CSS` `Framer Motion` `Node.js`

**AI** `Vercel AI SDK` `Groq` `Llama` `Ollama` `MCP`

**Automation** `n8n` `Airtable` `Shopify REST API` `Shopify GraphQL API` `Notion API`

**Cloud** `Google Cloud Functions` `Pub/Sub` `Gmail API`

**Engineering** `Python` `REST APIs` `GraphQL` `Webhooks` `OAuth` `Event-driven systems`

## Currently

Building Emerald and experimenting with ways to combine AI agents, business
automation and conventional software into systems that small businesses can
actually operate.

## About this profile

A lot of the work behind this profile runs inside private business
infrastructure, so not everything can be open-sourced. The repositories here are
the parts I'm able to show.

[calvo.alfredo2003@gmail.com](mailto:calvo.alfredo2003@gmail.com)
