# GTM Lead Enrichment Pipeline

## What This Does
An automated pipeline that takes a list of company 
domains and enriches them with firmographic data 
and AI-personalized cold email openers — replacing 
3–4 hours of manual sales research with a 
single script.

## The Problem It Solves
Sales teams waste hours manually researching prospects before outreach. This pipeline automates:
- Company data enrichment (size, industry, LinkedIn)
- Contact finder (decision maker at each company)
- AI-personalized email opener generation

## Tech Stack
- Python (pandas, requests, openai)
- Apollo.io API (company + contact enrichment)
- OpenAI API gpt-4o-mini (personalization)
- Output: enriched CSV ready for CRM import

## How To Run It
```bash
pip install -r requirements.txt
python src/enrichment_pipeline.py
```

## Example Output
| Company | Industry | Employees | AI Email Opener |
|---|---|---|---|
| Linear | Software | 208 | "Loved Linear's issue tracking approach..." |

## Built By
Hrushikesh Medhekar — GTM Engineer  
GitHub: https://github.com/IronhideStark
LinkedIn: https://www.linkedin.com/in/hrushikeshmedhekar/
```

---

## Task 2 — The Python Pipeline (2–3 hours)

Now the core script. Here's exactly what to build.

**First — understand what we're building:**
```
Input CSV (domains) 
→ Apollo API (enrich company data) 
→ OpenAI API (write personalized opener) 
→ Output CSV (enriched + personalized)
```

**Step 1: Get your Apollo API key**
- Log into apollo.io
- Go to Settings → Integrations → API
- Copy your API key
- Keep it safe — never push it to GitHub

**Step 2: Get your OpenAI API key**
- Go to platform.openai.com
- Sign up / log in
- Go to API Keys → Create new key
- Add $5 credit — gpt-4o-mini costs almost nothing

**Step 3: Create a `.env` file in your repo root**
```
APOLLO_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here
```

Then create a `.gitignore` file and add:
```
.env
output/
__pycache__/
```

This prevents your API keys from being pushed to GitHub publicly. Critical step.

**Step 4: Create `requirements.txt`**
```
pandas
requests
openai
python-dotenv
