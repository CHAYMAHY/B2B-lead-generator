# 🚀 B2B Lead Generation & AI Outreach Automation Engine (n8n)

An end-to-end automated B2B lead generation and cold outreach pipeline built using **n8n**. This workflow automates targeted Google searches, scrapes business data, analyzes and scores leads using Artificial Intelligence (OpenAI), logs them into Google Sheets, and executes personalized automated email outreach via Gmail.

---

## 📸 Workflow Screenshot 





## 🛠️ Tech Stack & Tools

* **n8n:** Core workflow orchestration and automation engine.
* **Apify (Google Search Scraper):** Extracts targeted business leads, websites, and emails based on specific niches.
* **OpenAI API:** Evaluates company profiles, assigns a fit score (0-100), writes a detailed rationale, and crafts hyper-personalized cold emails.
* **Google Sheets API:** Centralized CRM storage to track leads, contact info, scores, timestamps, and pipeline statuses.
* **Gmail API:** Automated dispatch of tailored initial proposals and follow-up sequences.
* **JavaScript / Code Node:** Custom data parsing, formatting, and string manipulation for robust error handling.

---

## ⚙️ Workflow Deep Dive & Step-by-Step Logic

1. **Trigger / Schedule (`Daily Schedule`):** 
   * Initiates the automation pipeline automatically on a scheduled interval or via manual trigger.
2. **Lead Scraping (`Run an Actor and get dataset` - Apify):** 
   * Executes a targeted Google search scraper to extract raw business leads, including company names, official websites, and contact emails.
3. **Data Preparation (`Prepare Lead` & Code Node):** 
   * Cleans and formats incoming JSON data to ensure uniform structure across subsequent nodes.
4. **AI Intelligence & Lead Scoring (`AI Lead Analysis` - OpenAI):** 
   * Passes company details through an advanced LLM prompt. The AI acts as an expert B2B sales strategist, generating a **Fit Score (0-100)**, an analytical rationale, and a custom cold email tailored to the prospect's niche.
5. **Score Filtering (`Filter High Score Leads`):** 
   * Automatically filters out low-potential leads and keeps only high-value prospects (Score $\ge$ 70) for outreach.
6. **CRM Integration & Status Tracking (`Save Lead` - Google Sheets):** 
   * Logs qualified leads into a Google Sheet database along with their evaluation score, timestamp, and initial status (`Offer Sent`).
7. **Automated Outreach (`Send Special Offer` - Gmail):** 
   * Dynamically populates and sends out the AI-generated personalized cold proposal directly to the lead's verified inbox.
8. **Automated Follow-up Sequence (`Not Replied Yet` & `Send Follow-up`):** 
   * Waits for a predefined delay (e.g., 3 days), checks Google Sheets reply status, and triggers automated follow-up emails for prospects who haven't responded yet.

---

## 📂 Repository Structure

```text
├── B2B Lead Generation & Automated Follow-up System.json  # Main n8n workflow export
├── README.md                                              # Project documentation
└── images/                                                # Workflow screenshots directory
