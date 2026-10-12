# 09 — Australia Post Shipping Preparation & Trello Document Filing

**Stack:** n8n · Trello · Australia Post MyPost CSV format · Google Drive · n8n Forms · HTTP APIs  
**Status:** Two active operational workflows (verified 12 October 2026)

## Overview

Two connected shipping-administration workflows help an Australian e-commerce operation prepare postage data and then attach shipping records to the appropriate Trello order.

They automate **preparation and record filing**, not the purchase of postage. Shipping labels and tax invoices are obtained separately and supplied to the second workflow.

## Operational problem

Shipping administration required repeated re-entry of order and address data into a postage system, then manual identification of the original Trello work order to store the label and tax invoice.

The two-workflow approach separates data preparation from document filing.

## Workflow A — Prepare MyPost CSV

```text
Operator starts an n8n form
    ↓
Read eligible order cards from a Trello list
    ↓
Retrieve order/card details and shipping instructions
    ↓
Validate package details, destination and address fields
    ↓
Route unsupported or incomplete records away from CSV creation
    ↓
Build rows in the required MyPost CSV structure
    ↓
Generate CSV file and store in Google Drive
    ↓
Operator handles the postage-system import / purchase separately
```

**Controls:** The saved workflow checks package-data completeness, parses address fields and includes destination-specific restrictions, including a US-order branch. The presence of a control in the workflow should not be confused with independently validated postal eligibility for every address.

## Workflow B — Attach shipment documents to Trello

```text
Operator starts a second n8n form
    ↓
Find the latest prepared CSV in Google Drive
    ↓
Read order rows and choose the relevant order
    ↓
Supply existing shipping-label and tax-invoice PDF files
    ↓
Find and verify the matching Trello card
    ↓
Upload both documents as card attachments
    ↓
Apply the relevant processing label
```

## Why two workflows?

A staged design makes an important process boundary visible: **CSV generation is not label purchasing**. After the postage operation has produced the documents, the second workflow handles systematic recordkeeping. This makes the human action explicit instead of disguising it as an API integration that has not been built.

## What this demonstrates

Trello API retrieval; structured shipping-data extraction; address validation; branching and exception control; CSV file generation; cloud-file storage; form-driven processing; PDF attachment uploads; and traceability across operational tools.

## Evidence and limitations

Both n8n workflows were active on 12 October 2026, with recent successful execution records. The configuration confirms CSV preparation, Google Drive handoff, matching the target Trello card and uploading shipping documents.

This documentation **does not claim direct Australia Post API label purchase, real-time postage pricing, automated carrier booking or universal address verification**. Successful workflow execution alone is not proof that every parcel was dispatched or every document matched correctly.

No real customer addresses, labels, purchase records, credentials or private Trello data are published.

## Next evidence to add

A fictional shipment example, sample redacted CSV schema, exception checklist, test evidence for card matching and comparative handling-time measurements.
