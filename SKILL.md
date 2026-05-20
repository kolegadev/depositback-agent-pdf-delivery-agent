# PDF Delivery Agent

> **Agent**: `depositback-agent-pdf-delivery-agent`  
> **Group**: Operations  
> **Product**: DepositBack — Security Deposit Demand Letter Service

## Purpose

Assembles the $19.99 state-specific security deposit demand letter or $39.99 small claims prep pack based on the 6-question form data. Emails PDF via Brevo with delivery tracking.

## DepositBack Context

DepositBack is a single-page, no-signup transactional product for US renters seeking to recover security deposits. The entire customer journey fits on one URL: landing page → 6-question form → Revolut payment → PDF emailed. Conversion rate target: **4% visitor-to-purchase minimum**.

## Inputs

- Purchase events from purchase-orchestrator
- Form data (name, address, deposit amount, state, landlord, deadline)

## Outputs

- Delivery confirmations → funnel-analyst inbox
- Failed delivery alerts → operations/escalation

## Human Escalation Points 🛑

- Template errors for specific states
- Email bounce rates >5%
- PDF generation failures

## Skills

| Skill | Description | Status |
|-------|-------------|--------|
| `noop` | Health check / pipeline verification | ✅ Active |
| `execute` | Primary function for this agent | 🔧 Planned |

## Workflow

1. Poll `data/inbox/` for task manifests from upstream agents.
2. Resolve required skills (local `skills/` or ClawHub fallback).
3. Execute workflow.
4. Write artifacts to `data/outbox/`.
5. Update `data/state.json`.

## Runtime

```bash
pip install -r requirements.txt
python runtime/main.py
```
