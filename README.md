
# 🧠 AI Powered Job Alert System

An automated job notification workflow that fetches remote programming job listings from **We Work Remotely**, summarizes them using GPT-3.5 Turbo, and delivers curated alerts via Gmail. Built with 💓 by Satyanarayan using `n8n`, OpenAI, and modular code design principles.

## 🚀 Features

- ⏰ **Daily Scheduling**: Triggers every 24 hours via `Schedule Trigger`.
- 📡 **RSS Feed Reader**: Fetches latest job posts from [We Work Remotely](https://weworkremotely.com/categories/remote-programming-jobs.rss).
- 📝 **GPT-Powered Summarization**: Uses OpenAI's GPT-3.5 Turbo to extract:
  - Title, company, location  
  - Responsibilities and requirements  
  - Direct application link (if present)
- ✉️ **Email Delivery**: Sends personalized alerts via Gmail with a human touch:
  ```
  Here’s a new job you might like:
  [job summary]

  🧠 Powered by OpenAI & n8n  
  Made with 💓 by Satyanarayan only for you
  ```

## 🧩 Workflow Overview

graph TD
  A[⏰ Schedule Trigger<br>Triggers every 24 hours] --> B[📡 RSS Feed Read<br>Fetch latest job posts]
  B --> C[🧠 Message a Model (OpenAI)<br>Summarize job details]
  C --> D[🔢 Limit to Last 5 Jobs<br>Filter recent entries]
  D --> E[✉️ Send Email Notification<br>Deliver curated alerts]


### 📦 Node Breakdown

| Node Name         | Description                                       |
|-------------------|---------------------------------------------------|
| Schedule Trigger  | Executes workflow every day                       |
| RSS Feed Read     | Loads remote programming job posts                |
| Message a Model   | Summarizes each post using `GPT-3.5 Turbo`        |
| Code              | Limits output to the latest 5 job entries         |
| Send a message    | Emails job alerts using `gmailOAuth2` credentials |

## ✨ Customization Options

- 🔁 Adjust job fetch frequency via `daysInterval`
- 📂 Swap RSS feed for other job boards
- 🎨 Style email template for branding or tone
- 🤖 Swap GPT model or tweak system prompt for different formats

## 🔒 Credentials Used

- **OpenAI API Key**
- **Gmail OAuth2 Connection**

> ⚠️ Ensure environment variables and API keys are securely stored in your n8n instance.

## 📌 Notes

- Output is recruiter/certification-ready with clean bullet formatting
- Easily extendable to filter by keywords, tags, or seniority level
- Natively supports integration into larger agentic architectures

---

Created with purpose, precision, and Satyanarayan’s signature modularity.  
For questions, improvements, or celebratory GIFs, reach out anytime!
