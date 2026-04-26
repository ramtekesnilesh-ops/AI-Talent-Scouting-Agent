# 🤖 AI Talent Scouting & Engagement Agent

An automated recruitment workflow built with **n8n** and **OpenAI** that parses job descriptions, logs candidate data to Google Sheets, and automates personalized outreach via Gmail.

## 🚀 Overview

This agent is designed to bridge the gap between a raw Job Description (JD) and the first step of candidate engagement. It uses a "Brain" (LLM) to handle the logic and "Tools" (Google Sheets & Gmail) to handle the execution, significantly reducing manual data entry for recruiters.

[Image of an AI recruitment agent workflow diagram]

## 🛠️ Tech Stack

* **Logic Engine:** [n8n](https://n8n.io/) (Self-hosted or Cloud)
* **LLM:** OpenAI GPT-4o / Gemini 1.5 Pro
* **Database:** Google Sheets
* **Communication:** Gmail API
* **Search (Optional):** SerpApi / Apollo.io

## 📋 Features

* **JD Parsing:** Automatically extracts key skills, years of experience, and role requirements from unstructured text.
* **Candidate Logging:** Creates a centralized "Talent Pipeline" spreadsheet automatically.
* **AI Scoring:** Assigns a **Match Score** (1-10) based on JD requirements.
* **Automated Outreach:** Drafts personalized, context-aware emails for high-scoring candidates.
* **Human-in-the-Loop:** Emails are created as **Drafts**, ensuring a recruiter reviews them before they are sent.

## ⚙️ Setup Instructions

### 1. Prerequisites
* An active n8n instance.
* Google Cloud Console account (for Google Sheets and Gmail API credentials).
* OpenAI API Key.

### 2. Google Sheets Setup
Create a Google Sheet with the following headers:
`Name` | `LinkedIn URL` | `Current Role` | `Match Score` | `Interest Score` | `Status`

### 3. n8n Workflow Configuration
1.  Import the `workflow.json` file into n8n.
2.  Connect your **Google Sheets** credentials.
3.  Connect your **Gmail** credentials.
4.  Update the **AI Agent Node**'s System Message with your specific recruitment guidelines.

## 🤖 System Prompt Logic

The agent operates on the following logic:
> "You are an Action-Oriented Recruitment Agent. When a JD is provided, you must immediately use the Google Sheets tool to log details and the Gmail tool to draft an email. Do not ask for permission; execute the tools sequentially."

## 🤝 Contributing

Contributions to improve the scoring logic or add support for LinkedIn Automation are welcome! Please feel free to submit a Pull Request.
