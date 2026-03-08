
# German News Vocabulary AI Agent

An automated AI agent that extracts advanced German vocabulary from daily news articles on Tagesschau and delivers a curated vocabulary digest by email.

## Overview

This project uses an AI agent to scrape the German news site Tagesschau, identify advanced vocabulary (B2–C2), and compile a daily learning digest.

The system automatically:

1. Scrapes current Tagesschau articles
2. Identifies advanced vocabulary useful for learners
3. Deduplicates previously collected words
4. Stores vocabulary in a Google Sheets database
5. Sends a daily email digest with translations and example sentences

The result is a lightweight automated German immersion system based on real news language.

## Architecture

Workflow built with **n8n**:

Schedule Trigger → Vocabulary Agent → Google Sheets → Email Digest

### Tools Used

- **n8n** — workflow orchestration
- **OpenAI model** — AI agent reasoning
- **Google Sheets** — vocabulary storage
- **Gmail** — daily email delivery

## Files in This Repo

- `workflow.json` — exported n8n workflow
- `prompt.md` — AI agent prompt
- `architecture.png` — workflow screenshot
- `example-output.png` — sample email output

## Outputs

The workflow produces two outputs:

### 1. Vocabulary Database (Google Sheets)

Each run appends structured vocabulary entries to a Google Sheet.

Fields stored:

- date
- word_phrase
- translation
- example_sentence
- difficulty
- type
- source_url

This creates a growing personal vocabulary dataset sourced from German news.

### 2. Daily Email Digest

The system also sends a formatted email summarizing the newest vocabulary items for quick review.

Example:

1. völkerrechtswidrig (C1)  
Meaning: contrary to international law  
Example: Nach Einschätzung der allermeisten Völkerrechtsexperten sind die Angriffe der USA und Israels auf Iran völkerrechtswidrig.

2. Handy orten (C1)  
Meaning: to track a mobile phone  
Example: Angesichts dieser Zahlen schlug Hessens Innenminister Roman Poseck vor, nicht auffindbare Migranten per Handyortung zu suchen.

## Importing the Workflow

1. Import `workflow.json` into n8n
2. Connect your OpenAI, Google Sheets, and Gmail credentials
3. Update the Google Sheet target if needed
4. Activate the schedule trigger

## Motivation

I built this project to turn real German news into a daily vocabulary learning system using AI agents, automation, and workflow orchestration.
