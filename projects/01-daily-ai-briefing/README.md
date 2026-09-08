# Daily AI Briefing

**Platform:** n8n  
**Status:** Working project / continuing development  
**Project Type:** Workflow Automation • AI-Assisted Information Processing • Operational Reporting

---

## Overview

Daily AI Briefing is an n8n workflow designed to reduce the repetitive work involved in monitoring developments across AI tools and platforms.

The workflow collects information from selected web and RSS sources, processes and filters the incoming content, aggregates relevant items, uses an LLM to produce a concise briefing, and delivers the resulting summary through Telegram.

The project is part of my ongoing development in workflow automation, APIs, structured data and AI-enabled operational processes.

---

## Business Problem

Keeping up with developments across AI platforms and tools can require repeatedly checking multiple information sources, identifying relevant updates and manually summarising them.

The underlying operational problem is broader than AI news:

> How can repetitive information gathering be converted into a structured workflow that produces a useful output for human review?

The Daily AI Briefing explores one practical solution.

---

## Workflow

```text
Scheduled Trigger
       ↓
RSS / Web Sources
       ↓
Content Retrieval
       ↓
Filtering & Processing
       ↓
Aggregation
       ↓
LLM Summarisation
       ↓
Telegram Briefing
```

The workflow separates information collection, processing and delivery into individual stages rather than treating the task as one large AI prompt.

---

## How It Works

### 1. Scheduled Trigger

The workflow starts automatically according to a defined schedule.

This removes the need to manually initiate the information-gathering process.

### 2. Information Collection

Selected RSS feeds and web sources provide the incoming information.

The workflow retrieves content from these sources for further processing.

### 3. Content Processing

Incoming items are separated and processed so that individual pieces of information can be evaluated.

Filtering helps reduce irrelevant material before later stages of the workflow.

### 4. Aggregation

Relevant information is brought together into a structured collection before being passed to the language model.

This creates a more controlled input for summarisation.

### 5. AI-Assisted Summarisation

An OpenAI language model is used to transform the processed information into a shorter briefing.

The LLM is one component within the workflow rather than the entire workflow.

### 6. Delivery

The resulting briefing is delivered through Telegram, creating a simple interface for receiving the output.

---

## Workflow Components

The project has involved working with n8n components including:

- Schedule Trigger
- HTTP requests
- RSS/XML data
- XML processing
- Split operations
- Filters
- Edit/Set operations
- HTML extraction
- Code nodes
- Merge operations
- Aggregation
- Basic LLM Chain
- OpenAI Chat Model
- Telegram

---

## Inputs, Processing and Outputs

### Inputs

Information retrieved from selected RSS feeds and web sources.

### Processing

The workflow:

1. retrieves source content;
2. converts incoming information into processable items;
3. filters and cleans relevant content;
4. combines selected information;
5. passes structured content to an LLM;
6. generates a concise briefing.

### Output

A human-readable AI-assisted briefing delivered through Telegram.

---

## What This Project Demonstrates

This project provides practical exposure to several transferable automation concepts:

**Workflow decomposition**  
Breaking a business process into smaller stages with defined responsibilities.

**Triggers**  
Using an event or schedule to initiate a workflow automatically.

**Data transformation**  
Changing information from one structure into another so that downstream steps can use it.

**Filtering**  
Applying rules to decide which information should continue through a workflow.

**Aggregation**  
Combining multiple pieces of information into a structured input.

**API-based services**  
Connecting different applications so that information can move between systems.

**LLM integration**  
Using a language model for a specific processing task inside a wider workflow.

**Automated delivery**  
Sending the final output to the channel where it will be consumed.

---

## Operational Relevance

Although this project uses AI-industry information as its subject, the underlying workflow pattern can be applied to other operational problems.

For example:

```text
Multiple Information Sources
          ↓
Retrieve Data
          ↓
Apply Rules
          ↓
Consolidate
          ↓
Analyse / Summarise
          ↓
Deliver to Decision Maker
```

Similar patterns could support:

- operational KPI summaries;
- supplier or logistics updates;
- customer issue monitoring;
- management reporting;
- exception reporting;
- daily operational briefings;
- recurring administrative processes.

The transferable capability is therefore not simply generating an AI-news summary. It is understanding how information can move through a structured automated process.

---

## Current Capability Level

This is a practical development project rather than evidence of advanced software engineering capability.

I can work with the workflow structure and understand the purpose of its major components, while continuing to develop deeper independent capability in:

- n8n;
- JSON;
- HTTP and REST APIs;
- webhooks;
- authentication and OAuth;
- Git/GitHub;
- basic Python;
- AI tool orchestration.

The objective is progressive independence: understanding not only how to make a workflow operate, but why each component is required and how the same concepts transfer to other business problems.

---

## Development Status

The core workflow has been built and tested as a working project.

Further development may include:

- improved source management;
- stronger filtering and relevance rules;
- better error handling;
- structured logging;
- duplicate-content handling;
- improved prompt and output consistency;
- workflow documentation;
- additional testing and monitoring.

---

## Next Portfolio Evidence

This project folder will progressively include supporting evidence such as:

- workflow screenshots;
- workflow export files where appropriate;
- example outputs;
- architecture documentation;
- implementation notes;
- lessons learned.

Sensitive credentials, API keys, tokens and private configuration will not be published.

---

## Key Learning

The most important lesson from this project is that useful automation is not simply about connecting applications.

A reliable workflow requires understanding:

**what triggers the process → what data enters → how the data is transformed → what decisions are applied → what output is required → where that output should go.**

That process thinking is directly transferable to operational automation beyond n8n.

---

[← Back to Automation Portfolio](../../README.md)

[Professional Portfolio](https://vicakoyo.github.io/)
