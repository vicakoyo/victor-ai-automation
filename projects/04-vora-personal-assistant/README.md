# VORA Personal Operations Assistant

**Platform:** n8n • WhatsApp • Anthropic • Groq • Structured Data Tools • Tavily  
**Status:** Working personal project / continuing development  
**Project Type:** AI Agent • Workflow Automation • Persistent Context • Conversational Interface

---

## Overview

VORA is a personal operations assistant designed to combine conversational AI with structured information, workflow automation and persistent context.

The assistant uses WhatsApp as the user interface and n8n as the orchestration layer.

Incoming messages can be processed as either text or audio. Audio messages follow a transcription path before reaching the AI Agent, while text messages can move directly into the agent-processing stage.

The AI Agent can then use conversational memory, retrieve structured information through connected tools, perform selected updates and return the resulting response through WhatsApp.

The project explores how an AI assistant can move beyond isolated question-and-answer interactions and operate as part of a more structured personal information system.

---

## Problem

General-purpose conversational AI is useful for individual questions, but important information can become fragmented across separate conversations, notes, tasks and applications.

A useful personal assistant may need to understand information such as:

- current goals;
- existing commitments;
- relevant people context;
- previous check-ins;
- persistent personal context;
- updates that should be remembered;
- current external information.

The underlying problem is:

> How can a conversational AI interface retrieve and use structured information while keeping memory, tools, updates and message handling under explicit workflow control?

VORA is an ongoing attempt to solve that problem.

---

## High-Level Architecture

```text
WhatsApp Message
       ↓
Initial Filter
       ↓
Message Type Check
       ↓
 ┌───────────────┐
 │ Audio Message?│
 └───────┬───────┘
      Yes│                 No
         ↓                  │
Download Media             │
         ↓                  │
Fetch Audio Bytes          │
         ↓                  │
Groq Transcription         │
         ↓                  │
Format Transcript          │
         └──────────┬───────┘
                    ↓
                 AI Agent
                    ↓
       ┌────────────┼─────────────┐
       ↓            ↓             ↓
   AI Model      Memory      Structured Tools
                                  ↓
                         Context / Goals /
                         People / Check-ins /
                         Commitments / Updates
                                  ↓
                         Optional Web Search
                                  ↓
                              AI Response
                                  ↓
                           WhatsApp Message
```

---

## Workflow Implementation

The screenshot below shows the current n8n implementation of VORA.

![VORA n8n workflow](workflow-overview.png)

The workflow combines message handling, conditional routing, audio transcription, AI-agent orchestration, conversational memory, structured data tools, external information retrieval and WhatsApp delivery.

Rather than placing all functionality inside one large prompt, the system separates different responsibilities into distinct workflow components.

---

## How It Works

### 1. WhatsApp Trigger

WhatsApp provides the primary conversational interface.

An incoming WhatsApp message triggers the n8n workflow and makes the message available for further processing.

This separates the user interface from the underlying automation architecture.

```text
User
  ↓
WhatsApp
  ↓
n8n
```

The same underlying assistant architecture could later use another interface without necessarily changing the complete reasoning or data layer.

---

### 2. Initial Filtering

After the trigger, the workflow applies an initial filter.

This provides an early control point before messages move deeper into the workflow.

Filtering is useful because external messaging systems can generate different kinds of events, and not every incoming event necessarily needs the same processing path.

---

### 3. Message-Type Decision

The workflow checks whether the incoming message is an audio message.

This introduces conditional processing.

```text
Incoming Message
       ↓
Is it audio?
     /      \
   Yes       No
    ↓         ↓
Audio Path   Continue
```

Different input types therefore receive different preprocessing while ultimately feeding into the same assistant.

---

## Audio Processing Path

### 4. Download Media

If the incoming WhatsApp message contains audio, the workflow first retrieves the associated media.

The message event itself does not necessarily contain the complete audio content required for transcription.

The workflow therefore needs to retrieve that media before further processing.

---

### 5. Fetch Audio Bytes

The audio content is then fetched in a form that can be passed to the transcription service.

This demonstrates an important API and automation concept:

> A file reference and the actual file data are not always the same thing.

The workflow may first receive information identifying the media and then perform a separate request to obtain the underlying audio data.

---

### 6. Groq Transcription

The retrieved audio is passed to a transcription service through Groq.

The purpose of this stage is to convert spoken input into text.

```text
Voice Message
      ↓
Audio Data
      ↓
Speech-to-Text
      ↓
Transcript
```

Once the message exists as text, it can enter the same reasoning process as a typed WhatsApp message.

---

### 7. Transcript Formatting

A formatting step prepares the transcription for the AI Agent.

This gives the next stage a cleaner and more predictable representation of the user's message.

It also illustrates why data preparation matters in automation:

```text
Raw Service Output
        ↓
Transform / Format
        ↓
Clean Input
        ↓
Next System
```

---

## AI Agent Layer

### 8. AI Agent

Both conversational input paths ultimately feed into the AI Agent.

The agent acts as the central decision and orchestration layer.

Instead of only generating text, the agent can determine when relevant connected tools should be used to retrieve additional information.

Conceptually:

```text
User Question
      ↓
AI Agent
      ↓
What information is needed?
      ↓
Use appropriate tool
      ↓
Receive tool result
      ↓
Generate response
```

This is different from a simple chatbot that only receives a prompt and immediately produces an answer.

---

### 9. Anthropic Chat Model

The AI Agent is connected to an Anthropic chat model.

The model provides the language-understanding and response-generation capability used by the agent.

The model and the agent are related but different components.

```text
AI Agent
   ↓
Decides how the task should be handled

Language Model
   ↓
Provides language reasoning / generation
```

The agent architecture allows the model to operate alongside memory and tools rather than acting in isolation.

---

## Memory and Persistent Context

### 10. Conversational Memory

VORA includes a memory component connected to the AI Agent.

This supports conversational continuity within the assistant interaction.

For example, a user might say:

```text
Message 1:
"I'm planning to complete that application tonight."

Message 2:
"What did I say I would do?"
```

Conversation memory can help preserve the immediate context between those messages.

---

### 11. Structured Persistent Context

VORA also uses structured information outside the conversational memory layer.

This is an important distinction.

```text
Conversational Memory
        ↓
Recent conversation continuity

Structured Context
        ↓
Information stored deliberately in defined records
```

Structured context can be retrieved through tools when the assistant needs it.

Current information areas include:

- personal/context facts;
- active goals;
- people context;
- daily check-ins;
- commitments;
- proposed context updates.

This makes the information more deliberate and structured than simply relying on a long conversation history.

---

## Agent Tools

The current VORA architecture connects the AI Agent to several specialised tools.

These tools allow the assistant to retrieve or act on particular categories of information.

The tool layer currently supports functions related to:

```text
Context
Goals
People
Daily Check-ins
Commitments
Context Updates
Check-in History
External Search
```

The important concept is that the AI Agent does not need every piece of information to be permanently placed inside its prompt.

Instead:

```text
Question arrives
      ↓
Agent identifies information required
      ↓
Agent selects tool
      ↓
Tool retrieves relevant information
      ↓
Agent uses result
      ↓
Response generated
```

This helps separate reasoning from data retrieval.

---

## Read Operations and Write Operations

VORA contains tools that serve different purposes.

Some tools primarily **read information**.

For example:

```text
Get active goals
Get people context
Get active commitments
Get previous check-ins
```

Other tools can support **changing or recording information**.

For example:

```text
Log a daily check-in
Update a commitment
Propose a context update
```

This distinction matters because reading information and changing information carry different risks.

```text
READ
↓
Retrieve existing information

WRITE
↓
Create or change stored information
```

Write operations should therefore be more controlled than simple retrieval.

---

## Controlled Context Updates

One of VORA's design ideas is that important context changes should not simply be written into persistent information without control.

A proposed update can be separated from the final stored information so that the system can maintain clearer boundaries around what becomes persistent context.

Conceptually:

```text
Conversation
      ↓
Potential New Fact
      ↓
Proposed Context Update
      ↓
Control / Confirmation
      ↓
Persistent Context
```

This is particularly useful in systems where conversational statements should not automatically become permanent records.

---

## Commitments

Commitments are maintained as a structured information category rather than being left only inside conversation history.

This allows the assistant to retrieve active commitments when relevant and support updates as circumstances change.

The broader pattern is:

```text
Commitment Created
       ↓
Stored Record
       ↓
Retrieved Later
       ↓
Reviewed / Updated
```

This demonstrates how an AI assistant can interact with operational records rather than functioning only as a text generator.

---

## Daily Check-ins

VORA can also work with structured daily check-in information.

This provides a way to record recurring information that may later be retrieved or reviewed.

The concept is similar to an operational log:

```text
Date
 ↓
Check-in
 ↓
Structured Record
 ↓
Future Retrieval / Review
```

The same concept appears in business systems through shift logs, incident records, quality records and operational journals.

---

## External Search

The current AI Agent also includes access to Tavily search.

This allows the assistant to retrieve current external information when the question requires information beyond stored personal context.

This creates another clear separation:

```text
Personal information needed
        ↓
Use structured context tools

Current external information needed
        ↓
Use search tool
```

The agent can therefore choose an information source according to the task.

---

## Response Delivery

After the AI Agent completes the processing, the final response is returned through WhatsApp.

The complete interaction loop becomes:

```text
WhatsApp Input
      ↓
Message Processing
      ↓
Context / Tools / Search
      ↓
AI Agent
      ↓
Response
      ↓
WhatsApp Output
```

This makes WhatsApp the interaction layer while n8n handles the underlying orchestration.

---

## Inputs, Processing and Outputs

### Inputs

Current supported input patterns include:

- WhatsApp text messages;
- WhatsApp audio messages.

The AI Agent may also retrieve information through connected tools during processing.

---

### Processing

At a high level, VORA:

1. receives an incoming WhatsApp message;
2. applies initial workflow filtering;
3. identifies whether the input is text or audio;
4. retrieves and transcribes audio where necessary;
5. formats the resulting text;
6. passes the user message into the AI Agent;
7. provides access to a language model and conversational memory;
8. allows the agent to call relevant structured-data tools;
9. allows external search when appropriate;
10. generates the final response;
11. sends the response back through WhatsApp.

---

### Outputs

The primary output is a conversational WhatsApp response informed by the information available to the agent.

Depending on the interaction, the workflow may also create or update structured records through controlled tools.

---

## What This Project Demonstrates

### Conversational Workflow Interfaces

Using a messaging application as the front end for a larger automated system.

### Conditional Routing

Processing different message types through different paths.

### Media Handling

Retrieving media associated with messaging-platform events.

### Speech-to-Text

Converting audio input into text so that it can enter the same downstream reasoning process.

### API-Based Processing

Moving data between external applications and services through automated requests.

### AI Agents

Connecting a language model to memory and tools so that the system can retrieve additional information before producing a response.

### Tool Use

Giving the AI Agent access to narrowly defined capabilities rather than placing every function inside the prompt.

### Persistent Context

Maintaining structured information separately from immediate conversation history.

### Read / Write Separation

Distinguishing information retrieval from operations that change stored data.

### External Information Retrieval

Using search when a task depends on information outside the assistant's stored context.

### Workflow Orchestration

Coordinating several distinct systems inside one end-to-end process.

---

## Memory Is Not One Thing

An important concept demonstrated by this project is that "memory" can refer to different mechanisms.

In VORA, it is useful to distinguish:

```text
Conversation Memory
        ↓
Helps maintain continuity during interaction

Structured Persistent Data
        ↓
Stores defined information such as goals or commitments

External Search
        ↓
Retrieves information that is neither conversational memory nor stored personal context
```

These components solve different problems.

Treating all three as simply "AI memory" would hide important architectural differences.

---

## Operational Relevance

Although VORA is a personal assistant, the architecture contains patterns that transfer directly to business automation.

For example:

```text
User / Employee Request
          ↓
Messaging Interface
          ↓
Classify Request
          ↓
Retrieve Required Records
          ↓
Apply Tools / Rules
          ↓
Generate Response
          ↓
Record Necessary Update
```

Similar patterns could support:

- employee support assistants;
- internal operations assistants;
- customer-service triage;
- knowledge retrieval;
- HR service workflows;
- management information assistants;
- supplier-support workflows;
- quality-information retrieval;
- incident reporting;
- structured operational check-ins.

The value of the architecture is therefore broader than the personal use case.

---

## Why This Project Is Different From a Basic Chatbot

A basic chatbot can often be represented as:

```text
Message
   ↓
LLM
   ↓
Response
```

VORA has additional system layers:

```text
Message
   ↓
Input Handling
   ↓
Message-Type Logic
   ↓
Optional Transcription
   ↓
AI Agent
   ↓
Memory + Structured Tools + Search
   ↓
Controlled Data Operations
   ↓
Response
```

The difference is not simply that one chatbot has a longer prompt.

The system has explicit components responsible for input handling, information retrieval, persistent records and external actions.

---

## Privacy and Public Evidence

VORA processes personal context and therefore requires stronger privacy controls than the other portfolio projects.

The public repository will not contain:

- private WhatsApp messages;
- phone numbers;
- personal relationship information;
- private goals or commitments;
- personal check-in records;
- authentication credentials;
- API keys or tokens;
- webhook URLs;
- server credentials;
- database contents;
- private workflow execution payloads.

Screenshots used publicly will show architecture rather than private data.

Any future sample interactions will use recreated information.

---

## Infrastructure and Portability

The current workflow is hosted through a self-hosted n8n environment.

Because personal systems should not depend indefinitely on infrastructure that may become unavailable, portability and backup remain important development areas.

Useful future documentation will include:

```text
Workflow Definition
Persistent Data
Credentials / Secrets
Environment Configuration
External Service Connections
Backup
Restore
Migration
```

The objective is not merely to have the current workflow running.

A mature personal automation system should also be recoverable and understandable enough to move to another environment when required.

---

## Development Focus

VORA is being used to deepen practical understanding of:

- n8n;
- WhatsApp workflow integration;
- conditional routing;
- media handling;
- HTTP requests;
- speech-to-text processing;
- AI Agents;
- Anthropic model integration;
- memory;
- structured persistent data;
- agent tools;
- read and write operations;
- web search;
- JSON and data mapping;
- APIs;
- webhooks;
- authentication;
- workflow error handling.

The objective is to progressively understand and control more of the architecture independently rather than treating a working AI-assisted build as proof of complete technical mastery.

---

## Development Status

VORA is a working personal project under continuing development.

The current documented architecture includes:

- WhatsApp-triggered input;
- initial workflow filtering;
- text/audio message handling;
- audio media retrieval;
- audio-byte retrieval;
- Groq-based transcription;
- transcript formatting;
- an AI Agent;
- Anthropic chat-model integration;
- conversational memory;
- structured context tools;
- goal retrieval;
- people-context retrieval;
- daily check-in functionality;
- commitment functionality;
- controlled context-update functionality;
- check-in retrieval;
- Tavily web search;
- WhatsApp response delivery.

Further development may include:

- stronger error handling;
- retry behaviour;
- clearer tool permissions;
- more explicit write confirmation;
- improved logging;
- structured testing;
- backup and migration documentation;
- sanitised workflow export;
- representative public sample interactions;
- deeper authentication and API documentation.

---

## Portfolio Evidence

This project currently includes:

- project documentation;
- real n8n workflow architecture;
- WhatsApp message handling;
- audio-processing architecture;
- agent-tool architecture;
- structured-data design;
- persistence concepts;
- privacy controls.

Additional evidence may be added progressively without publishing private personal information.

---

## Key Learning

The most important lesson from VORA is that a useful AI assistant is not simply a language model connected to a messaging application.

The complete system requires understanding:

> **How the message arrives → what type of input it is → what preprocessing is required → what information the agent needs → which tool should retrieve it → whether the operation reads or changes data → how external information is obtained → how the response is returned → what information should persist.**

The language model is one component.

The wider capability is designing and controlling the system around it.

---

[← Back to Automation Portfolio](../../README.md)

[Professional Portfolio](https://vicakoyo.github.io/)
