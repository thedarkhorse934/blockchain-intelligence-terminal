# IDMON — Digital Asset Intelligence

> Bitcoin-native market intelligence, prospective research, and decision-support infrastructure.

IDMON is an independent research and engineering project exploring whether Bitcoin-native intelligence can improve the quality of real market decisions.

The project began as a system for detecting and interpreting significant Bitcoin transactions. It has since developed into a broader research platform combining Bitcoin Core data, on-chain behavioural intelligence, perpetual-futures market structure, ETF and macro context, prospective quantitative research, and evidence-gated decision testing.

The central question behind IDMON is:

> **What is happening in the Bitcoin market, why might it matter, and is there enough evidence to justify taking action?**

---

## The Problem

Large Bitcoin transactions are easy to sensationalise.

A transfer of 1,000 BTC to an exchange may be described as a whale preparing to sell.

Movement from an old wallet may immediately be labelled bearish.

Falling perpetual-futures open interest may be described as liquidation.

Those conclusions often go further than the available evidence supports.

IDMON is designed around a different principle:

> **Observe first. Preserve uncertainty. Build evidence prospectively. Test what actually happens afterwards.**

A Bitcoin transfer is therefore not automatically treated as selling.

Address relationships are not automatically treated as common ownership.

Missing evidence is not interpreted as neutral evidence.

Historical relationships are not presented as predictive signals simply because they exist.

---

## System Architecture

IDMON combines several independent evidence domains.

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

These evidence domains remain separately inspectable rather than being collapsed into a simplistic bullish/bearish master score.

### Bitcoin-Native Intelligence

IDMON runs against a local Bitcoin Core node and processes Bitcoin blocks and transactions directly.

The Bitcoin intelligence layer analyses characteristics including:

- significant BTC transfers;
- exchange-related deposits and withdrawals;
- source and destination attribution;
- coin dormancy and input age;
- entity behaviour;
- destination, source, and route recurrence;
- activity unusual relative to an entity's own history;
- multi-transfer activity episodes;
- relay campaigns;
- exchange-to-exchange movements;
- related or sibling transaction structures;
- case and investigation history.

The objective is not simply to identify large transactions.

It is to understand whether a transaction is unusual in context.

For example, a 1,000 BTC transfer may be significant in absolute terms, but IDMON can also ask:

Is 1,000 BTC unusual for this particular entity?

That distinction has become increasingly important in the project's quantitative research.

### Derivatives Market Structure

IDMON collects prospective BTC perpetual-futures data from Hyperliquid and Deribit.

The current market-structure layer includes information such as:

- ₿ price
- Open interest
- Funding
- Mark price
- Oracle price
- Basis / premium / discount
- Rolling volume
- Cross-venue changes
- 1h / 6h / 24h structure


The system deliberately avoids unsupported interpretations.

For example:

- Falling open interest ≠ proven liquidation
- Positive funding ≠ proof that the market is bullish
- Cross-venue disagreement ≠ automatically actionable
- Derivatives information is treated as market evidence rather than a trading signal by default.

### T0 — Prospective Research Integrity

A major focus of IDMON is avoiding hindsight bias.

The project uses the concept of T0 — time zero.

T0 is the exact point at which a research observation or decision is created.

The evidence available at that moment is frozen.

                ```  T0
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
       6h           24h          72h
     outcome       outcome      outcome

     ```

Information learned after T0 cannot silently be inserted into the original research record.

This means IDMON cannot reconstruct yesterday's setup using information that only became available today.

Subsequent Bitcoin outcomes are instead appended prospectively.


### Prospective Research Dataset
#### Snapshot — 14 September 2026

At this stage of development, IDMON had accumulated:

```

Prospective Intelligence V2 vectors:       782
Independent capture cohorts:               601

Aligned research captures:                 832
Reference prices available:                832 / 832

Aligned outcome windows observed:        2,342
Aligned outcome windows pending:           154
Aligned outcome windows unavailable:         0

Malformed V2 vectors:                         0
Invalid V2 joins:                             0
Aligned T0 mismatches:                        0
Rejected future features:                     0

```

Seven 24-hour research families had reached the project's internal
DESCRIPTIVE sample threshold:

- Exchange Deposit
- Exchange Withdrawal
- Exchange Deposit Episode
- Exchange Withdrawal Episode
- Relay Campaign
- Repeated Route Episode
- Exchange To Exchange

The threshold represents dataset maturity only.

It does not establish statistical significance, causation, or predictive edge.

### Quantitative Research

IDMON groups prospectively captured Bitcoin events into comparable research cohorts and measures subsequent Bitcoin behaviour.

Research can then be segmented using semantic characteristics such as:

- Transaction amount
- Route novelty
- Counterparty novelty
- Destination recurrence
- Source recurrence
- Entity-relative transfer size
- Entity historical percentile
- Episode transfer count
- Episode BTC volume
- Relay characteristics
- Dormancy

One current research question examines entity-relative abnormality.

Instead of asking only:

Was this a large Bitcoin transfer?

IDMON can ask:

Was this transfer unusually large relative to the historical behaviour of that entity?

For example, research cohorts can distinguish transfers occurring above an entity's historical 90th percentile from more typical transfers.

Early descriptive work suggests entity-relative abnormality may sometimes be more interesting for subsequent movement magnitude than raw BTC amount alone.

Directional evidence remains mixed.

The project therefore does not currently interpret this relationship as a trading signal.

### Decision Lab

Decision Lab is IDMON's prospective decision-research environment.

Its purpose is not to force the system to produce trades.

Its purpose is to test whether available evidence is strong enough to justify one.

Before a hypothetical trade can pass, the system records:

- Directional hypothesis
- Confidence
- Time horizon
- Prospective thesis
- Counter-evidence
- Invalidation conditions
- Evidence timestamps
- Canonical BTC reference
- Derivatives context
- On-chain context
- Research context

Deterministic gates then assess factors including:

- T0 integrity
- Evidence freshness
- Venue timestamp alignment
- Evidence breadth
- Cross-venue conflict
- Thesis definition
- Counter-evidence
- Invalidation
- Directional confidence
- Prospective-only integrity

Decision Lab can return:

TRADE

or:

NO_TRADE

NO_TRADE is deliberately treated as a valid successful outcome.

### Example Decision

One prospective Decision Lab record captured the following setup:

Hypothesis:     DOWN
Confidence:     LOW
Horizon:        24H

BTC at T0:      $78,373

Decision:       NO_TRADE

The downside hypothesis subsequently missed its primary horizon:

6h outcome:     +0.13%
24h outcome:    +1.18%
72h outcome:    -1.31%

The later negative 72-hour result does not retrospectively rescue the original 24-hour hypothesis.

At T0, however, Decision Lab had already rejected the setup as a trade because:

Directional confidence was insufficient

and

Hyperliquid / Deribit evidence contained
material cross-venue disagreement

This example captures the purpose of the system.

IDMON is not being built to demonstrate that every market interpretation is correct.

It is being built to investigate whether disciplined evidence and risk gates can prevent weak interpretations from becoming bad decisions.

### Research Principles

Several rules sit underneath the project:

Unknown remains unknown.

Address linkage does not automatically establish ownership.

Bitcoin movement does not automatically establish selling.

An exchange deposit does not prove a sale occurred.

Market movement does not prove causation.

Missing or stale evidence is not neutral evidence.

Descriptive relationships are not automatically predictive edge.

AI interpretation cannot override deterministic evidence.

NO_TRADE is a legitimate research result.

These constraints are intentional.

They are part of the product rather than limitations to be hidden.

### Technology and Data

IDMON is primarily developed in Node.js and runs continuously on a Mac mini research environment.

Core infrastructure currently includes:

- Bitcoin Core
- Node.js
- Bitcoin JSON-RPC
- Hyperliquid market data
- Deribit market data
- Canonical BTC price history
- US spot Bitcoin ETF context
- US macroeconomic context
- NDJSON prospective research stores
- Deterministic research and decision engines
- AI-assisted interpretation with evidence constraints

The system is designed around deterministic collection and evidence processing first, with AI used as an interpretation layer rather than the source of truth.

### Current Research Direction

The next major research phase moves beyond studying individual transaction families toward studying complete market states.

Instead of asking only:

What happened after an unusual exchange deposit?

IDMON increasingly aims to investigate:

When Bitcoin price structure, Hyperliquid positioning, Deribit structure, ETF context, market regime, and relevant on-chain behaviour looked like this at T0, what happened afterwards?

The intended research path is:

OBSERVE
   │
   ▼
UNDERSTAND
   │
   ▼
TEST
   │
   ▼
QUANT RESEARCH
   │
   ▼
DECISION LAB
   │
   ▼
TRADE / NO_TRADE
   │
   ▼
MEASURE OUTCOME
   │
   ▼
LEARN

No assumption is made that a usable predictive edge must exist.

The research is designed to discover whether one exists.

### Long-Term Objective

The long-term objective is an explainable Bitcoin-native intelligence system capable of answering:

What is happening?

What evidence matters?

What contradicts the thesis?

What would invalidate it?

What has happened historically under comparable conditions?

Is there enough evidence to trade — or should nothing be done?


### About the Builder

IDMON is designed and built by Darkhorse934.

My professional background is analytical rather than traditional software engineering.

I have more than a decade of experience working with complex evidence, regulation, individual cases, and uncertain information in an advisory environment.

IDMON began as a way to deepen my understanding of Bitcoin while building something practical.

It has developed into a broader technical and research project spanning Bitcoin infrastructure, blockchain analysis, derivatives market structure, prospective quantitative research, and evidence-based decision systems.

I am currently developing my skills across three connected areas:

Blockchains · Bitcoin · Perpetual Futures

I am interested in opportunities involving:

Bitcoin research · Digital-asset intelligence · On-chain analysis · Crypto market research · Research tooling · Data-driven product development

### Project Status

IDMON remains an active independent research project.

Current research outputs are descriptive and experimental.

Nothing produced by the system should be interpreted as financial advice or as evidence of guaranteed trading performance.

### From BIT to IDMON

IDMON began as BIT — Blockchain Intelligence Terminal, originally focused on turning raw Bitcoin transaction activity into structured on-chain intelligence.

As the project developed, its scope expanded beyond transaction monitoring. Bitcoin-native intelligence remains the foundation, but the system now incorporates derivatives market structure, ETF and macro context, prospective quantitative research and evidence-gated decision testing.

The project therefore evolved into IDMON — Digital Asset Intelligence to better reflect its broader research objective.

BIT represents the project's origins; IDMON represents the system it is becoming.
