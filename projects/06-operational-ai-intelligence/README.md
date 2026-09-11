# Operational AI Intelligence System

**Platform:** Make.com • AI / LLM Processing • Business Meeting Data  
**Status:** Workplace implementation / portfolio documentation in progress  
**Project Type:** AI-Assisted Operational Intelligence • Workflow Automation • Continuous Improvement

---

## Overview

The Operational AI Intelligence System is a workplace automation designed to turn recurring organisational information into useful intelligence about operational problems and potential opportunities for AI-enabled improvement.

The system consists of two connected workflows:

1. **AI Intelligence Collector** — reviews information generated across departmental meetings and identifies recurring themes, blockers, operational issues and areas where AI or automation may be useful.
2. **AI Weekly Curated Publisher** — converts the collected intelligence into a structured weekly output, including relevant observations and potential tools or approaches worth exploring.

The objective was not simply to distribute AI news.

The system was designed to connect AI adoption to real operational problems being discussed inside the business.

---

## Business Problem

AI tools change quickly, but simply sharing lists of new tools does not necessarily improve a business.

A more useful question is:

> What problems are teams actually experiencing, and where could AI or automation make a meaningful difference?

Departmental meetings already contain useful operating information such as:

- recurring blockers;
- administrative bottlenecks;
- repeated manual tasks;
- communication problems;
- information-flow issues;
- process inefficiencies;
- emerging priorities.

The challenge is that this information is distributed across different conversations and can be difficult to review systematically.

The system was developed to turn those recurring operational signals into structured intelligence.

---

## System Architecture

```text
Departmental Meetings
        ↓
Operational Information
        ↓
AI Intelligence Collector
        ↓
Identify Themes
        ↓
Blockers / Repeated Work /
Process Issues / Opportunities
        ↓
Collected Intelligence
        ↓
AI Weekly Curated Publisher
        ↓
Prioritise & Structure Insights
        ↓
Relevant AI / Automation Opportunities
        ↓
Weekly Intelligence Output
```

---

## Two-Workflow Design

### 1. AI Intelligence Collector

The Collector focuses on gathering and interpreting information from recurring organisational activity.

Its role is to identify useful signals from the week's operational discussions.

Examples can include:

```text
Repeated blocker
        ↓
Operational problem

Manual repetitive activity
        ↓
Automation opportunity

Information-access problem
        ↓
Potential knowledge / AI opportunity

Repeated reporting requirement
        ↓
Potential workflow improvement
```

The Collector therefore acts as the information-gathering layer of the system.

---

### 2. AI Weekly Curated Publisher

The Publisher works with the intelligence produced by the collection process.

Its purpose is to turn that information into a more useful weekly output rather than simply presenting raw meeting information.

The workflow helps organise the intelligence into areas such as:

- important recurring operational themes;
- blockers worth investigating;
- processes that may benefit from automation;
- potential AI use cases;
- relevant tools or approaches worth exploring.

The Publisher therefore acts as the interpretation and communication layer.

---

## Why the Two Workflows Are Separate

Separating collection from publishing creates a clearer architecture.

```text
COLLECT
   ↓
Gather and interpret information

STORE / PREPARE
   ↓
Maintain useful intelligence

PUBLISH
   ↓
Select, structure and communicate
```

This is more flexible than attempting to retrieve, analyse and publish everything through one large workflow.

For example, the collection process can run independently from the weekly publication process.

The same collected intelligence could also potentially support other outputs later.

---

## Inputs, Processing and Outputs

### Inputs

The system uses information generated through recurring organisational meetings and departmental operating discussions.

The public portfolio will not publish the original internal meeting information.

### Processing

At a high level, the system:

1. gathers relevant information from organisational meetings;
2. identifies operational themes and recurring problems;
3. looks for repeated manual work and process friction;
4. identifies areas where AI or automation may be relevant;
5. consolidates the resulting intelligence;
6. prepares a curated weekly view;
7. surfaces useful observations and relevant AI opportunities.

### Outputs

The primary output is a structured weekly intelligence update designed to connect emerging AI capabilities with actual operational needs.

---

## What This Project Demonstrates

### Problem-First AI Adoption

Starting with operational problems rather than beginning with an AI tool and searching for somewhere to use it.

### Organisational Intelligence

Using information generated through normal operating activity to identify themes and opportunities across the business.

### Multi-Stage Automation

Separating information collection from later analysis and publishing.

### LLM-Assisted Analysis

Using language models to help interpret unstructured organisational information.

### Continuous Improvement

Looking for recurring friction, blockers and repetitive work that may justify process redesign or automation.

### Management Information

Turning distributed operational information into a more structured view for review and decision-making.

### AI Opportunity Identification

Connecting business problems with possible AI or automation interventions rather than recommending technology in isolation.

---

## Problem-First AI Framework

An important principle behind this project was:

```text
Business Problem
      ↓
Understand Process
      ↓
Identify Friction
      ↓
Determine Whether Automation Helps
      ↓
Select Appropriate Technology
```

rather than:

```text
New AI Tool
      ↓
Search for Something to Automate
```

This reduces the risk of adopting technology simply because it is new.

The objective is operational improvement, not AI adoption for its own sake.

---

## Operational Relevance

The architecture could be applied to many organisations where recurring meetings contain valuable information that is difficult to consolidate.

For example:

```text
Meetings
   ↓
Issues + Actions + Blockers
   ↓
Pattern Detection
   ↓
Cross-Department Themes
   ↓
Improvement Opportunities
   ↓
Management Intelligence
```

Potential applications include:

- operational excellence;
- continuous improvement;
- digital transformation;
- AI adoption governance;
- management reporting;
- process improvement;
- knowledge management;
- recurring blocker analysis;
- automation opportunity discovery.

---

## Human Review and Decision-Making

The system is designed to support human judgement rather than automatically decide which technologies a business should adopt.

The workflow can help surface patterns and opportunities.

Management still needs to determine:

- whether the problem is important;
- whether automation is appropriate;
- whether the proposed approach is secure;
- whether the benefit justifies the effort;
- who should own implementation;
- whether human oversight is required.

The intended relationship is:

```text
Automation
    ↓
Collect + organise + surface patterns
    ↓
Human Review
    ↓
Prioritise + validate + decide
```

---

## Confidentiality and Public Evidence

This project was implemented in a real workplace environment.

The public repository will therefore not contain:

- original internal meeting transcripts;
- employee information;
- customer information;
- confidential company metrics;
- internal management reports;
- private Teams or SharePoint content;
- credentials;
- API keys or tokens;
- private workflow execution data.

Portfolio documentation will focus on the architecture, process logic and transferable concepts.

Where sample information is needed, recreated or anonymised examples will be used.

---

## Development Status

The workplace implementation included separate workflows for:

- organisational AI intelligence collection;
- weekly curated AI intelligence publishing.

Further portfolio documentation may include:

- a recreated architecture diagram;
- sanitised screenshots of the Collector workflow;
- sanitised screenshots of the Publisher workflow;
- representative example input;
- recreated weekly intelligence output;
- explanation of how information moves between the two workflows;
- processing and filtering logic;
- lessons learned.

---

## Portfolio Evidence

This project will progressively document:

```text
AI Intelligence Collector
        +
AI Weekly Curated Publisher
        ↓
Operational AI Intelligence System
```

The objective is to demonstrate both the technical workflow and the operating principle behind it:

> **Start with real business problems, use organisational information to identify recurring friction, and then evaluate where AI or automation can create practical value.**

---

## Key Learning

The most important lesson from this project is that an effective organisational AI strategy should not begin with technology.

It should begin with the work.

The reusable pattern is:

> **What is happening in the organisation → what problems keep appearing → which processes create friction → which problems are worth solving → where can automation or AI genuinely help → what should people review and act on?**

AI becomes a tool within operational improvement rather than the objective itself.

---

[← Back to Automation Portfolio](../../README.md)

[Professional Portfolio](https://vicakoyo.github.io/)
