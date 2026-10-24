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

## Google Sheets Structure

Lead Scout uses Google Sheets to manage search inputs and store discovered leads. The spreadsheet contains three logical sheets.

### 1. Locations

Defines the geographic areas to search.

| Column | Description |
|---|---|
| `Locations` | The target area or location to search. |
| `Status` | Tracks the processing status of the location. |

### 2. Niches

Defines the business categories to discover.

| Column | Description |
|---|---|
| `Niches` | The business niche or category to search for. |

### 3. Results

Stores the business records collected by the workflow and tracks outreach activity.

| Column | Description |
|---|---|
| `Name` | Name of the discovered business. |
| `Address` | Business address returned by the search provider. |
| `Place ID` | Unique place identifier, when provided by the search API. |
| `Location` | Target location associated with the search. |
| `Category` | Business niche or category used for discovery. |
| `Email` | Available business email address. |
| `Outreach Status` | Tracks the email outreach state. |
| `Sent At` | Timestamp when the outreach email was sent. |

**Important:** Use these exact column names and capitalization in Google Sheets. The spreadsheet structure must match the field mappings configured in the n8n workflow.


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

