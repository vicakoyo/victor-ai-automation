# 04 — VORA Personal Operations Assistant

**Platform:** n8n, WhatsApp, structured data tables, AI  
**Status:** Working personal project / continuing development

## Overview

VORA is a personal operations assistant designed to combine conversational AI with structured, persistent information.

Rather than operating only as a stateless chatbot, the workflow can retrieve relevant information about goals, commitments, people, check-ins and other context from structured data sources.

## Problem

Important personal information can become fragmented across conversations, notes and applications.

VORA explores how workflow automation, structured data and AI can work together to create a more persistent personal operations system that can retrieve useful context when needed.

## High-Level Workflow

```text
WhatsApp Message
        ↓
Webhook
        ↓
n8n
        ↓
AI / Decision Layer
        ↓
Context & Data Tools
        ↓
Structured Data
        ↓
Response
