# aml-investigation-agent

LLM agent that investigates AML transaction alerts, backed by an ML risk score and human review.

## Overview

Banks generate large volumes of transaction-monitoring alerts, most of them false positives. Each
alert requires an analyst to investigate and write a report. This project prepares that work:
a machine-learning model ranks alerts by risk, an LLM agent investigates the high-risk ones with
dedicated tools and drafts a report citing the transactions involved, and an analyst makes the
final decision.

```
Transactions -> data pipeline -> ML risk score -> LLM agent (investigation + report) -> human review
```

## Data

The project uses synthetic, labelled transaction datasets. No real personal or banking data is
involved. Results measure behaviour on synthetic data and do not establish performance on real
bank data.

## Repository layout

| Path | Content |
|---|---|
| `src/aml_agent/` | Package: pipeline, risk model, agent, tools |
| `notebooks/` | Data exploration |
| `tests/` | Unit tests |
| `docs/` | Architecture decisions and evaluation results |
| `data/` | Local datasets (not versioned) |

## Configuration

Copy `.env.example` to `.env` and fill in the values. The `.env` file is never committed.
