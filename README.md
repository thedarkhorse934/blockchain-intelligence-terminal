# IDMON — Digital Asset Intelligence ₿

> **Bitcoin-native market intelligence, prospective research, and evidence-gated decision support.**

IDMON is an independent research and engineering project exploring whether Bitcoin-native intelligence can improve the quality of real market decisions.

The system combines direct Bitcoin Core ingestion, on-chain behavioural intelligence, Hyperliquid and Deribit perpetual-futures data, ETF and macro context, prospective quantitative research, and a decision-research layer that can explicitly return **TRADE** or **NO_TRADE**.

The production codebase remains private. This repository is the public technical showcase for the project.

**→ [Read the full IDMON case study](docs/IDMON_CASE_STUDY.md)**

---

## What IDMON Does

IDMON is designed to answer progressively harder questions:

- What happened on-chain?
- Is the activity unusual in context?
- What is happening in BTC derivatives markets at the same time?
- What evidence supports or contradicts a market thesis?
- What happened after comparable observations in the prospective dataset?
- Is there enough evidence to justify a trade, or is **NO_TRADE** the correct result?

The project deliberately avoids turning every interesting event into a bullish or bearish signal.

---

## Architecture

```text
                        BITCOIN CORE
                             │
                             ▼
                  TRANSACTION INGESTION
                             │
                             ▼
                 BITCOIN INTELLIGENCE
                  ├─ Exchange flows
                  ├─ Whale activity
                  ├─ Dormancy
                  ├─ Entity behaviour
                  ├─ Route recurrence
                  ├─ Activity episodes
                  ├─ Relay campaigns
                  └─ Related movements
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
     HYPERLIQUID          DERIBIT         MARKET CONTEXT
     BTC PERPS            BTC PERPS       ETF / MACRO
          │                  │                  │
          └──────────────────┼──────────────────┘
                             ▼
                    PROSPECTIVE RESEARCH
                             │
                             ▼
                       QUANT LAYER
                             │
                             ▼
                       DECISION LAB
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
                  TRADE            NO_TRADE
```

Each evidence domain remains separately inspectable rather than being collapsed into a single opaque market score.

---

## Bitcoin Intelligence

IDMON uses a locally operated Bitcoin Core node as its primary Bitcoin data source.

Current Bitcoin-native research includes:

- significant BTC transfers;
- exchange deposits and withdrawals;
- source and destination attribution;
- coin dormancy and input age;
- entity behaviour;
- source, destination, and route recurrence;
- entity-relative transfer size;
- activity episodes;
- relay campaigns;
- exchange-to-exchange movement;
- related transaction structures;
- structured intelligence cases.

The objective is not simply to detect a large transaction. It is to understand whether that transaction is unusual **for the entity, route, market state, and historical context in which it occurred**.

---

## Derivatives Market Structure

IDMON prospectively collects BTC perpetual-futures data from **Hyperliquid** and **Deribit**.

The current market-structure layer includes:

- open interest;
- funding;
- mark and oracle pricing;
- basis / premium / discount;
- rolling volume;
- 1h / 6h / 24h structural changes;
- cross-venue comparison.

The system deliberately avoids unsupported shortcuts:

> Falling open interest does not automatically prove liquidation.
>
> Positive funding does not prove the market is bullish.
>
> Cross-venue disagreement is not automatically actionable.

Derivatives data is treated as evidence first, not as a trading signal by default.

---

## Prospective Research and T0

A major focus of IDMON is avoiding hindsight bias.

The project uses **T0 — time zero**: the exact moment at which a research observation or decision is created.

Evidence available at T0 is frozen. Information learned later cannot be silently inserted into the original observation.

```text
                    T0
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
       6h           24h          72h
     outcome       outcome      outcome
```

This allows IDMON to measure what happened afterwards without reconstructing yesterday using today's knowledge.

---

## Quant Research

Prospectively captured Bitcoin events are grouped into comparable research cohorts and measured against subsequent BTC outcomes.

Research dimensions currently include characteristics such as:

- transaction amount;
- entity-relative transfer size;
- entity historical percentile;
- route and counterparty novelty;
- recurrence;
- dormancy;
- episode structure;
- relay behaviour.

These cohorts are explicitly treated as **descriptive research** unless stronger evidence is established.

Sample maturity does not establish statistical significance, causation, or predictive edge.

---

## Decision Lab

Decision Lab is IDMON's prospective decision-research environment.

Before a hypothetical trade can pass, the system records and checks:

- directional hypothesis;
- confidence and horizon;
- thesis;
- counter-evidence;
- invalidation conditions;
- evidence freshness;
- timestamp integrity;
- evidence breadth;
- cross-venue agreement;
- prospective-only integrity.

The output can be:

```text
TRADE
```

or:

```text
NO_TRADE
```

`NO_TRADE` is intentionally treated as a valid outcome when the evidence is weak, conflicting, stale, or incomplete.

The purpose is not to make IDMON produce more trades. It is to test whether disciplined evidence gates can improve the quality of decisions.

---

## From BIT to IDMON

IDMON began as **BIT — Blockchain Intelligence Terminal**.

BIT's original focus was turning raw Bitcoin transaction activity into structured, explainable on-chain intelligence.

As the project developed, its scope expanded beyond transaction monitoring into derivatives market structure, ETF and macro context, prospective quantitative research, and evidence-gated decision testing.

The project therefore evolved into **IDMON — Digital Asset Intelligence** to better reflect the system it is becoming.

> **BIT represents the project's origins. IDMON represents its broader research direction.**

The Bitcoin intelligence work built during the BIT phase remains the foundation of IDMON rather than a discarded earlier project.

---

## Research Principles

IDMON is built around a few deliberately conservative rules:

- **Unknown remains unknown.**
- **Address linkage does not automatically establish ownership.**
- **Bitcoin movement does not automatically establish selling.**
- **An exchange deposit does not prove a sale occurred.**
- **Market movement does not prove causation.**
- **Missing or stale evidence is not neutral evidence.**
- **Descriptive relationships are not automatically predictive edge.**
- **AI interpretation cannot override deterministic evidence.**
- **NO_TRADE is a legitimate research result.**

These constraints are part of the product, not caveats to be hidden.

---

## Current Research Direction

The next major research phase moves from studying isolated transaction families toward studying **complete market states**.

Instead of asking only:

> What happened after an unusual exchange deposit?

IDMON increasingly asks:

> When Bitcoin price structure, Hyperliquid positioning, Deribit structure, ETF context, market regime, and relevant on-chain behaviour looked like this at T0, what happened afterwards?

The intended research loop is:

```text
OBSERVE
   ↓
UNDERSTAND
   ↓
TEST
   ↓
QUANT RESEARCH
   ↓
DECISION LAB
   ↓
TRADE / NO_TRADE
   ↓
MEASURE OUTCOME
   ↓
LEARN
```

No assumption is made that a usable predictive edge must exist. The research is designed to investigate whether one exists.

---

## Technology

Current technologies and workflows include:

- JavaScript / Node.js
- Bitcoin Core
- Bitcoin JSON-RPC
- Hyperliquid market data
- Deribit market data
- canonical BTC price history
- US spot Bitcoin ETF context
- US macroeconomic context
- NDJSON prospective research stores
- deterministic research and decision engines
- Git / GitHub
- AI-assisted interpretation with evidence constraints

AI is used as an interpretation layer. Deterministic collection, timestamps, evidence, and research integrity remain the source of truth.

---

## Why Is the Production Repository Private?

The production codebase contains active intelligence logic, entity datasets, classification systems, heuristics, prospective research data, and experimental decision infrastructure.

This public repository therefore documents the project's architecture, research philosophy, capabilities, and development direction without exposing the full private implementation.

**→ [Full technical and research case study](docs/IDMON_CASE_STUDY.md)**

---

## About the Builder

IDMON is designed and built by **Darkhorse934**.

My professional background is analytical rather than traditional software engineering, with more than a decade of experience working with complex evidence, regulation, individual cases, and uncertain information.

I am currently developing my skills across three connected areas:

**Blockchains · Bitcoin · Perpetual Futures**

I am particularly interested in opportunities involving:

**Bitcoin research · Digital-asset intelligence · On-chain analysis · Crypto market research · Research tooling · Data-driven product development**

---

## Status

**Active independent research project — 2026**

IDMON's current research outputs are experimental and should not be interpreted as financial advice or evidence of guaranteed trading performance.

---

> **Understand the evidence first. Decide whether action is justified second.**
