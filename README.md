# Chakula v1 (Archived)

An AI-powered recipe generator and grocery price research tool that I built
as lead developer. This repository preserves the original v1 codebase for
reference. **It is not actively maintained and is not deployable in its
current state.**

An active rebuild — Chakula v2 — is in progress at
[chakula-v2](https://github.com/joeehis1/chakula-v2).

## What Chakula v1 did

Users signed up, provided personal data (age, height, weight, activity level)
to calculate their Total Daily Energy Expenditure (TDEE), and selected
pantry items and food preferences. The application then used the OpenAI API
to generate personalized recipes calibrated to the user's caloric needs and
available ingredients. Generated recipes were saved to a shared library
visible across all users.

A separate feature used Puppeteer to scrape grocery store websites,
retrieving prices for items the user intended to buy.

## Stack

- Node.js + Express
- Server-rendered with EJS templates
- MongoDB via Mongoose
- OpenAI API for recipe generation
- Puppeteer for headless browser scraping
- Session-based authentication with passport
- Deployed on Render (v1 deployment since retired)

## Why it's archived

Two reasons, in order of importance:

1. **Architectural lesson:** In building v1, I came to see that it bundled
   two distinct products — AI recipe generation and grocery price research —
   into a single codebase. The two features shared users and database but
   little else, and the coupling was more cost than benefit. The v2 rebuild
   is deliberately scoped to focus on the AI recipe generation product as
   the core.

2. **Practical:** The original repo was tied to a now-deactivated account.
   Re-hosting the code here preserves it as a reference artifact.

## What I took from v1 into v2

- Keep: TDEE calculation, pantry-aware recipe prompting, shared recipe library
- Change: TypeScript throughout, PostgreSQL instead of MongoDB, Next.js
  (App Router) instead of server-rendered EJS, streaming LLM responses,
  proper test coverage, CI pipeline
- Cut: Puppeteer-based grocery price scraping (separate product)

## Running v1 (not recommended)

This code is preserved as reference. If you want to actually run it, you
would need to: provide an OpenAI API key, set up a MongoDB instance,
configure Puppeteer hosting (Render free tier does not support it), and
debug any dependencies that have since moved. The rebuild (v2) is the
actively maintained version.
