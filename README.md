# web-scrapping
 Denver Real Estate Lead Scraper (March 2026)

## Project Overview

This project is an **automated real estate lead extraction and enrichment system** for **Denver, Colorado**. It focuses on single-family homes that have been on the market for **60+ days**, producing a curated dataset of high-intent leads ideal for **investors, wholesalers, and market analysts**.

## Extraction & Filtering Criteria

The scraper ensures **relevant and high-quality data** by following these rules:

* **Location:** Denver, CO (validated via URL and address parsing)
* **Property Type:** Single-family homes only (Condos, Townhomes, Apartments, and Units are excluded)
* **Price:** Maximum of $600,000
* **Days on Market (DOM):** Listings with 60 or more days on Redfin

## Dataset Schema

The final output, `denver_leads_final_perfect.csv`, contains:

| Column           | Description                                                     |
| :--------------- | :-------------------------------------------------------------- |
| **Address**      | Verified street address (single-family homes only)              |
| **Price**        | Current listing price extracted reliably from listing data      |
| **Agent**        | Full name of the primary listing agent                          |
| **Company**      | Brokerage or agency name, parsed from official source text      |
| **Direct Phone** | Correct brokerage contact, **excluding Redfin routing numbers** |
| **Email**        | Predicted professional email (`firstname.lastname@company.com`) |
| **DOM**          | Days on Redfin, cleaned of UI artifacts                         |
| **Link**         | Direct and sanitized property URL                               |

## Technical Approach

* **Automation Engine:** Python 3.10+ with asynchronous browser automation
* **Anti-Bot Handling:** Implemented human-like scrolling and bot detection bypass
* **Data Cleaning & Enrichment:**

  * Sanitized URLs to remove unnecessary parameters
  * Used advanced parsing techniques to extract agent and company names accurately
  * Standardized DOM metric and predicted professional emails
* **Human-in-the-loop Handling:** Script resumes automatically after manual CAPTCHA or “Press and Hold” interactions

## Compliance & Data Integrity

* **Privacy Compliance:** Emails are predicted while respecting privacy, avoiding direct scraping from protected interfaces
* **Data Accuracy:** If a valid brokerage phone number is unavailable, the field defaults to `"Check Brokerage"` to maintain honesty

## Key Professional Highlights

* **Phone Handling:** Properly bypassed Redfin routing numbers for accurate contacts
* **DOM Cleaning:** Removed UI artifacts for reliable numeric data
* **Portfolio Ready:** Demonstrates full-cycle expertise in scraping, cleaning, and enriching high-value real estate data

