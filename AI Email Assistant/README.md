# AI-Powered Email Assistant

This project demonstrates an AI-powered email assistant built using **n8n**.  
Users can interact with the system through a publicly available chat interface, and the AI agent automatically understands the request, generates a complete email, and sends it via **Gmail**.

The goal of this project is to show how conversational AI can be combined with workflow automation to fully automate email creation and delivery.


## Architecture Overview

<div align="center">
  <img src="media/n8n_workflow.png" alt="n8n Workflow Architecture" width="850"/>
</div>

The workflow is built entirely in **n8n** and consists of the following components:

1. **Chat Trigger**  
   Receives messages from a public chat interface.

2. **AI Agent**  
   Interprets user intent and decides how the email should be written and sent.

3. **Google Gemini Chat Model**  
   Provides the language understanding and generation capabilities.

4. **Simple Memory**  
   Maintains conversational context when required.

5. **Gmail Node**  
   Sends the generated email automatically.

---

## Email Delivery Example

<div align="center">
  <img src="media/email_example.png" alt="Email Sent via Gmail" width="850"/>
</div>

The email shown above is generated and sent entirely by the AI agent based on a simple user instruction.

---

## Live Demo

The following demo shows the complete interaction flow:
- User sends a message in the chat
- The AI agent interprets the request
- The email is generated and sent automatically

<div align="center">
  <img src="media/demo.gif" alt="AI Email Assistant Demo" width="900"/>
</div>

---

## How It Works

1. A user sends a message through the chat interface.
2. n8n triggers the workflow when the message is received.
3. The AI agent analyzes the request and determines email requirements.
4. The agent generates a complete, well-structured email.
5. The Gmail node sends the email automatically.

This entire process happens in real time with no manual intervention.

---

## Requirements

- n8n (self-hosted or n8n cloud)
- Google Gemini API access
- Gmail account with OAuth configured in n8n

---

## Setup Instructions

1. Import the workflow into n8n.
2. Configure credentials for:
   - Google Gemini Chat Model
   - Gmail
3. Connect or expose a public chat interface to the workflow trigger.
4. Activate the workflow.
5. Start sending messages through the chat interface.

---

## Use Cases

- Automated email drafting and sending
- AI-powered virtual assistants
- Workflow-driven communication tools
- Rapid prototyping of AI agents with real-world actions

---

## Notes

- The AI agent dynamically determines email structure and content.
- No hardcoded email templates are used.
- The behavior of the agent is controlled via a system prompt.

---

## Future Enhancements

- Email preview before sending
- Support for attachments
- Multiple email provider support
- Enhanced logging and error handling

---

## License

MIT License
