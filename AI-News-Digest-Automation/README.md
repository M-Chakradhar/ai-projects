# 🚀 AI News Digest Automation (Last 24 Hours)

An automated workflow that fetches the most relevant **AI-related news from the last 24 hours**, summarizes it into **concise, email-ready updates**, and delivers it directly to your inbox.

Built using **n8n**, **Perplexity Sonar Pro**, **Google Gemini**, and **Gmail**, this project removes the need to manually track daily AI news.

## ✨ Features

- ⏰ Scheduled daily execution
- 🔎 Real-time AI news retrieval (last 24 hours)
- 🧠 Multi-model architecture (retrieval + summarization)
- ✉️ Clean, readable email delivery via Gmail
- 🧾 Concise summaries (≤ 50 words per article)
- 🔁 Fully automated end-to-end workflow


## 🧠 Architecture Overview

This project uses **two AI agents**, each with a clearly defined responsibility:

### 1. AI News Retrieval Agent (Perplexity Sonar Pro)
- Fetches AI-related news articles from the last 24 hours
- Returns raw, structured data (title, URL, date, source, article text)
- No summarization or formatting

### 2. AI News Formatting Agent (Google Gemini)
- Consumes the full article content
- Generates a neutral, factual summary (max 50 words)
- Formats output specifically for email delivery


## 🔄 Workflow Overview (n8n)

The automation pipeline consists of the following steps:

1. **Schedule Trigger**
   - Runs automatically at a defined interval (e.g., daily)

2. **AI News Retrieval Agent**
   - Uses Perplexity Sonar Pro to fetch AI news from the last 24 hours

3. **AI News Formatting Agent**
   - Uses Google Gemini to summarize and format each article

4. **Gmail**
   - Sends the formatted AI news digest to the configured email address


## 🧩 n8n Workflow

<p align="left">
  <img
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-News-Digest-Automation/AI_News_Digest_Automation_Wokflow.png?raw=true"
    alt="n8n Workflow"
    width="600"
  />
</p>

> The workflow shows the schedule trigger, retrieval agent, formatting agent, memory node, and Gmail integration.


## 📧 Email Output Example

<p align="left">
  <img
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-News-Digest-Automation/Email_Received_Through_Automation.png?raw=true"
    alt="Email & Workflow"
    width="600"
  />
</p>

<p align="left">
  <img
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-News-Digest-Automation/Gmail_Received_Through_Automation.png?raw=true"
    alt="Email Output"
    width="600"
  />
</p>

Each email contains:
- Refined headline
- 50-word summary
- Source and publication date
- Read more link


## 🎥 Demo

A GIF demonstrating the full workflow execution and email delivery is included below:

<p align="left">
  <img
    src="https://github.com/M-Chakradhar/ai-projects/blob/main/AI-News-Digest-Automation/AI_News_Automation_Workflow_Demo.gif?raw=true"
    alt="Workflow Execution Demo"
    width=700"
  />
</p>



## 🛠️ Tech Stack

- **n8n** – Workflow automation
- **Perplexity Sonar Pro** – Real-time AI news retrieval
- **Google Gemini** – Article summarization and formatting
- **Gmail API** – Email delivery

