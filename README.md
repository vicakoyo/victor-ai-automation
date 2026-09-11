# Victor Akoyo — Operations Automation Portfolio

Practical automation, AI and business-systems projects focused on improving operational reporting, information flow, decision support and repetitive business processes.

**Victor Akoyo**  
Operations | Supply Chain | Quality | Process Improvement  
Nairobi, Kenya

[Professional Portfolio](https://vicakoyo.github.io/) | [LinkedIn](https://www.linkedin.com/in/victorakoyo/) | [Email](mailto:vicakoyo2@gmail.com)

---

## About This Repository

My professional background is primarily in Operations, Supply Chain, Quality Management and Process Improvement.

Across those roles, I have worked with operational data, ERP and business systems, KPI reporting, SOPs, cross-functional workflows and recurring administrative processes.

I am developing automation and AI capability to extend that operational experience.

This repository documents practical projects where I have explored how workflow automation, APIs, AI and structured data can be applied to real operational problems.

The objective is not automation for its own sake.

The objective is to build systems that can improve:

- information flow;
- management visibility;
- reporting;
- repetitive process execution;
- accountability;
- operational decision-making;
- continuous improvement.

Some projects are personal builds and others are documented versions of real workplace implementations.

Where workplace projects involved confidential information, the public portfolio uses architecture-level evidence, anonymised descriptions and recreated examples rather than publishing private business data.

---

# Projects

## [01 — Daily AI Briefing](projects/01-daily-ai-briefing/)

**Platform:** n8n • OpenAI • Telegram  
**Status:** Working project / continuing development

A scheduled information-processing workflow that gathers selected AI-industry information from web and RSS sources, filters and transforms the incoming content, aggregates relevant items, uses an LLM to prepare a concise briefing and delivers the result automatically through Telegram.

### Demonstrates

- scheduled workflow execution;
- web and RSS information retrieval;
- filtering and data transformation;
- aggregation;
- LLM integration;
- Telegram delivery;
- structured information flow.

[View project →](projects/01-daily-ai-briefing/)

---

## [02 — Executive Meeting Intelligence](projects/02-executive-meeting-intelligence/)

**Platform:** Make.com • Microsoft SharePoint • Microsoft Graph • OpenAI • Microsoft Teams • Data Store  
**Status:** Workplace implementation / portfolio documentation in progress

A workplace automation used to turn senior-leadership meeting information into structured management reporting.

The workflow combines SharePoint monitoring, Microsoft Graph and HTTP requests, record iteration, meeting-information retrieval, AI-assisted analysis, output formatting, persistent workflow state and Microsoft Teams delivery.

### Demonstrates

- Microsoft 365 integration;
- API-based information retrieval;
- record iteration;
- LLM-assisted management reporting;
- persistent workflow state;
- conditional delivery;
- automated Teams reporting.

[View project →](projects/02-executive-meeting-intelligence/)

---

## [03 — CRM Campaign Routing Automation](projects/03-crm-campaign-routing/)

**Platform:** Make.com • Pipedrive • Lemlist  
**Status:** Workplace implementation / portfolio documentation in progress

A CRM-to-outreach workflow that monitors Pipedrive activity, retrieves the associated person record and applies conditional routing logic across multiple branches before placing eligible contacts into the appropriate Lemlist campaign.

The project demonstrates that effective automation does not always require AI. Where clear business rules exist, deterministic routing can often provide the simpler and more predictable solution.

### Demonstrates

- CRM triggers;
- related-record retrieval;
- field mapping;
- routers and filters;
- conditional logic;
- multi-path workflows;
- cross-platform integration;
- rule-based automation.

[View project →](projects/03-crm-campaign-routing/)

---

## [04 — VORA Personal Operations Assistant](projects/04-vora-personal-assistant/)

**Platform:** n8n • WhatsApp • Anthropic • Groq • Structured Data Tools • Tavily  
**Status:** Working personal project / continuing development

VORA is a personal operations assistant that combines conversational AI with structured persistent information and workflow-controlled tools.

The workflow accepts both text and audio messages through WhatsApp. Audio messages are retrieved and transcribed before being passed to an AI Agent.

The agent can then use conversational memory, retrieve structured information about goals, commitments, people and check-ins, perform controlled data operations, use external search when needed and return the response through WhatsApp.

### Demonstrates

- WhatsApp-triggered workflows;
- text and audio routing;
- media retrieval;
- speech-to-text processing;
- AI Agents;
- tool use;
- structured persistent context;
- conversational memory;
- read/write operations;
- external search;
- workflow orchestration.

[View project →](projects/04-vora-personal-assistant/)

---

## [05 — IT Support Triage Workflow](projects/05-it-support-triage/)

**Platform:** Microsoft Forms • Power Automate • Microsoft Teams  
**Status:** Workplace implementation / portfolio documentation in progress

A structured internal service workflow created to give employees a consistent route for reporting technology issues.

Microsoft Forms captured the request, Power Automate processed the submission and Microsoft Teams provided notification and visibility for triage, ownership and escalation.

### Demonstrates

- structured data capture;
- trigger-based automation;
- automated notifications;
- service-request triage;
- workflow ownership;
- process standardisation;
- Microsoft 365 integration.

[View project →](projects/05-it-support-triage/)

---

## [06 — Operational AI Intelligence System](projects/06-operational-ai-intelligence/)

**Platform:** Make.com • Make AI Web Search • Make AI Toolkit • Data Store • Microsoft Teams  
**Status:** Workplace implementation / portfolio documentation in progress

A two-workflow system designed to connect AI discovery with real operational problems emerging across an organisation.

The wider process used themes from recurring departmental activity — including blockers, repetitive work and process friction — to identify areas where AI or automation could potentially add value.

The technical implementation separates the process into:

**AI Intelligence Collector**

```text
Make AI Web Search
        ↓
Iterator
        ↓
Data Store
```

and:

**AI Weekly Curated Publisher**

```text
Data Store
        ↓
Text Aggregator
        ↓
Make AI Toolkit
        ↓
Publishing Control
        ↓
Microsoft Teams
```

The Collector builds a persistent pool of relevant intelligence. The Publisher retrieves that information, consolidates it, uses AI to curate the most useful material and delivers a weekly update through Microsoft Teams.

### Demonstrates

- problem-first AI adoption;
- scheduled intelligence gathering;
- AI-assisted web research;
- iteration;
- persistent data storage;
- multi-workflow architecture;
- aggregation;
- AI-assisted curation;
- controlled publishing;
- Microsoft Teams delivery.

[View project →](projects/06-operational-ai-intelligence/)

---

# Portfolio Map

| Project | Primary Problem | Main Concepts |
|---|---|---|
| **Daily AI Briefing** | Repetitive information monitoring | Retrieval, filtering, aggregation, LLMs, delivery |
| **Executive Meeting Intelligence** | Manual meeting reporting | APIs, iteration, AI analysis, persistence, Teams |
| **CRM Campaign Routing** | Manual lead routing | CRM data, filters, routers, deterministic logic |
| **VORA** | Fragmented personal context | Agents, tools, memory, structured data, audio, search |
| **IT Support Triage** | Unstructured technology requests | Forms, workflow routing, ownership, notifications |
| **Operational AI Intelligence** | Connecting business problems with relevant AI opportunities | Research, persistence, aggregation, curation, publishing |

---

# Automation Concepts Across the Portfolio

Although the projects use different platforms, many of the underlying concepts are transferable.

## Triggers

A trigger determines when a workflow starts.

Examples in this portfolio include:

- schedules;
- CRM activity;
- WhatsApp messages;
- SharePoint activity;
- form submissions.

---

## Data Retrieval

Automations often need to obtain information from another application before they can act.

Examples include:

- RSS and web content;
- CRM records;
- related CRM contacts;
- Microsoft Graph information;
- meeting information;
- WhatsApp media;
- persistent Data Store records;
- external search results.

---

## Transformation

Information frequently needs to be cleaned, separated, reformatted or combined before another system can use it.

Examples include:

- iterators;
- filters;
- formatting;
- aggregation;
- transcript preparation;
- field mapping.

---

## Conditional Logic

Not every input should receive the same action.

Conditional logic allows workflows to make repeatable decisions.

The same concept appears as:

```text
Make.com Router / Filter
n8n IF or Switch logic
Power Automate Condition
if statements in code
business rules in operational systems
```

---

## Persistence

Some workflows need information from previous executions.

Examples in this portfolio include Make Data Stores and structured data used by VORA.

Persistence allows a workflow to remember information such as:

```text
Has this item already been processed?

What commitments currently exist?

What intelligence has already been collected?

What context should be retrieved later?
```

---

## AI as a Workflow Component

Several projects use language models, but AI is not treated as the complete workflow.

The wider architecture typically looks more like:

```text
Trigger
   ↓
Retrieve Information
   ↓
Prepare Data
   ↓
Apply Rules
   ↓
AI Processing where useful
   ↓
Validate / Control
   ↓
Deliver Result
```

Some problems, such as CRM campaign routing, are better handled through deterministic rules without an LLM.

The technology choice should follow the problem.

---

# Operational Approach to Automation

My approach is increasingly centred on a simple principle:

> **Start with the process and the problem, then determine whether automation or AI can improve it.**

A useful automation should answer questions such as:

```text
What triggers the process?
        ↓
What information is required?
        ↓
Where does that information come from?
        ↓
How should it be transformed?
        ↓
What decisions or rules apply?
        ↓
Where can AI add useful capability?
        ↓
What output is required?
        ↓
Who or what receives the output?
        ↓
What happens when something fails?
```

This process-oriented approach connects automation development with my wider background in Operations, Supply Chain, Quality and Process Improvement.

---

# Current Development Areas

I am progressively developing deeper capability in:

- n8n;
- Make.com;
- workflow architecture;
- JSON and structured data;
- HTTP and REST APIs;
- webhooks;
- authentication and OAuth;
- AI Agents and tool use;
- workflow state and persistence;
- error handling;
- Git and GitHub;
- basic Python;
- automation testing and documentation.

The objective is not simply to produce increasingly sophisticated AI-assisted outputs.

The objective is to understand the architecture well enough to design, adapt, troubleshoot and explain comparable systems with increasing independence.

---

# Evidence and Privacy

Public portfolio material is selected carefully.

This repository does **not** intentionally publish:

- API keys;
- passwords;
- access tokens;
- private webhook URLs;
- personal data;
- confidential workplace transcripts;
- customer or employee records;
- private management reports;
- internal financial information;
- sensitive operational information.

Workplace projects are documented through architecture, sanitised screenshots, anonymised descriptions and recreated examples where necessary.

---

# Portfolio Development

The repository will be expanded progressively through deeper evidence rather than simply increasing project count.

Planned additions may include:

- sanitised workflow exports;
- architecture diagrams;
- representative input/output examples;
- data-flow documentation;
- error-handling patterns;
- testing scenarios;
- troubleshooting notes;
- implementation lessons;
- backup and portability documentation.

The aim is for each project to become increasingly:

```text
Working
   ↓
Understood
   ↓
Reproducible
   ↓
Documented
   ↓
Portable
   ↓
Presentable
```

---

# Professional Background

My core professional experience is in:

- Operations and Business Operations;
- Supply Chain and Logistics;
- Quality Management;
- Process Improvement;
- Management Reporting;
- Business Systems;
- Cross-functional execution.

Automation and AI are being developed as complementary capabilities for improving those operating environments rather than as a separate software-engineering identity.

---

## Links

**Professional Portfolio:**  
https://vicakoyo.github.io/

**LinkedIn:**  
https://www.linkedin.com/in/victorakoyo/

**Email:**  
vicakoyo2@gmail.com

---

*This repository is an evolving portfolio of practical automation work, implementation evidence and technical learning.*
