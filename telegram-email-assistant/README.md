# Telegram Email Assistant

An AI-powered Telegram bot that allows users to send emails using natural language.  
The bot understands user intent, composes emails, sends them via Gmail, and confirms delivery within the same Telegram conversation.


## Problem Statement

Sending emails from mobile devices can be slow and inconvenient.  
This project explores how conversational AI and automation can simplify email composition using a chat-based interface.


## What This Bot Does

- Accepts natural language email requests via Telegram
- Understands intent using an LLM
- Extracts email details automatically (recipient, subject, message)
- Sends the email using Gmail
- Confirms successful delivery back to the user

All interactions happen inside a single Telegram chat.


## Demo

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/telegram-email-assistant/demo.gif?raw=true"
    alt="Telegram Email Assistant Demo"
    width="400"
  />
</p>

## Email Delivery Confirmation

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/telegram-email-assistant/Gmail_Confirmation.jpg?raw=true"
    alt="Email received in Gmail sent via Telegram bot"
    width="300"
  />
</p>


## Architecture Overview

This automation is built using the n8n workflow automation platform.

**Workflow Flow:**
1. User sends a message via Telegram
2. Telegram Trigger activates the workflow
3. AI Agent processes the message
4. Google Gemini interprets intent and content
5. Simple Memory maintains conversation context
6. Gmail tool sends the email
7. Confirmation message is sent back to Telegram

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/telegram-email-assistant/Workflow.png?raw=true"
    alt="n8n workflow diagram for Telegram Email Assistant"
    width="650"
  />
</p>


## Tools & Technologies Used

- **n8n** – Workflow automation platform
- **Telegram Bot API** – User interaction interface
- **Google Gemini API** – Language model for intent understanding
- **n8n Simple Memory** – Conversation context handling
- **Gmail API** – Email sending


## Key Design Choices

- Used **natural language** instead of forms or commands
- Implemented **memory** to support conversational follow-ups
- Used **tool calling** to bridge AI reasoning with real actions
- Kept the workflow **simple and modular**


## Limitations

- Supports email sending only
- No attachments
- Uses a single Gmail account
- Optimized for English language input
- Depends on third-party API limits

## Future Enhancements

- Email drafts without sending
- Attachments support
- Scheduled emails
- Multi-account Gmail support
- Analytics and logging


## Why This Project Matters

This project demonstrates:
- Practical use of GenAI in automation
- AI agent orchestration
- API integrations
- Workflow-based system design
- Clear problem-to-solution thinking

