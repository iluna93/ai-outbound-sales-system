# 🎯 AI Outbound Sales System

Automated end-to-end outbound sales system built with n8n and GPT-4.1. Scrapes leads from Google Maps, enriches them with web data, and generates hyper-personalized WhatsApp icebreakers — all on autopilot.

## 🎯 The Problem

Manual outbound sales is slow and generic. Finding leads, researching each business, and writing personalized messages one by one takes hours. Most cold messages get ignored because they're obviously templated.

## ✅ The Solution

A two-workflow system that goes from zero to ready-to-send personalized WhatsApp messages in minutes — fully automated.

## 🔄 How It Works

### Workflow 1 — Lead Scraper (`AGENTE_ALMACENAMIENTO_LEADS`)
1. Scrapes Google Maps by niche and city
2. Extracts business websites and contact info
3. Scrapes each business website
4. Extracts emails automatically
5. Deduplicates URLs to avoid repeats
6. Saves enriched leads to Google Sheets

### Workflow 2 — WhatsApp IceBreaker Generator
1. Reads leads from Google Sheets (only those without a message yet)
2. Cleans and normalizes website URLs
3. Scrapes each business website in real time
4. Strips HTML and extracts clean text (first 4,000 chars)
5. Sends to GPT-4.1 with a detailed prompt to generate:
   - A hyper-personalized WhatsApp message (max 70 words) referencing a specific detail from their website
   - The country detected from the website
   - The phone number converted to international WhatsApp format
6. Builds a ready-to-click `wa.me` link with the message pre-filled
7. Saves everything back to Google Sheets

## 🧠 AI Prompt Strategy

The GPT-4.1 prompt is engineered to:
- Reference a **specific, non-obvious detail** from the business website (not the generic industry)
- Connect that detail to a **real pain point** specific to that type of business
- Write in a **casual, human tone** — sounds handwritten, not templated
- Auto-detect the **country** from domain, address, currency, and language signals
- Convert local phone numbers to **international WhatsApp format** for 10+ Latin American countries

## 🛠️ Tech Stack

- **n8n** — workflow orchestration
- **GPT-4.1 (OpenAI)** — message generation and country detection
- **Google Maps** — lead sourcing
- **Google Sheets API** — lead database and output storage
- **HTTP Request** — website scraping
- **Custom JavaScript** — HTML cleaning, URL normalization, phone formatting

## 📊 Results

Used for real outbound campaigns targeting Latin American businesses across Ecuador, Colombia, Argentina, Peru, Chile and more. Generates ready-to-send personalized messages at scale in minutes instead of hours.

## 🔧 Built By

Designed and deployed by **Iván Luna** — AI Automation Specialist at [Lunar Projects](https://lunarprojects.net)
