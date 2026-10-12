# 07 — Trello to Xero Draft Invoicing

**Stack:** n8n · Trello · Gmail · PDF extraction · Xero API · JavaScript transformations  
**Status:** Active operational workflow, being refined (verified 12 October 2026)

## Overview

An order-to-accounting workflow that connects a Trello work-order queue with source purchase orders and Xero. When an eligible work order reaches a defined processing stage, the workflow gathers and reconciles supporting information, checks for duplicates and prepares a **draft** sales invoice for review.

This case study describes the workflow architecture without publishing customer records, supplier-specific product mappings, credentials or commercial terms.

## Operational problem

Creating draft invoices manually required information to be checked across order cards, emails, attached purchase orders and the accounting system. Inconsistent purchase-order layouts and subsequent amendments made direct copying error-prone.

The goal was to reduce repeat data entry while preserving an explicit draft/review boundary for financial records.

## Workflow at a glance

```text
Trello work order reaches a designated processing stage
    ↓
Read card and validate work-order details
    ↓
Find matching order correspondence and purchase-order attachment in Gmail
    ↓
Extract PDF text or handle email-only purchase orders
    ↓
Normalise line items, references and amendments
    ↓
Check Xero for existing invoices, customer and item matches
    ↓
Validate quantities, codes, shipping charge and tax/account treatment
    ↓
Create a Xero draft or update an existing eligible draft
    ↓
Attach the original supporting PO where available
    ↓
Accounting review / approval remains separate
```

## Implementation details

- **Event-driven:** an n8n Trello trigger feeds a stage-gate and card validation steps.
- **Document handling:** Gmail searches retrieve order correspondence; PDF extraction and an alternative email-only path handle different source formats.
- **Normalisation:** code nodes reconcile differences in customer order layouts, corrections and item identifiers.
- **Accounting checks:** Xero invoice, contact, item and account data inform customer matching, item validation, duplicate handling, shipping charges and GST/revenue treatment.
- **Controlled output:** the final action is confined to draft invoicing. It may create missing item records when required by validated mapping logic, so deployment and account permissions must be controlled carefully.
- **Audit trail:** the workflow includes an attachment step for the original purchase order.

## What this demonstrates

Multi-system integration; event triggers; data extraction; format normalisation; conditional routing; validation against a system of record; duplicate-prevention logic; draft-only accounting operations; and handling operational exceptions.

## Evidence and limitations

The saved n8n workflow was active on 12 October 2026 and recent execution history included successful runs. These are **execution-status observations**, not a claim that every invoice was independently audited or that a quantified amount of time was saved.

The implementation prepares drafts; it **does not automatically approve, email or reconcile invoices**. Accounting review and final authorisation remain separate.

No live credentials, customer details, exact mapping rules, invoice identifiers or internal source documents are shared here.

## Next evidence to add

An anonymised order-to-draft example, exception-path tests, a redacted architecture diagram, and measured before/after processing time once a reliable baseline is available.
