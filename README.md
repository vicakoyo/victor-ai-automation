# Victor Akoyo — Operations Automation Portfolio

Practical automation, AI and business-systems projects focused on improving operational reporting, information flow and repetitive business processes.

**Victor Akoyo**  
Operations | Supply Chain | Quality | Process Improvement  
Nairobi, Kenya

[Professional Portfolio](https://vicakoyo.github.io/) | [LinkedIn](https://www.linkedin.com/in/victorakoyo/) | [Email](mailto:vicakoyo2@gmail.com)

---

## About This Repository

My professional background is primarily in **Operations, Supply Chain, Quality Management and Process Improvement**.

Across those roles, I have worked with operational data, ERP and business systems, KPI reporting, SOPs, cross-functional workflows and recurring administrative processes.

I am developing automation capability to extend that experience.

This repository documents practical projects where I explore how workflow automation, APIs and AI can be applied to real operational problems.

The objective is not automation for its own sake.

The objective is to build simpler systems that can improve:

- information flow;
- management visibility;
- reporting;
- repetitive process execution;
- accountability; and
- operational decision-making.

---

# Projects

## 01 — Daily AI Briefing

**Platform:** n8n  
**Status:** Working project / continuing development

A workflow designed to collect information from selected AI-industry sources, process the incoming content, generate a concise AI-assisted briefing and deliver the result through Telegram.

### Business Problem

Keeping up with developments across AI tools and platforms requires repeatedly checking multiple information sources.

The workflow explores how that repetitive information-gathering process can be automated while still producing a concise output suitable for human review.

### Workflow

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
