
# Aura Intelligence – Customer Support AI Agent

A Telegram-based **Customer Support AI Agent** built using **n8n**, **Google Gemini**, and **Google Docs** as a knowledge base.  
The agent answers company-related queries directly within Telegram by strictly referencing a predefined knowledge base and a carefully designed system prompt to prevent hallucinations.


## Project Overview

This project demonstrates how to build a **knowledge-grounded customer support AI agent** using low-code automation and large language models.

- Users interact with the agent via Telegram
- Queries are answered using a Google Doc–based knowledge base
- Responses are generated using Google Gemini
- Context is preserved using n8n Simple Memory
- A strict system prompt ensures accuracy and prevents hallucinated responses

The knowledge base represents a **dummy AI company (Aura Intelligence)** created specifically for this project using Gemini.


## Key Features

- Telegram-based real-time customer support interface
- Google Docs used as a centralized and editable knowledge base
- Google Gemini as the LLM for response generation
- Context-aware conversations using n8n Simple Memory
- Strong hallucination prevention via system prompt constraints
- Graceful handling of missing or undocumented information


## Tech Stack

- n8n – Workflow automation and orchestration
- Google Gemini – Large Language Model (LLM)
- Google Docs – Knowledge base storage
- n8n Simple Memory – Conversation context management
- Telegram Bot API – User interaction layer


## Workflow Architecture

1. User sends a query through Telegram
2. n8n captures the message via Telegram Trigger
3. Previous context is retrieved using n8n Simple Memory
4. Relevant knowledge is fetched from Google Docs
5. Query, context, and knowledge base are passed to Google Gemini
6. Gemini generates a response following the system prompt rules
7. The final answer is sent back to the Telegram chat




## Demo

- n8n workflow visualization
- GIF demonstrating live interaction with the Telegram bot



## Knowledge Base

- Implemented using Google Docs
- Contains structured company information including:
  - Company overview and mission
  - Products and pricing
  - Account management and billing
  - Security, privacy, and compliance
  - Integrations and API details
  - SLA and support information
- The AI agent is restricted to using only this documented information


## System Prompt Design (Hallucination Prevention)

A carefully crafted **system prompt** is used to strictly control the LLM’s behavior.

### Core Principles

- The knowledge base is the **single source of truth**
- The model must cross-reference the Google Doc for every response
- The model is explicitly forbidden from:
  - Making assumptions
  - Guessing missing details
  - Providing undocumented or speculative information

### Behavior When Information Is Missing

If a user asks a question that is not covered in the knowledge base, the agent:
- Clearly states that the information is not available
- Does not fabricate or infer an answer
- Suggests contacting official support when appropriate

This design significantly reduces hallucinations and improves trustworthiness.


## Challenges Faced

- Integrating the Google Docs API was time-consuming and complex compared to previous projects
- Managing authentication, permissions, and document access required careful configuration


## License

This project is created for educational and demonstration purposes only.  
All company data, policies, and branding are fictional.


