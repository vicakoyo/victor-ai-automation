# 08 — ChatGPT-Assisted Trello Work Order Management

**Stack:** ChatGPT · Trello integration / MCP tools · structured work-order templates  
**Status:** Operational AI-assisted process; human-reviewed (documented 12 October 2026)

## Overview

An AI-assisted order-administration process that uses a connected Trello account to help read, prepare and update work-order cards. Natural-language requests in ChatGPT can initiate supported Trello read/write actions without repeatedly transcribing the same details by hand.

**Important distinction:** this is a tool-assisted process involving ChatGPT and a human operator, not a claim that an unattended n8n workflow autonomously handles every order.

## Operational problem

Work orders had to follow consistent naming, descriptions, required fields and list placement. Manual drafting and cross-checking increased administrative effort and the risk of missing essential order information.

## Operating flow

```text
New order / relevant instruction
    ↓
ChatGPT reads relevant Trello board, list or card information
    ↓
Extracts and structures supported work-order fields
    ↓
Applies the applicable template and naming conventions
    ↓
Checks required information and flags missing / ambiguous fields
    ↓
Creates or updates a Trello card through an authorised tool
    ↓
Human review, corrections and subsequent operational processing
```

## Implementation approach

- **Direct integration:** ChatGPT's Trello tools can inspect boards, lists and card details and perform supported card actions.
- **Template control:** work-order descriptions are drafted in an established business format rather than an improvised free-text style.
- **Context-aware preparation:** existing board conventions and source instructions guide what should appear in each card.
- **Human checks:** uncertain specifications, client references and processing decisions should be confirmed before a consequential update.
- **Separation of roles:** Trello remains the operational source of truth; ChatGPT assists with interpreting and updating it.

## What this demonstrates

Natural-language interfaces to business tools; MCP/tool use; data structuring; process standardisation; human-in-the-loop control; and practical AI assistance embedded in everyday operations.

## Evidence and limitations

The operator has used this pattern to prepare and maintain work-order content. Trello read/write actions are available through the connected integration. This case study does **not** claim a fully autonomous system, an independently measured error reduction, or that every possible Trello action is supported.

The public description omits customer names, order numbers, internal naming algorithms and order-specific instructions.

## Next evidence to add

A fictional example showing input instructions, the resulting sanitised card template, validation decisions and a review checklist.
