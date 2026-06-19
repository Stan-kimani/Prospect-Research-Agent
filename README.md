# Prospect-Research-Agent
> An intelligent daily prospecting system built with **n8n** that automatically finds, researches, and enriches marketing agencies in East Africa (Kenya, Uganda, Tanzania) and saves them to Google Sheets.

![n8n](https://img.shields.io/badge/n8n-Workflow-blue)
![AI Powered](https://img.shields.io/badge/AI-Powered-brightgreen)
![Apify](https://img.shields.io/badge/Apify-Search-orange)
![Firecrawl](https://img.shields.io/badge/Firecrawl-Scraping-red)

## ✨ Features

- **Daily Automated Trigger** – Runs every morning at 9 AM EAT
- **AI-Powered Research Agent** – Uses Claude 3.5 Haiku via OpenRouter
- **Multi-tool Integration**:
  - Apify Google Search Scraper
  - Firecrawl website scraping
- **Smart Data Enrichment** – Extracts company info, emails, decision makers, LinkedIn, etc.
- **Google Sheets Integration** – Automatically appends clean prospects
- **Robust Parsing** – Multiple fallback mechanisms to handle AI output
- **Configurable** – Easy to change target industry, location, or number of prospects

## 🛠️ Tech Stack

- **n8n** – Workflow automation
- **Claude 3.5 Haiku** (via OpenRouter)
- **Apify** – Google Search scraping
- **Firecrawl** – Website content extraction
- **Google Sheets** – Lead storage
- **JavaScript Code Nodes** – Data cleaning & parsing

## 📋 How It Works

1. **Daily Trigger** fires at 9 AM
2. **Config Node** sets search parameters (Industry, Location, ICP, etc.)
3. **AI Research Agent** coordinates between tools
4. **Apify Tool** searches for marketing agencies
5. **Firecrawl Tool** scrapes websites for contact info
6. **Parsing Nodes** clean and structure the AI output
7. **Google Sheets** appends new prospects

## 🚀 Setup & Installation

### Prerequisites

- n8n instance (self-hosted or cloud)
- Apify account + API key
- OpenRouter account + API key
- Google Service Account (for Sheets access)
- Firecrawl API key

### Import Workflow

1. Download the workflow JSON file
2. In n8n, go to **Workflows** → **Import from File**
3. Import `Prospect Research.json.`
4. Set up credentials:
   - Apify API
   - OpenRouter API
   - Google Sheets OAuth2
   - Firecrawl Bearer Token

### Configuration

Edit the **"Config"** node to change:
- Industry
- Target countries
- Number of prospects per run
- Ideal Customer Profile (ICP)

## 📊 Output

The workflow appends the following fields to your Google Sheet:

- `company`
- `industry`
- `location`
- `website`
- `email`
- `phone`
- `company_size`
- `description`
- `decision_maker`
- `decision_maker_title`
- `linkedin`
- `score`
- `priority`
- `score_reason`
- `source`
- `date_added`

## 🔧 Customization

- Change search queries in the **"Edit Fields"** node
- Modify prompt instructions in the **Research Agent**
- Adjust scoring logic in the parsing nodes

## 📝 License

MIT License – feel free to use and modify.

## 🙏 Acknowledgments

Built with ❤️ using n8n, Apify, Firecrawl, and OpenRouter.

---
