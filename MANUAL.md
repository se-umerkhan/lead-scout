# Lead Scout — Manual

## Requirements

- A working n8n instance
- A Google account and Google Sheets spreadsheet
- Google Cloud OAuth credentials
- Access to the business-search API used by the workflow
- Email provider credentials if outreach is configured

## Installation

1. Import `lead_scout.json` into n8n.
2. Open the workflow and configure its required credentials.
3. Connect the correct Google spreadsheet.
4. Verify the input tab names, column headers, and output tab.
5. Configure the business-search API node.

## Google Sheets

Maintain separate inputs for locations and business niches, plus a dedicated output tab.

Example locations:
- F-7 Markaz, Islamabad
- Blue Area, Islamabad

Example niches:
- Dental Clinics
- Restaurants
- Real Estate Agencies

Use the exact tab names and column headers expected by the imported workflow.

## Google OAuth Setup

1. Create a project in Google Cloud Console.
2. Enable the Google Sheets API and Google Drive API if required.
3. Configure the OAuth consent screen.
4. Create OAuth client credentials.
5. Add the exact redirect URI shown by n8n.
6. Connect the credential in n8n and authorize access.

## Execution

1. Start with one location and one niche.
2. Execute the workflow manually.
3. Confirm that the search returns business records.
4. Verify that the results appear in the correct output tab.
5. Test multiple locations and niches to confirm iteration works correctly.

## Email Outreach

Email outreach is a separate stage and depends on the configured workflow.

Before enabling it, verify recipient addresses, test the message template, and implement appropriate sending limits and safeguards. An available email address is not necessarily verified or eligible for marketing outreach.

## Troubleshooting

- **No results:** Check search parameters, API credentials, and provider limits.
- **Only one target processed:** Inspect the iteration nodes and their connections.
- **Google Sheets errors:** Check OAuth authorization, spreadsheet access, and column mappings.
- **Missing email addresses:** Confirm whether the configured provider returns emails or whether enrichment is required.
- **Duplicate results:** Add deduplication using a stable business identifier where available.

## Security

Keep API keys, OAuth secrets, and email credentials in n8n's credential manager. Never commit secrets or personal access tokens to the repository.

