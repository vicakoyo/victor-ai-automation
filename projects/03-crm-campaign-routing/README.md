# 03 — CRM Campaign Routing Automation

**Platform:** Make.com, Pipedrive, Lemlist  
**Status:** Workplace implementation / portfolio documentation in progress

## Overview

A workflow used to move sales and marketing leads between CRM and outreach systems based on defined routing conditions.

The automation monitored information in Pipedrive, retrieved the associated contact and used conditional routing to place appropriate leads into Lemlist campaigns.

## Business Problem

Manually checking lead status across CRM records and deciding which outreach campaign each contact should enter creates repetitive administrative work and increases the risk of missed or inconsistent follow-up.

The workflow was designed to automate that routing process while preserving clear decision rules.

## Workflow

```text
Pipedrive Deal
      ↓
Retrieve Contact
      ↓
Evaluate Data
      ↓
Routing Rules
      ↓
Select Campaign
      ↓
Lemlist
