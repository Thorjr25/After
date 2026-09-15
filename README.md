
# AFTER

### The market closes. Information doesn't.

**AFTER** is an AI-powered after-hours information pricing agent built for event-driven trading workflows.

When traditional U.S. equity markets are closed, important information keeps arriving: earnings, company announcements, macroeconomic releases, Fed commentary, analyst actions, and geopolitical events.

AFTER analyzes that information, determines which assets may be affected, estimates the expected market reaction, compares it with related market movements, detects potential pricing dislocations, applies risk controls, and records the complete decision process.

---

## The Problem

U.S. equity market hours are limited.

Information isn't.

A major earnings report can arrive after the market closes. A Fed statement can change expectations overnight. A geopolitical event can move futures and related assets while the underlying equity market remains closed.

A trader must manually answer:

* What happened?
* Which assets are affected?
* How important is the information?
* What should the affected asset do?
* Are related markets already pricing it?
* Is there still a pricing gap?
* Is the opportunity worth the risk?

AFTER brings these steps into one workflow.

---

## Core Hypothesis

> **When significant information arrives while the traditional market is closed, related markets may partially reprice before the directly affected asset fully reflects the information.**

AFTER attempts to identify these temporary information-pricing gaps.

It does not treat an AI prediction as a guaranteed outcome.

---

## How AFTER Works

```text
INFORMATION
     ↓
EVENT DETECTION
     ↓
ASSET IDENTIFICATION
     ↓
AI IMPACT ANALYSIS
     ↓
EXPECTED MARKET REACTION
     ↓
REFERENCE MARKET ANALYSIS
     ↓
EXPECTED VS IMPLIED MOVE
     ↓
MISPRICING DETECTION
     ↓
RISK CHECK
     ↓
PAPER EXECUTION
     ↓
RUN RECORD
     ↓
OUTCOME
```

---

## Key Features

### After-Hours Scanner

Monitor important information such as:

* Earnings announcements
* Company announcements
* SEC/company disclosures
* Macro releases
* Fed statements and speeches
* Analyst actions
* Geopolitical events
* Breaking market news

---

### AI Information Analysis

AFTER uses an LLM as its reasoning layer.

The model helps:

* Understand unstructured financial information
* Classify events
* Identify affected assets
* Assess impact and relevance
* Evaluate surprise
* Develop an expected market-reaction thesis
* Identify uncertainty and invalidation conditions
* Explain why an opportunity may exist

Example:

```text
IMPACT       91/100
SURPRISE     82/100
RELEVANCE    96/100
CONFIDENCE   88%
```

---

### Expected Move Engine

AFTER asks:

> **What should happen next?**

Example:

```text
EVENT
AAPL earnings beat expectations

EXPECTED REACTION
AAPL → POSITIVE

EXPECTED MOVE
+4.1%

CONFIDENCE
88%
```

The system explains the thesis instead of presenting an unexplained signal.

---

### Relative Pricing Engine

AFTER compares the affected asset with related markets and proxies.

Example:

```text
NASDAQ FUTURES          +1.1%
TECH SECTOR             +0.8%
RELATED EXPOSURE        +0.2%

PRICING DISLOCATION
HIGH
```

The purpose is to determine whether information appears to be reflected consistently across related markets.

---

### Opportunity Radar

Rank potential opportunities by a combined opportunity score.

```text
01  AAPL    93
02  NVDA    78
03  TSLA    54
```

Each opportunity can show:

* Expected move
* Current implied move
* Confidence
* Information strength
* Risk level
* Reason for the opportunity

---

### Risk Gate

Before paper execution, AFTER checks:

* Confidence
* Liquidity
* Expected volatility
* Conflicting information
* Reference-market confirmation
* Position size
* Exposure limits
* Invalidation conditions
* Data freshness

Example:

```text
RISK CHECK

PASSED
```

or

```text
RISK CHECK

BLOCKED

Reason:
Conflicting reference markets and insufficient confidence.
```

---

# Run Records

## The AI Flight Recorder

Every meaningful AFTER run generates a **Run Record**.

A Run Record captures the complete lifecycle of an analysis or paper-trading decision.

Example:

```text
RUN #AF-00291

18:32:04
INFORMATION RECEIVED

18:32:07
EVENT CLASSIFIED

18:32:11
AAPL IDENTIFIED

18:32:15
IMPACT SCORE 91

18:32:19
REFERENCE MARKET ANALYZED

18:32:23
MISPRICING DETECTED

18:32:25
RISK CHECK PASSED

18:32:27
LONG SIGNAL GENERATED

18:32:32
PAPER ORDER SUBMITTED

18:32:39
RUN COMPLETE
```

Each record can contain:

```text
Run ID
Timestamp
Trigger
Event
Primary Asset
Related Assets
Impact Score
Surprise Score
Relevance Score
Confidence
Expected Direction
Expected Move
Reference Market Data
Implied Move
Calculated Dislocation
Risk Checks
Agent Decision
Execution Mode
Execution Details
Outcome
```

Run Records make AFTER auditable instead of presenting the AI as a black box.

---

## Run Replay

A completed run can be reviewed as a chronological decision story:

```text
INPUT
  ↓
INTERPRETATION
  ↓
IMPACT
  ↓
MARKET COMPARISON
  ↓
DISLOCATION
  ↓
RISK
  ↓
DECISION
  ↓
ACTION
  ↓
OUTCOME
```

The goal is to answer:

**What did AFTER see?**

**Why did it matter?**

**What did AFTER expect?**

**Where did it detect a pricing gap?**

**What risk checks were applied?**

**What action was taken?**

**What happened afterward?**

---

## Paper Trading

AFTER is designed around **paper execution first**.

A generated opportunity can be reviewed before a simulated trade is placed.

Example:

```text
SIGNAL
LONG AAPL

ENTRY REFERENCE
$XXX.XX

EXPECTED MOVE
+4.1%

RISK
MEDIUM

POSITION
$1,000

[ EXECUTE PAPER TRADE ]
```

After execution, the trade is automatically linked to a Run Record.

---

## AI + Deterministic Architecture

AFTER deliberately separates AI reasoning from numerical and risk-critical logic.

```text
            AFTER
              │
      ┌───────┴────────┐
      │                │
   INFORMATION       MARKET DATA
      │                │
      ▼                ▼
    LLM / AI      DETERMINISTIC ENGINE
      │                │
      └───────┬────────┘
              ▼
       PRICING GAP
              │
              ▼
          RISK GATE
              │
              ▼
      PAPER EXECUTION
              │
              ▼
         RUN RECORD
```

### LLM responsibilities

The LLM handles interpretation and reasoning:

* Event extraction
* Classification
* Asset relevance
* Impact reasoning
* Expected-direction thesis
* Risk-context interpretation
* Explainable analysis

### Deterministic responsibilities

Application logic handles:

* Market-data calculations
* Percentage changes
* Expected/implied comparisons
* Dislocation calculations
* Position sizing
* Risk thresholds
* Execution controls
* Run logging

This prevents the AI model from being the sole source of numerical truth.

---

## Example Scenario

Imagine an earnings report arrives after the U.S. equity market closes.

```text
AAPL REPORTS STRONG EARNINGS
```

AFTER analyzes the information.

```text
IMPACT       91
SURPRISE     82
RELEVANCE    96
CONFIDENCE   88
```

It identifies:

```text
PRIMARY
AAPL

RELATED
NASDAQ
QQQ
XLK
TECH SECTOR
```

Reference markets are then evaluated:

```text
NASDAQ FUTURES       +1.1%
TECH SECTOR           +0.8%
RELATED EXPOSURE      +0.2%
```

AFTER identifies a potential gap:

```text
EXPECTED MOVE
+4.1%

CURRENT IMPLIED MOVE
+0.8%

OPPORTUNITY
93
```

The risk engine evaluates the setup.

If the conditions pass:

```text
RISK CHECK
PASSED

PAPER EXECUTE
```

The complete process becomes a Run Record.

---

# Product Philosophy

AFTER is not designed to be another generic AI trading bot.

The product is built around a specific question:

> **What information arrived while the market was closed, and has the market priced it yet?**

The AI helps understand the information.

The market-data engine measures the pricing difference.

The risk engine controls the action.

Run Records preserve the evidence.

---

# Design

AFTER uses a kinetic financial-terminal aesthetic built around:

* Kinetic typography
* Oversized numerical information
* Acid-yellow accent
* High-contrast black/off-white interface
* Sharp borders
* Zero-radius geometry
* Sticky storytelling
* Scroll-triggered transitions
* Information marquees
* Large editorial layouts
* Hard visual state changes

The interface is intentionally different from conventional rounded-card fintech dashboards.

---

# Project Status

### Current

* Product concept and workflow designed
* After-hours information workflow designed
* AI reasoning architecture defined
* Expected-vs-implied pricing workflow defined
* Opportunity ranking designed
* Risk gate designed
* Paper execution flow designed
* Run Records architecture designed
* Run Replay concept designed
* Kinetic interface system designed

### Next

* Connect production information sources
* Connect market-data infrastructure
* Complete real LLM integration
* Expand historical validation
* Generate long-period strategy records
* Improve paper-trading evaluation
* Add broader asset/reference coverage

---

# Validation

AFTER is intended to validate its strategy using historical and paper-trading records.

Key metrics include:

```text
Return
Sharpe Ratio
Sortino Ratio
Maximum Drawdown
Win Rate
Turnover
Fees
Slippage
Funding
```

Every reported metric should be explicitly labeled as:

```text
OBSERVED
ESTIMATED
TARGETED
```

No performance number should be presented as historical evidence unless it has actually been generated and documented.

---

# Project Structure

Conceptually:

```text
AFTER/
├── app/
│   ├── dashboard/
│   ├── opportunities/
│   ├── catalysts/
│   ├── runs/
│   └── settings/
│
├── components/
│   ├── event/
│   ├── opportunity/
│   ├── terminal/
│   ├── runs/
│   ├── risk/
│   └── motion/
│
├── lib/
│   ├── ai/
│   ├── market/
│   ├── risk/
│   ├── execution/
│   └── records/
│
├── data/
│   └── demo/
│
└── README.md
```

Actual structure may vary according to the implementation.

---

# Getting Started

## 1. Clone the repository

```bash
git clone YOUR_REPOSITORY_URL
cd AFTER
```

## 2. Install dependencies

```bash
npm install
```

## 3. Configure environment variables

Create:

```text
.env.local
```

Example:

```env
AI_PROVIDER=
AI_MODEL=
AI_API_KEY=
```

Never commit API keys.

## 4. Start the development server

```bash
npm run dev
```

Open the local application in your browser.

---

# Demo Mode

AFTER should support a demo environment using synthetic market and event data.

This allows the complete workflow to be demonstrated without depending on live market conditions.

Demo mode should clearly identify itself as:

```text
SYSTEM
DEMO
```

Real AI mode should clearly identify itself as:

```text
SYSTEM
REAL AI
```

The application must never present synthetic outputs as real market data.

---

# Disclaimer

AFTER is a research and trading-workflow prototype.

Its signals and analyses are experimental and should not be considered financial advice or guaranteed predictions.

Historical or simulated results do not guarantee future performance.

---

# Built For

**Bitget AI × Crypto Hackathon S2**

**Track:** Alpha Factory

**Sub-theme:** After-hours information pricing

---

## Core Idea

```text
THE MARKET CLOSES.

INFORMATION DOESN'T.

AFTER KEEPS WATCHING.
```
