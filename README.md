# 🤖 AI News Summarizer & Daily Tech Briefing

> An AI-powered news automation system built with **n8n** and **Google Gemini** that collects AI and technology news, generates concise summaries, and delivers a daily technology briefing by email.

## 🚀 Overview

Keeping up with the rapidly changing AI and technology landscape can be time-consuming.

This project automates the process of collecting and summarizing relevant news. It uses scheduled workflow automation to fetch news from RSS feeds, combine the collected articles, process them with Google Gemini, and deliver a concise daily briefing through email.

## ✨ Features

* 📰 Collects AI news from an RSS feed
* 💻 Collects broader technology news from an RSS feed
* 🔄 Combines news from multiple sources
* 🧠 Uses Google Gemini for AI-powered summarization
* 📑 Organizes news into AI and Technology sections
* ✂️ Produces concise 1–2 sentence summaries
* 🔗 Preserves article links
* ⏰ Runs automatically on a scheduled trigger
* 📧 Delivers the final briefing through email

## 🏗️ Workflow Architecture

```text
                    ┌──────────────────┐
                    │  Schedule Trigger │
                    └────────┬─────────┘
                             │
                  ┌──────────┴──────────┐
                  │                     │
                  ▼                     ▼
          ┌──────────────┐      ┌──────────────┐
          │   AI News    │      │  Tech News   │
          │   RSS Feed   │      │   RSS Feed   │
          └──────┬───────┘      └──────┬───────┘
                 │                     │
                 └──────────┬──────────┘
                            ▼
                     ┌────────────┐
                     │    Merge   │
                     └─────┬──────┘
                           ▼
                    ┌─────────────┐
                    │  Aggregate  │
                    └──────┬──────┘
                           ▼
                  ┌──────────────────┐
                  │  Google Gemini   │
                  │  AI Summarizer   │
                  └────────┬─────────┘
                           ▼
                    ┌─────────────┐
                    │ Email Brief │
                    └─────────────┘
```

## 🔄 How It Works

### 1. Scheduled Trigger

The workflow starts automatically using a scheduled trigger.

### 2. Collect AI News

The workflow reads AI-related articles from an RSS feed.

### 3. Collect Technology News

A second RSS feed provides broader technology news.

### 4. Merge & Aggregate

The two streams are merged and aggregated into a combined collection of news items.

### 5. AI Summarization

The collected articles are passed to a Google Gemini-powered LLM chain.

The prompt instructs the model to:

* Use only the provided news items
* Avoid inventing information
* Separate AI news from broader technology news
* Select relevant stories
* Generate concise summaries
* Preserve article links

### 6. Email Delivery

The generated technology briefing is sent as an email containing the summarized news.

## 📰 News Sources

The current workflow uses RSS feeds from:

* **AI Business** — AI-focused news
* **TechCrunch** — broader technology news

## 🛠️ Technologies Used

| Technology        | Purpose                                     |
| ----------------- | ------------------------------------------- |
| **n8n**           | Workflow automation                         |
| **Google Gemini** | AI-powered news summarization               |
| **RSS Feeds**     | News ingestion                              |
| **Gmail**         | Automated email delivery                    |
| **LLM Prompting** | Structured summarization and categorization |

## ⚙️ Setup

### Prerequisites

Before running this workflow, you need:

* An **n8n** instance
* A **Google Gemini API credential**
* A **Gmail account/credential**
* Internet access for RSS feeds

### Import the Workflow

1. Open your n8n instance.
2. Create or open a workflow.
3. Use **Import from File**.
4. Select the workflow JSON from this repository.
5. Configure your own credentials.
6. Review the RSS feed configuration.
7. Configure the destination email.
8. Test the workflow.
9. Activate the workflow when everything works correctly.

> ⚠️ **Security:** Never commit API keys, OAuth tokens, passwords, private credentials, or personal configuration values to GitHub. Configure your own credentials inside n8n.

## 📧 Example Output

The generated briefing is structured into:

```text
Hi there,
Here's your Tech Brief:

AI NEWS
=======

HEADLINE

Summary...

Link: <article link>

TECHNOLOGY UPDATES
==================

HEADLINE

Summary...

Link: <article link>
```

## 🎯 Project Goals

This project demonstrates how AI and workflow automation can be combined to transform raw information into a useful, automatically delivered daily briefing.

It also provides practical experience with:

* Workflow orchestration
* RSS-based data ingestion
* Data aggregation
* LLM integration
* Prompt engineering
* Automated communication
* AI-powered information processing

## 🔮 Future Improvements

Potential improvements include:

* Add more news sources
* Add configurable news categories
* Add keyword-based filtering
* Add duplicate-news detection
* Add HTML email formatting
* Add personalized topics
* Add a web dashboard
* Add database storage for historical news
* Add article ranking based on relevance
* Add error handling and monitoring

## 👨‍💻 Author

**THOD2006**

Built as a practical AI automation project using **n8n** and **Google Gemini**.

---

⭐ If you find this project useful, consider giving the repository a star!
