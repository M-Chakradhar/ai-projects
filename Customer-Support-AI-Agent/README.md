# Aura Intelligence – Customer Support AI Agent

A Telegram-based Customer Support AI Agent built using n8n, Google Gemini, and Google Docs as a knowledge base.  
The agent answers company-related queries directly within Telegram by strictly referencing a predefined knowledge base and a carefully designed system prompt to prevent hallucinations.

## Project Overview

This project demonstrates how to build a knowledge-grounded customer support AI agent using low-code automation and large language models.

Users interact with the agent via Telegram. Queries are answered using a Google Doc–based knowledge base, responses are generated using Google Gemini, and conversation context is preserved using n8n Simple Memory.

The knowledge base represents a dummy AI company (Aura Intelligence) created specifically for this project.

## Key Features

- Telegram-based real-time customer support interface  
- Google Docs as a centralized and editable knowledge base  
- Google Gemini used as the LLM  
- Context-aware conversations using n8n Simple Memory  
- Strict hallucination prevention via system prompt constraints  
- Clear handling of missing or undocumented information  

## Tech Stack

- n8n – Workflow automation and orchestration  
- Google Gemini – Large Language Model  
- Google Docs – Knowledge base storage  
- n8n Simple Memory – Conversation context management  
- Telegram Bot API – User interaction layer  

## Workflow Architecture

1. User sends a query through Telegram  
2. n8n captures the message using the Telegram Trigger  
3. Previous context is retrieved via n8n Simple Memory  
4. Relevant information is fetched from Google Docs  
5. Query, context, and knowledge base are sent to Google Gemini  
6. Gemini generates a response following the system prompt rules  
7. The response is returned to the user in the Telegram chat

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/Customer-Support-AI-Agent/Customer_Support_AgentWorkflow.png?raw=true" 
    alt="Customer Support Agent Workflow" 
    width="600"
  />
</p>


## Demo

### Telegram Interaction Demo

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/Customer-Support-AI-Agent/Customer_Support_Agent_Interaction_Demo.gif?raw=true" 
    alt="Customer Support Agent Interaction Demo" 
    width="600"
  />
</p>

### Agent Demo Screenshot

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/Customer-Support-AI-Agent/Customer_Support_Agent_Demo.png?raw=true" 
    alt="Customer Support Agent Demo" 
    width="600"
  />
</p>


## Knowledge Base

- Implemented using Google Docs  
- Contains structured company information such as:
  - Company overview and mission
  - Products and pricing
  - Account management and billing
  - Security, privacy, and compliance
  - Integrations and API details
  - SLA and support information
- The agent is restricted to using only documented information from this source

## System Prompt Design (Hallucination Prevention)

A carefully designed system prompt is used to control the behavior of the LLM and ensure reliable responses.

### Core Principles

- The Google Doc knowledge base is the single source of truth  
- The model must cross-reference the knowledge base for every response  
- The model is explicitly forbidden from:
  - Making assumptions
  - Guessing missing information
  - Providing undocumented or speculative answers  

### Behavior When Information Is Missing

When a user asks a question that is not covered in the knowledge base, the agent:
- Clearly states that the information is not available  
- Does not fabricate or infer an answer  
- Suggests contacting official support if appropriate  

This approach significantly reduces hallucinations and improves response reliability.

## Challenges Faced

- Integrating the Google Docs API was more complex and time-consuming compared to previous projects  
- Managing authentication, permissions, and document access required careful setup  


## License

This project is created for educational and demonstration purposes only.  
All company data, policies, and branding are fictional.

