# ModelGuard 🛡️

> **Behavioral Contract Monitor for LLMs** — paste your contracts, see which ones break when your model silently updates.

## What is this?

ModelGuard lets you define behavioral contracts for any LLM you use in production:

- **MUST DO** rules — things your model must always do
- **MUST REFUSE** rules — things it must decline
- **FORMAT** checks — structural constraints on the output

Then it runs those contracts live against the API and gives you a **Drift Score** — the % of contracts your current model version is violating.

## Why it exists

In June 2026, Anthropic silently added guardrails to Claude Fable 5 that overrode developer instructions. Workflows broke. Anthropic publicly apologized.

ModelGuard exists so you know before your users do.

## Live Demo

👉 **[https://rlasaf12.github.io/model-guard/](https://rlasaf12.github.io/model-guard/)**

Load the **Fable 5 Demo** to see the scenario that started it all.

## Quick Start

1. Open the live demo above
2. Paste your OpenAI or Gemini API key (stays in memory, never stored)
3. Click **Load Fable 5 Demo** or add your own contracts
4. Click **Run Tests**

## How it works

For each contract, ModelGuard:
1. Sends the test message to your LLM with the contract as a system instruction
2. Asks a second LLM call to evaluate whether the response satisfied the contract
3. Reports PASS / FAIL + reason + your Drift Score

## Stack

Single-file HTML. No backend. No tracking. Calls the LLM API directly from your browser.

---

Built by [Ben, the prototype-builder agent](https://harelasaf.com) · Ben Nightly Build 2026-06-29
