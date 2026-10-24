# Lead Scout

### From Locations to Leads

Lead Scout is an n8n-powered business discovery and lead generation workflow that automates prospect research using Google Sheets and a business-search API.

Define your target locations and business niches, let the workflow discover matching businesses, and collect the results in a structured output sheet. Lead Scout reduces repetitive research and creates a foundation for scalable outreach, offering an alternative to manually searching for prospects and sending cold emails one by one.

![Lead Scout Demo](asset/demo.png)

## Features

- **Location-Based Discovery:** Search for businesses across specified areas.
- **Niche Targeting:** Find businesses within selected industries or categories.
- **Automated Iteration:** Process multiple search targets through an n8n workflow.
- **Structured Lead Collection:** Store discovered business information in Google Sheets.
- **Contact Data:** Capture available email addresses when supported by the configured data sources.
- **Outreach Potential:** Connect collected leads to an email workflow for personalized, scalable outreach.

## Workflow

1. Define locations and niches in Google Sheets.
2. Read the search criteria through n8n.
3. Query the configured business-search API.
4. Process and organize the returned business records.
5. Write results to the output sheet.
6. Use available contact information for a separately configured outreach process.

## Architecture

Google Sheets → n8n → Business Search API → Data Processing → Google Sheets Output → Optional Email Outreach

## Tech Stack

- **n8n:** Workflow automation
- **Google Sheets:** Input management and lead storage
- **Business Search API:** Business discovery
- **Google OAuth 2.0:** Google service authorization
- **Email Integration:** Optional outreach automation

## Getting Started

1. Import `lead_scout.json` into your n8n instance.
2. Configure Google Sheets credentials and the business-search API.
3. Connect the correct spreadsheet and input/output tabs.
4. Test with one location and one niche.
5. Verify the results before expanding the search.

See [MANUAL.md](MANUAL.md) for setup instructions.

## Important Notes

Business discovery does not guarantee verified email addresses, qualified prospects, or successful email delivery. Email enrichment and outreach depend on the configured integrations. Follow applicable API terms, privacy requirements, and email marketing regulations.

## License

Distributed under the MIT License if the included `LICENSE` file specifies MIT.

---
