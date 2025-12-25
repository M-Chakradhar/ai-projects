# AI Calendar Booking Agent

This project is an AI-powered automation workflow that allows users to create Google Calendar events using natural language through a Telegram bot.


## Overview

The goal of this project is to simplify calendar scheduling by combining conversational AI with workflow automation. Instead of manually opening Google Calendar, users can simply send a message to a Telegram bot describing the event they want to schedule.

The workflow uses an LLM to interpret natural language, validates time and date constraints, creates the event in Google Calendar, and sends a human-readable confirmation back to the user.


## Architecture

The automation is built using n8n as the orchestration layer.

**Workflow Components:**

- Telegram Trigger  
  Receives user messages from the Telegram bot.

- AI Agent (n8n)  
  Acts as the central controller that:
  - Uses an LLM to understand user intent
  - Extracts structured event details
  - Applies validation logic

- Google Gemini Chat Model  
  Used as the LLM for intent understanding and information extraction.

- Simple Memory (n8n)  
  Maintains short-term context during the conversation.

- Google Calendar  
  Creates the calendar event and generates the Event link.

- Telegram Send Message  
  Sends the final confirmation back to the user.
  

## Workflow Diagram

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-Calendar-Booking-Agent/AI%20Calendar%20Booking%20Agent%20Workflow.png?raw=true"
    alt="Workflow Diagram"
    width="600"
  />
</p>

---

## Demo

### Telegram Bot Interaction

The following GIF shows the interaction with the Telegram bot, from user input to successful confirmation.

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-Calendar-Booking-Agent/AI_Calendar_Booking_Agent_Demo.gif?raw=true"
    alt="Telegram Bot Demo"
    width="600"
  />
</p>

---

### Google Calendar Event Creation

The image below shows the event successfully created in Google Calendar with the correct date, time, and Google Event link.

<p align="left">
  <img 
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-Calendar-Booking-Agent/AI%20Calendar%20Booking%20Agent%20Screenshot.png?raw=true"
    alt="Google Calendar Event"
    width="600"
  />
</p>


---

## How It Works

1. The user sends a natural language message to the Telegram bot (for example, “Schedule an AI literacy webinar on 27th December 2025 at 10:00 AM”).
2. The Telegram Trigger in n8n receives the message.
3. The AI Agent uses the Google Gemini model to:
   - Understand the intent
   - Extract event name, date, and time
4. Validation logic ensures:
   - The event is not scheduled in the past
   - The time is correctly interpreted in IST
   - An end time is set (defaults to 1 hour if missing)
5. The Google Calendar node creates the event.
6. A confirmation message with all details and the calendar link is sent back to the user via Telegram.


## System Prompt Design

A carefully designed system prompt ensures the LLM:

- Extracts dates and times accurately
- Does not hallucinate event details
- Respects timezone constraints (IST)
- Avoids double booking or scheduling events in the past
- Produces output in a predictable format suitable for automation

This prompt is critical for making the workflow reliable and deterministic.


## Challenges and Fixes

### Google Calendar Timezone Issue

**Problem:**  
Events were created 5 hours and 30 minutes earlier than the intended time.

**Root Cause:**  
The Google Calendar account timezone was set incorrectly, and missing or ambiguous timezone handling caused the event time to be reinterpreted.

**Fix:**  
- Updated Google Calendar account timezone to Asia/Kolkata (IST)
- Ensured consistent timezone handling across n8n and Google Calendar


## Learnings

- Building end-to-end workflow automations using n8n
- Integrating multiple APIs (Telegram, Google Calendar, LLMs)
- Understanding how LLMs process prompts, tokens, and structured outputs
- Differences in behavior across LLMs
- Importance of prompt engineering for reliable automation
- Debugging real-world timezone issues


## Tech Stack

- Telegram Bot API  
- n8n (Workflow Automation)  
- Google Gemini (LLM)  
- Google Calendar API  
- Simple Memory (n8n)


## Notes

This project was built as a hands-on learning exercise to explore AI agents, workflow automation, and real-world API integrations. It demonstrates how conversational AI can be combined with deterministic systems to build reliable scheduling automation.

