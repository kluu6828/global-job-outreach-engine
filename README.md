# Global Multi-Region Job Application & Persona-Tailored Outreach System

A semi-autonomous GTM and job search engine built to eliminate application fatigue using a deterministic n8n state-flow architecture.

---

## 🏗️ System Architecture & Data Flow

1. **Multi-Region Cron Triggers:** Runs daily scheduled cron jobs across APAC (HK/SGP), Canada (Toronto), and the USA (TX/FL/NYC).
2. **Scraping & LLM Filtering (Apify & Google AI Studio):** 
   - Apify scrapes live job listings.
   - Custom LLM nodes evaluate job-fit scores and prioritize Tier 1 targets.
3. **Dynamic Tailoring & PDF Generation (PDFShift):** 
   - Dynamically tailors resume bullet points to match the specific job description.
   - Formats the clean output into professional HTML/PDF files hosted on cloud storage.
4. **Enrichment & Multi-Channel Push (Prospeo & Instantly):** 
   - Finds verified decision-maker emails via Prospeo domains.
   - Pushes personalized hooks, custom merge tags, and sequences directly into Instantly.
5. **Resilience, Webhooks & Error Handling:** 
   - Includes webhook listeners for positive responses and a global error-handling node tied to a Telegram bot for real-time alerting.

---

## 📂 Repository Contents
- `/workflows/n8n-workflow-template.json`: The complete exportable n8n state machine workflow template.
- `/docs`: Architecture diagrams and workflow breakdowns.
