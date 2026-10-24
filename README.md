
# Lead Scout

### From Locations to Leads

Lead Scout is an n8n-powered business discovery and lead generation workflow that automates prospect research using Google Sheets and a business-search API.

Define target locations and business niches, let the workflow discover matching businesses, and collect the results in a structured output sheet. Lead Scout reduces repetitive research and provides a repeatable foundation for prospecting and email outreach.

![Lead Scout Demo](Demo/screenshot.png)

## Features

- **Location-Based Discovery:** Search for businesses across specified areas.
- **Niche Targeting:** Find businesses within selected industries or categories.
- **Automated Iteration:** Process multiple locations and niches through an n8n workflow.
- **Structured Lead Collection:** Store discovered business information in Google Sheets.
- **Contact Data:** Capture available email addresses when supported by the configured data sources.
- **Outreach Tracking:** Record outreach status and sent timestamps in the results sheet when email sending is configured.
- **Email Outreach:** Connect collected leads to an email workflow for prospect communication.

## Workflow

1. Define target locations in the `Locations` sheet.
2. Add business categories to the `Niches` sheet.
3. Read the search criteria through n8n.
4. Iterate through the configured locations and niches.
5. Query the business-search API.
6. Process and organize the returned business records.
7. Write results to the `Results` sheet.
8. Use available contact information in the configured email outreach workflow.
9. Track outreach status and sent timestamps when email sending is enabled.

## Architecture

Google Sheets → n8n → Business Search API → Data Processing → Results Sheet → Email Outreach → Outreach Tracking

## Tech Stack

- **n8n:** Workflow automation and orchestration
- **Google Sheets:** Search inputs, lead storage, and outreach tracking
- **Business Search API:** Business discovery
- **Google OAuth 2.0:** Authorization for Google services
- **Email Integration:** Email outreach and activity tracking

## Getting Started

1. Import [`Workflow/Lead_Scout.json`](Workflow/Lead_Scout.json) into your n8n instance.
2. Configure Google Sheets credentials and the business-search API.
3. Connect the correct spreadsheet and verify the `Locations`, `Niches`, and `Results` sheets.
4. Confirm that column names match the workflow mappings.
5. Test the workflow with one location and one niche.
6. Verify the results before expanding the search.
7. Configure email credentials and test outreach if using the email functionality.

See [Manual.md](Manual.md) for setup instructions.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
