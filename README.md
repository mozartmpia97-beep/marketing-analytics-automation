================================================================================
Marketing Analytics Automation Platform — API-Based Reporting Data Foundation
================================================================================

A modular Python automation platform that replaced fragmented, manual marketing
data exports with a repeatable API-based extraction workflow for web analytics
and newsletter performance reporting.

Built for a Brussels-based non-profit / economic development organisation with
limited analytics maturity, no dedicated BI infrastructure, no Power BI Service
budget at the start of the mission, and a Mac-first operating environment.

The system automates extraction from Google Analytics 4 and Mailchimp, writes
structured CSV outputs, supports multiple GA4 properties, handles OAuth
authentication, applies API pagination and date chunking, and provides local
execution launchers so non-technical users can refresh reporting data without
editing Python code.

The project was not only a dashboarding assignment. The core value was upstream:
creating a lightweight, maintainable data foundation that could feed Power BI,
Excel, Looker Studio, future databases, and eventually AI-assisted analytics.

All client-identifying information, credentials, tokens, folder paths, and
production data have been removed from this portfolio version.


--------------------------------------------------------------------------------
IMPACT AT A GLANCE
--------------------------------------------------------------------------------

Before     Marketing and web analytics data was spread across several platforms
           and accessed mainly through native application interfaces.

           Reporting required manual consultation or export from tools such as
           Google Analytics, Mailchimp, social media platforms, and event/action
           files.

           No standardized, recurring, cross-channel analytics dataset existed.

After      Automated Python extraction workflow for Google Analytics 4 and
           Mailchimp.

           Repeatable CSV outputs for Power BI, Excel, Looker Studio, or other
           reporting tools.

           Multi-property GA4 extraction with separate OAuth credentials and
           tokens per property.

           Mailchimp campaign report export with incremental state tracking.

           Windows and macOS launcher approach for non-technical users.

Scope      Digital performance reporting:
             - Website traffic
             - Newsletter performance
             - Campaign engagement
             - Traffic source analysis
             - Year-over-year reporting foundation
             - Future extension toward social, event, and action data

Users      Marketing, communication, project, and business stakeholders.

Outputs    CSV files
           Reporting-ready datasets
           Documentation
           Power BI report prototype / base model
           Architecture diagrams
           Handover material

Outcome    Reduced dependency on manual platform exports.
           Improved reproducibility.
           Improved data consistency.
           Created a reusable analytics foundation.
           Prepared the organisation for more advanced BI and AI use cases.


--------------------------------------------------------------------------------
THE PROBLEM
--------------------------------------------------------------------------------

The organisation needed to monitor and report on digital and communication
performance across several channels:

  - Website activity
  - Newsletter performance
  - Social media statistics
  - Events and project-related actions
  - Registrations and participation metrics

At the start of the mission, data was not centralized or structured in a
homogeneous way. Most insights were obtained by consulting native interfaces
directly, such as Google Analytics, Mailchimp, and social media analytics tools.

The existing situation created several operational and analytical issues:

  - Manual exports from multiple platforms
  - No systematic historical extraction process
  - No recurring centralized dataset
  - Heterogeneous formats between platforms
  - Different metric definitions depending on the source system
  - Limited ability to compare channels
  - Limited ability to track trends over time
  - Dependence on users with access to each source platform
  - No reliable foundation for recurring dashboarding
  - No AI-ready data layer

The organisation had already defined business indicators, but these indicators
were not yet supported by a sustainable technical process. KPI lists existed,
but there was no reliable operating model for extracting, structuring,
refreshing, validating, and sharing the underlying data.

A pure dashboard solution would not have solved the underlying issue. The
actual bottleneck was data availability and repeatability.

The real question was:

  How do you create a practical analytics foundation for an organisation that
  has marketing data, but no mature data platform?


--------------------------------------------------------------------------------
CONSTRAINTS
--------------------------------------------------------------------------------

The solution was designed under real-world consulting constraints:

  - Limited budget
  - No dedicated data warehouse
  - No guaranteed Power BI Service licensing
  - Mac-first client environment
  - Non-technical operational users
  - Multiple external SaaS platforms
  - API authentication requirements
  - Different Google accounts / properties
  - Need for handover and autonomy
  - Need for minimal operational complexity	

The architecture therefore had to be:

  - Lightweight
  - Local-first
  - Transparent
  - Maintainable
  - Low-cost
  - Portable across Windows and macOS
  - Simple enough for non-technical users to operate
  - Structured enough for technical users to extend


--------------------------------------------------------------------------------
THE SOLUTION
--------------------------------------------------------------------------------

A Python-based automation platform was designed and delivered to extract,
standardize, and export marketing analytics data.

The platform consists of:

  1. GA4 extraction scripts
  2. Mailchimp extraction script
  3. OAuth authentication files and token handling
  4. CSV export layer
  5. Local execution launchers
  6. Power BI reporting prototype / base model
  7. AS-IS / TO-BE documentation
  8. Technical handover documentation
  9. Architecture diagrams for progressive maturity levels

The central design principle:

  The complexity should live in the technical layer.
  The user should only interact with a button, launcher, or scheduled task.

This means the user does not need to understand OAuth, API pagination,
date chunking, token refreshes, Python environments, or request structures.


--------------------------------------------------------------------------------
HIGH-LEVEL ARCHITECTURE
--------------------------------------------------------------------------------

  +-----------------------+        +---------------------------+
  | Google Analytics 4    |        | Mailchimp                 |
  | Multiple properties   |        | Campaign reports          |
  +-----------+-----------+        +-------------+-------------+
              |                                  |
              | Google Analytics Data API        | Mailchimp API
              | OAuth 2.0                        | API key auth
              v                                  v
  +----------------------------------------------------------------+
  |                    Python Extraction Layer                     |
  |                                                                |
  |  - Authentication handling                                     |
  |  - API requests                                                |
  |  - Pagination                                                  |
  |  - Monthly date chunking                                       |
  |  - Error handling                                              |
  |  - Data normalization                                          |
  |  - CSV writing                                                 |
  |  - Logging / console traceability                              |
  +----------------------------------------------------------------+
              |
              v
  +----------------------------------------------------------------+
  |                         CSV Export Layer                       |
  |                                                                |
  |  exports/                                                      |
  |    website_property_A.csv                                      |
  |    website_property_B.csv                                      |
  |    mailchimp campaign report files                             |
  +----------------------------------------------------------------+
              |
              v
  +----------------------------------------------------------------+
  |                    Reporting / Analytics Layer                 |
  |                                                                |
  |  - Power BI Desktop                                            |
  |  - Power Query                                                 |
  |  - Excel                                                       |
  |  - Looker Studio                                               |
  |  - Future database layer                                       |
  |  - Future AI assistant / natural language analytics            |
  +----------------------------------------------------------------+


--------------------------------------------------------------------------------
ARCHITECTURE EVOLUTION
--------------------------------------------------------------------------------

The project considered multiple levels of maturity.

V0.1 — Local Reporting Prototype

  Sources:
    - Google Analytics
    - Mailchimp
    - Social media platforms
    - Event and action CSV files

  Processing:
    - Manual or semi-manual CSV extracts
    - Power Query for cleaning and transformation
    - Power BI Desktop as the local modelling and reporting tool

  Sharing:
    - PBIX file sharing between users

  Limitation:
    Sharing PBIX files directly is free, but creates operational risks:
      - Users need Power BI Desktop installed
      - Files can be modified accidentally
      - Collaboration is limited
      - Report distribution is not controlled

V1.0 — Shared Reporting Architecture

  Processing remains local or file-based, but reports can be published to a
  shared BI service.

  Benefits:
    - Dynamic report sharing
    - Centralized report access
    - Reusable semantic models
    - Better collaboration

  Constraint:
    Requires licensing and organisational acceptance.

V2.0 — Programmatic Data Foundation

  The delivered Python automation moves the architecture closer to a V2 data
  foundation by introducing programmatic extraction through APIs.

  Benefits:
    - Less manual extraction
    - More reproducible data refreshes
    - Better historical continuity
    - Cleaner path toward cloud storage, databases, and AI


--------------------------------------------------------------------------------
SCRIPTS
--------------------------------------------------------------------------------

  EntreprendreBruxellesGAEXP.py     274 lines    9 functions
  export_ga4_two_properties.py      295 lines    9 functions    1 dataclass
  export_localguide_ga4.py          245 lines    8 functions    1 dataclass
  ga4_auth_localguide.py             27 lines    1 function
  ga4_extract_basic.py               88 lines    2 functions
  export_mailchimp_reports.py       233 lines   13 functions
  Run_GA4_Export.bat                 60 lines
  run_mailchimp_export.bat           16 lines

  Total Python code                 1162 lines
  Total Python functions              42 functions
  Total launcher code                 76 lines

  Total scanned implementation       1238 lines


--------------------------------------------------------------------------------
TECHNICAL STACK
--------------------------------------------------------------------------------

  Language             Python 3.x

  APIs                 Google Analytics Data API
                       Mailchimp Marketing API

  Authentication       OAuth 2.0 for Google Analytics 4
                       API key authentication for Mailchimp

  Python libraries     google-analytics-data
                       google-auth
                       google-auth-oauthlib
                       pandas
                       python-dateutil
                       requests

  Standard library     csv
                       os
                       re
                       time
                       json
                       pathlib
                       datetime
                       dataclasses
                       typing

  Reporting            Power BI Desktop
                       Power Query
                       Excel
                       Looker Studio considered as low-cost alternative

  Output formats       CSV
                       JSON for state and token/config handling

  Execution            Windows batch launchers
                       macOS shell launcher design
                       Optional scheduling through OS-level task schedulers


--------------------------------------------------------------------------------
FOLDER STRUCTURE
--------------------------------------------------------------------------------

A sanitized portfolio version can be structured as follows:

  marketing-analytics-automation-platform/
  |
  |-- README.txt
  |-- requirements.txt
  |
  |-- config/
  |   |-- oauth_client.example.json
  |   |-- oauth_client_property_b.example.json
  |   |-- token.example.json
  |   |-- token_property_b.example.json
  |
  |-- scripts/
  |   |-- export_ga4_two_properties.py
  |   |-- ga4_property_export.py
  |   |-- ga4_auth_property_b.py
  |   |-- ga4_extract_basic.py
  |   |-- export_mailchimp_reports.py
  |
  |-- exports/
  |   |-- ga4/
  |   |-- mailchimp/
  |
  |-- launchers/
  |   |-- run_ga4_export.bat
  |   |-- run_mailchimp_export.bat
  |   |-- run_ga4_export.sh
  |   |-- run_mailchimp_export.sh
  |
  |-- docs/
  |   |-- AS_IS_TO_BE_ANALYSIS.pdf
  |   |-- TECHNICAL_DOCUMENTATION_PYTHON.pdf
  |   |-- POWER_BI_USER_GUIDE.pdf
  |   |-- HANDOVER_DOCUMENTATION.pdf
  |   |-- ARCHITECTURE_V0_1.pdf
  |   |-- ARCHITECTURE_V1_0.pdf
  |
  |-- powerbi/
  |   |-- report_base.pbix
  |
  |-- logs/
  |
  |-- mailchimp_exports/
      |-- config.example.txt
      |-- export_state.example.json
      |-- campaigns_mailchimp_style/


--------------------------------------------------------------------------------
DATA SOURCES
--------------------------------------------------------------------------------

1. Google Analytics 4

  Used for website analytics.

  Extracted dimensions:

    - date
    - sessionSource
    - sessionMedium

  Extracted metrics:

    - sessions
    - engagedSessions
    - activeUsers
    - screenPageViews
    - averageSessionDuration
    - bounceRate

  Output:

    - One CSV per GA4 property
    - Date normalized from GA4 YYYYMMDD format to YYYY-MM-DD
    - Numeric metrics prepared for reporting layer

2. Mailchimp

  Used for newsletter and campaign analytics.

  Extracted information:

    - Campaign ID
    - Campaign title
    - Delivery date/time
    - Total recipients
    - Bounces
    - Open rate
    - Click rate
    - Click details by URL
    - Total clicks by URL
    - Unique clicks by URL

  Output:

    - One CSV-style report per campaign
    - Mailchimp-style folder organization
    - State file tracking already-exported campaigns


--------------------------------------------------------------------------------
GA4 EXPORT PROCESS
--------------------------------------------------------------------------------

The GA4 export process is implemented around a repeatable extraction pattern:

  Step 1   Resolve project paths

           BASE_DIR
           CONFIG_DIR
           EXPORTS_DIR
           LOGS_DIR

  Step 2   Load OAuth credentials

           If token exists:
             - Load token
             - Refresh token if expired

           If token does not exist:
             - Start local browser OAuth flow
             - Ask user to choose the correct Google account
             - Save token for future runs

  Step 3   Resolve reporting period

           Historical start:
             - 2018-01-01

           End date mode:
             - yesterday by default
             - today available as alternative

  Step 4   Split date range into chunks

           Default:
             - Monthly chunks

           Reason:
             - Avoid API timeouts
             - Reduce quota pressure
             - Improve retry/debugging experience

  Step 5   Execute GA4 RunReport requests

           For each configured GA4 property:
             For each month:
               - Build RunReportRequest
               - Use configured dimensions
               - Use configured metrics
               - Execute request
               - Paginate using offset when needed

  Step 6   Normalize output

           - Convert GA4 date format
           - Preserve stable column order
           - Merge all rows into one dataset per property

  Step 7   Write CSV output

           - Overwrite output file each run
           - Produce current full-history file
           - Log completion


--------------------------------------------------------------------------------
MAILCHIMP EXPORT PROCESS
--------------------------------------------------------------------------------

The Mailchimp process is implemented around campaign-level exports.

  Step 1   Resolve script-relative paths

           SCRIPT_DIR
           OUT_DIR
           REPORTS_DIR
           STATE_FILE
           CONFIG_PATH

  Step 2   Load configuration

           Expected config.txt keys:

             API_KEY=xxxxxxxxxxxxxxxxxxxx-usXX
             SERVER_PREFIX=usXX

           Optional:

             REFRESH_LAST_DAYS=7
             SLEEP_SECONDS=0.25

  Step 3   Fetch all campaigns

           Endpoint:

             /campaigns

           Pagination:

             count=100
             offset increments by 100

  Step 4   Determine whether campaign should be refreshed

           The script loads export_state.json and checks campaign IDs already
           exported in previous runs.

           Campaigns already exported and older than the refresh window are
           skipped.

           This avoids unnecessary repeated API calls while still refreshing
           recent campaigns whose reporting metrics may still change.

  Step 5   Fetch campaign report

           Endpoint:

             /reports/{campaign_id}

           Extracted sections include:
             - Recipients
             - Bounces
             - Opens
             - Clicks

  Step 6   Fetch click details

           Endpoint:

             /reports/{campaign_id}/click-details

           Pagination:

             count=1000
             offset increments by 1000

  Step 7   Write report file

           File naming:

             sanitized_campaign_title__campaign_id.csv

           The script sanitizes filenames by replacing invalid filesystem
           characters and compressing whitespace.

  Step 8   Save state

           export_state.json is updated after successful campaign export.


--------------------------------------------------------------------------------
TECHNICAL HIGHLIGHTS
--------------------------------------------------------------------------------

1. MULTI-PROPERTY GA4 CONFIGURATION

The main GA4 script uses a dataclass-based configuration model:

  PropertyExportConfig:
    - name
    - property_id
    - output_csv
    - oauth_client_json
    - token_json

This allows each property to have its own:

  - Business name
  - GA4 property ID
  - Output file
  - OAuth client file
  - Token file

This design was important because the organisation had multiple GA4 properties
that could be linked to different accounts or credentials.

The exported configuration included two properties in the working version:

  Property A:
    - Main website analytics
    - Own OAuth client
    - Own token file
    - Own CSV output

  Property B:
    - Secondary / local guide analytics
    - Own OAuth client
    - Own token file
    - Own CSV output

Why this matters:

  A single hardcoded GA4 script would have been faster to write, but harder to
  maintain. The dataclass approach makes the script extensible without
  changing the extraction engine.

Benefits:

  - Easier onboarding of new GA4 properties
  - Cleaner separation between logic and configuration
  - Lower risk of mixing credentials
  - Better long-term maintainability


--------------------------------------------------------------------------------
2. OAUTH TOKEN PERSISTENCE AND REFRESH

GA4 requires OAuth authentication.

The scripts implement the following authentication flow:

  If token file exists:
    - Load authorized user token
    - Check validity
    - Refresh automatically if expired and refresh token exists

  If token file does not exist or is invalid:
    - Start local OAuth browser flow
    - User authenticates with the correct Google account
    - Token is saved to disk for future executions

This is handled through:

  - google.oauth2.credentials.Credentials
  - google.auth.transport.requests.Request
  - google_auth_oauthlib.flow.InstalledAppFlow

Important implementation choice:

  Tokens are stored per property/account combination rather than forcing a
  single shared token for all properties.

Why this matters:

  In real organisations, different properties may be owned by different users,
  Google accounts, or permission scopes. Keeping token files isolated reduces
  confusion and makes debugging easier.

Operational benefit:

  Users authenticate once during setup. Future executions can run without
  repeated browser login, unless permissions change or reauthentication is
  forced.


--------------------------------------------------------------------------------
3. FORCE_REAUTH RECOVERY PATTERN

The multi-property GA4 script supports a recovery path through an environment
variable:

  FORCE_REAUTH=1

When enabled, the script can delete or ignore existing tokens and restart the
OAuth process.

This is useful when:

  - A user selected the wrong Google account
  - A token was created with insufficient permissions
  - GA4 access rights changed
  - PermissionDenied / 403 errors occur
  - The solution is installed on a new machine

The script also catches PermissionDenied and prints explicit recovery guidance:

  - Re-authenticate with the correct Google account
  - Delete the incorrect token file
  - Rerun with forced reauthentication if needed

This is a small but important production-readiness feature: it turns a common
API failure into an understandable operational fix.


--------------------------------------------------------------------------------
4. MONTHLY DATE CHUNKING

GA4 extraction can fail or become difficult to debug when a request covers a
large time range, especially with multiple dimensions.

The scripts therefore split the historical period into monthly chunks.

Example:

  2018-01-01 to 2018-01-31
  2018-02-01 to 2018-02-28
  2018-03-01 to 2018-03-31
  ...

instead of:

  2018-01-01 to yesterday

The default configuration uses:

  EARLIEST_DATE = 2018-01-01
  CHUNK_MONTHS = 1

Benefits:

  - Reduced timeout risk
  - More predictable API response sizes
  - Easier troubleshooting
  - Easier retry logic in future versions
  - Better fit for historical reporting refreshes

Trade-off:

  More API calls are required, but each call is safer and easier to inspect.

This is the right trade-off for a low-maturity organisation where reliability
and maintainability matter more than micro-optimizing execution time.


--------------------------------------------------------------------------------
5. OFFSET PAGINATION FOR GA4

The GA4 Data API can return many rows when combining:

  - date
  - sessionSource
  - sessionMedium
  - multiple metrics
  - a multi-year historical period

The scripts therefore implement offset-based pagination:

  PAGE_SIZE / PAGE_LIMIT = 100,000

Execution logic:

  offset = 0

  while True:
    - Run report request with limit and offset
    - Append returned rows
    - Increase offset by number of returned rows
    - Stop when fewer rows than the page size are returned

Why this matters:

  Without pagination, exports risk silently missing rows when response limits
  are reached.

This design is a key difference between a quick proof of concept and a more
reliable extraction utility.


--------------------------------------------------------------------------------
6. DATE NORMALIZATION FOR REPORTING

GA4 returns the date dimension as:

  YYYYMMDD

This is not ideal for reporting tools or non-technical users.

The scripts normalize the value to:

  YYYY-MM-DD

Example:

  20260131  ->  2026-01-31

Why this matters:

  - Power BI handles the normalized format more easily
  - CSV outputs become more readable
  - Manual inspection becomes easier
  - Date logic in Power Query / DAX becomes cleaner


--------------------------------------------------------------------------------
7. MAILCHIMP STATEFUL INCREMENTAL REFRESH

Mailchimp reporting metrics can continue to evolve after a campaign is sent,
especially opens and clicks.

At the same time, re-exporting every campaign on every run is unnecessary.

The Mailchimp script introduces a pragmatic state mechanism:

  STATE_FILE = export_state.json

This stores exported campaign IDs.

Default logic:

  REFRESH_LAST_DAYS = 7

Campaigns already exported and older than the refresh window are skipped.

Recent campaigns can be refreshed because their engagement metrics may still
change.

Benefits:

  - Fewer API calls
  - Faster execution
  - Less unnecessary file rewriting
  - Still captures late engagement activity

Trade-off:

  This is not a full database-style incremental load with change detection.
  It is a lightweight stateful export strategy appropriate for the project
  context.


--------------------------------------------------------------------------------
8. MAILCHIMP PAGINATION AND CLICK DETAIL EXTRACTION

The script does not only export campaign summary metrics. It also drills into
click details.

Campaign list pagination:

  Endpoint:
    /campaigns

  Parameters:
    count=100
    offset=0, 100, 200, ...

Click detail pagination:

  Endpoint:
    /reports/{campaign_id}/click-details

  Parameters:
    count=1000
    offset=0, 1000, 2000, ...

Click-detail output includes:

  - URL
  - Total clicks
  - Unique clicks

Why this matters:

  Newsletter performance is not only about open rate and click rate. URL-level
  click details help identify what content actually generated engagement.


--------------------------------------------------------------------------------
9. FILENAME SANITIZATION

Campaign titles can contain characters that are invalid in Windows or macOS
filenames:

  \ / : * ? " < > |

The Mailchimp script sanitizes filenames by replacing invalid characters with
underscores and normalizing whitespace.

File pattern:

  campaign_title__campaign_id.csv

Why this matters:

  - Prevents runtime errors when campaign titles contain unsafe characters
  - Makes files easier to browse
  - Keeps campaign ID in the filename for traceability
  - Avoids collisions when titles are similar


--------------------------------------------------------------------------------
10. SCRIPT-RELATIVE PATH DESIGN

The Mailchimp script detects its own location:

  SCRIPT_DIR = os.path.dirname(os.path.abspath(__file__))

and builds paths relative to the script.

This means the script does not depend on a hardcoded username or absolute
machine path.

Generated folders:

  mailchimp_exports/
  mailchimp_exports/campaigns_mailchimp_style/
  mailchimp_exports/export_state.json
  mailchimp_exports/config.txt

Benefits:

  - Easier deployment to another machine
  - Fewer path errors
  - Better fit for handover
  - Cleaner repository structure


--------------------------------------------------------------------------------
11. WINDOWS AND MACOS EXECUTION LAYER

The Python scripts are the cross-platform core.

Only the execution layer changes by operating system.

Windows:

  - .bat file
  - cd /d "%~dp0"
  - execute Python script
  - pause at end so user can read console output

macOS:

  - .sh file
  - cd "$(dirname "$0")"
  - optional virtual environment activation
  - execute Python script
  - can be scheduled through launchd

This design keeps business logic identical across environments.

Only the launcher changes.

Why this matters:

  The client environment was Mac-first, while development and testing could
  happen in a Windows environment. Separating execution from logic avoided
  duplicating or rewriting the solution.


--------------------------------------------------------------------------------
12. POWER BI REPORTING BASE

A Power BI report base was created to demonstrate how the extracted data could
be used for actual reporting.

The report was designed to answer questions such as:

  - How many people visit the websites?
  - Where do visitors come from?
  - Which newsletter campaigns perform best?
  - Are results improving or declining compared with the previous year?
  - How do performance indicators evolve by year, month, or subject?

The Power BI documentation emphasized safe usage for non-technical users:

  - Use existing measures
  - Do not modify raw data
  - Copy an existing page before experimenting
  - Use filters such as year, month, and subject
  - Treat Power BI as a visualization layer, not the source of truth

This is important because the project included user enablement, not only
technical delivery.


--------------------------------------------------------------------------------
13. POWER QUERY TRANSFORMATION LAYER

Power Query was positioned as the transformation and modelling layer for the
local reporting architecture.

Role of Power Query:

  - Connect to exported folders/files
  - Clean extracted data
  - Standardize column types
  - Prepare datasets for visuals
  - Support year/month filtering and comparisons

This created a bridge between Python extraction and Power BI reporting.

Python handled the source-system complexity.
Power Query handled report-specific shaping.


--------------------------------------------------------------------------------
14. DOCUMENTATION-FIRST DELIVERY

The project included several documentation layers:

  - AS-IS analysis
  - TO-BE analysis
  - Power BI user documentation
  - Python technical documentation
  - Handover documentation
  - Architecture diagrams
  - Execution instructions for Windows and macOS
  - Maintenance guidance
  - Troubleshooting guidance

This was a deliberate consulting choice.

For low-maturity analytics environments, the documentation is part of the
product. Without it, the client remains dependent on the consultant.


--------------------------------------------------------------------------------
DESIGN TRADE-OFFS
--------------------------------------------------------------------------------

1. CSV FILES INSTEAD OF DATABASE

Decision:

  Export structured CSV files instead of writing directly to a database.

Reason:

  - Lower cost
  - Lower infrastructure complexity
  - Easier adoption
  - Compatible with Power BI, Excel, Looker Studio, and Google Sheets
  - Better fit for the client's maturity level

Trade-off:

  CSV files are not ideal for enterprise-scale governance, concurrency,
  versioning, or access control.

Future improvement:

  Add a database or cloud storage layer once maturity and budget increase.


--------------------------------------------------------------------------------
2. LOCAL-FIRST INSTEAD OF CLOUD-FIRST

Decision:

  Build a local automation workflow with OS-level launchers.

Reason:

  - Minimal cost
  - No need for cloud platform setup
  - Easier handover
  - Works with the user's existing computer
  - Compatible with both Windows and macOS

Trade-off:

  Local execution depends on a machine being available and configured.

Future improvement:

  Move scheduled extraction to a cloud function, container, VM, or managed
  workflow orchestrator.


--------------------------------------------------------------------------------
3. FULL GA4 HISTORY OVERWRITE INSTEAD OF INCREMENTAL DATABASE LOAD

Decision:

  GA4 exports overwrite a full-history CSV.

Reason:

  - Simpler reporting consumption
  - Easier to explain to non-technical users
  - Avoids merge/upsert logic
  - Ensures output is always current

Trade-off:

  Full-history refresh is less efficient than an incremental warehouse load.

Future improvement:

  Introduce partitioned historical storage by month and only refresh recent
  periods.


--------------------------------------------------------------------------------
4. SEPARATE TOKENS PER PROPERTY INSTEAD OF SINGLE AUTH CONTEXT

Decision:

  Use separate OAuth client/token files for different GA4 properties.

Reason:

  - Easier management when properties are tied to different accounts
  - Better troubleshooting
  - Reduces risk of permission confusion

Trade-off:

  Slightly more setup complexity.

Future improvement:

  Add a credential registry or config-driven secrets manager.


--------------------------------------------------------------------------------
5. MAILCHIMP CAMPAIGN FILES INSTEAD OF SINGLE NORMALIZED TABLE

Decision:

  Export one report-style CSV per campaign.

Reason:

  - Closely mirrors how business users understand Mailchimp campaign reports
  - Easy manual inspection
  - Useful for handover and validation
  - Avoids overengineering the first version

Trade-off:

  Not ideal for analytical modelling compared with a normalized campaign fact
  table and click-detail table.

Future improvement:

  Add normalized outputs:

    mailchimp_campaigns.csv
    mailchimp_campaign_metrics.csv
    mailchimp_click_details.csv


--------------------------------------------------------------------------------
CONFIGURATION
--------------------------------------------------------------------------------

GA4 configuration points:

  - EARLIEST_DATE
  - END_DATE_MODE
  - DIMENSIONS
  - METRICS
  - PAGE_SIZE / PAGE_LIMIT
  - CHUNK_MONTHS
  - property_id
  - output_csv
  - oauth_client_json
  - token_json

Mailchimp configuration points:

  - API_KEY
  - SERVER_PREFIX
  - REFRESH_LAST_DAYS
  - SLEEP_SECONDS

Important governance note:

  Credentials and tokens must never be committed to a public repository.

Use example files instead:

  oauth_client.example.json
  token.example.json
  config.example.txt

The real versions should remain local, ignored by Git, and handled as secrets.


--------------------------------------------------------------------------------
SECURITY AND CONFIDENTIALITY
--------------------------------------------------------------------------------

The production implementation required sensitive files:

  - OAuth client JSON files
  - OAuth token JSON files
  - Mailchimp API key config
  - Client-specific property IDs
  - Client-specific export names
  - Potentially identifiable campaign data

These must not be published publicly.

Portfolio-safe approach:

  - Replace client names with generic labels
  - Replace property IDs with placeholders
  - Remove OAuth client secrets
  - Remove refresh tokens
  - Remove access tokens
  - Replace API keys with dummy values
  - Use synthetic sample outputs
  - Add .gitignore rules for config and token files

Recommended .gitignore:

  config/*.json
  config/token*.json
  mailchimp_exports/config.txt
  mailchimp_exports/export_state.json
  exports/
  logs/
  *.pbix
  .venv/
  __pycache__/


--------------------------------------------------------------------------------
REQUIREMENTS
--------------------------------------------------------------------------------

Python packages:

  pip install google-analytics-data
  pip install google-auth
  pip install google-auth-oauthlib
  pip install pandas
  pip install python-dateutil
  pip install requests

Optional requirements.txt:

  google-analytics-data
  google-auth
  google-auth-oauthlib
  pandas
  python-dateutil
  requests


--------------------------------------------------------------------------------
HOW TO RUN — GA4
--------------------------------------------------------------------------------

1. Create a virtual environment

  python -m venv .venv

2. Activate it

  Windows:
    .venv\Scripts\activate

  macOS:
    source .venv/bin/activate

3. Install dependencies

  pip install -r requirements.txt

4. Place OAuth client files in config/

  config/oauth_client.json
  config/oauth_client_property_b.json

5. Run the export

  Windows:
    launchers/run_ga4_export.bat

  macOS:
    ./launchers/run_ga4_export.sh

6. First run

  - Browser opens
  - User chooses correct Google account
  - Token is saved locally

7. Future runs

  - Token is reused
  - Token is refreshed when possible
  - CSV outputs are overwritten with refreshed data


--------------------------------------------------------------------------------
HOW TO RUN — MAILCHIMP
--------------------------------------------------------------------------------

1. Create Mailchimp config file

  mailchimp_exports/config.txt

2. Add configuration

  API_KEY=xxxxxxxxxxxxxxxxxxxx-usXX
  SERVER_PREFIX=usXX
  REFRESH_LAST_DAYS=7
  SLEEP_SECONDS=0.25

3. Run the export

  Windows:
    launchers/run_mailchimp_export.bat

  macOS:
    ./launchers/run_mailchimp_export.sh

4. Output

  mailchimp_exports/campaigns_mailchimp_style/

5. State tracking

  mailchimp_exports/export_state.json


--------------------------------------------------------------------------------
TROUBLESHOOTING
--------------------------------------------------------------------------------

GA4 PermissionDenied / 403

  Likely cause:
    The authenticated Google account does not have access to the GA4 property.

  Fix:
    - Delete the relevant token file
    - Re-run OAuth
    - Select the correct Google account
    - Use FORCE_REAUTH=1 if implemented in the launcher

Missing OAuth client file

  Likely cause:
    The config folder does not contain the required OAuth client JSON.

  Fix:
    - Download the OAuth client from Google Cloud Console
    - Place it in the expected config path
    - Ensure the filename matches the script configuration

Empty GA4 output

  Possible causes:
    - Wrong property ID
    - No data for selected period
    - Dimensions/metrics incompatible
    - Insufficient permissions

Mailchimp API error

  Possible causes:
    - Wrong API key
    - Wrong server prefix
    - Expired or revoked API key
    - Campaign report unavailable
    - Network timeout

Invalid filenames

  Handled by:
    - sanitize_filename()
    - Replacement of invalid filesystem characters

Encoding issues

  Mitigation:
    - CSV written with utf-8-sig where relevant
    - Console logging simplified for Windows compatibility


--------------------------------------------------------------------------------
POWER BI REPORTING LAYER
--------------------------------------------------------------------------------

The Power BI report base was designed as a practical consumption layer for the
exported data.

Functional areas:

  - Newsletter campaign performance
  - Main website performance
  - Secondary website / local guide performance
  - Traffic acquisition
  - Time-based analysis
  - Year-over-year comparison

User-facing concepts documented:

  - What the report is used for
  - Where the data comes from
  - How filters work
  - How to interpret charts and tables
  - How to compare with the previous year
  - How to create a new chart without breaking the report
  - What not to modify

Technical concepts documented:

  - Python extraction scripts
  - File organization
  - Power Query transformations
  - Duration handling for GA4
  - Data model structure
  - DAX measures
  - Best practices for future evolution


--------------------------------------------------------------------------------
AI READINESS
--------------------------------------------------------------------------------

This project was not an AI implementation, but it created the type of data
foundation required before AI can be useful.

AI assistants, natural language reporting tools, and LLM-based analytics agents
need structured and reliable data.

This project addressed several common blockers:

  Blocker                     Delivered foundation

  Data locked in platforms     API-based extraction
  Manual exports               Automated refresh workflow
  Inconsistent formats         Standardized CSV outputs
  No historical structure      Full-history GA4 export
  No refresh repeatability     Launchers and documented execution
  No cross-channel base        Common reporting layer
  No user autonomy             Handover and documentation

Future AI use cases enabled:

  - Ask natural language questions about campaign performance
  - Summarize monthly digital performance automatically
  - Detect unusual traffic or engagement patterns
  - Generate management commentary from KPI trends
  - Recommend campaigns or content themes based on historical engagement
  - Build a lightweight marketing analytics copilot
  - Connect structured exports to vector or semantic layers
  - Use LLMs to explain Power BI visuals to non-technical stakeholders

Important principle:

  AI does not solve messy data foundations.
  This project focused on making the data usable first.


--------------------------------------------------------------------------------
WHAT THIS DEMONSTRATES
--------------------------------------------------------------------------------

  - API integration in a real client context
  - OAuth implementation and token lifecycle management
  - GA4 Data API extraction
  - Mailchimp API extraction
  - Pagination handling
  - Monthly date chunking
  - Stateful export logic
  - CSV-based data product design
  - Configuration-driven architecture
  - Cross-platform execution design
  - Reporting-tool neutral thinking
  - Power BI / Power Query integration
  - Documentation for non-technical users
  - Technical handover for maintainability
  - Analytics architecture under budget constraints
  - Building an AI-ready data foundation before introducing AI

This is not simply a dashboard project.

It demonstrates the ability to identify the real bottleneck in a reporting
process, design the upstream data pipeline, build the automation layer,
document the operating model, and create a realistic path from manual
reporting toward scalable analytics.


--------------------------------------------------------------------------------
LESSONS LEARNED
--------------------------------------------------------------------------------

1. The most important reporting problem is often upstream.

   Dashboards are only as reliable as the extraction, transformation, and
   refresh process behind them.

2. Low-budget environments require architectural discipline.

   A small Python + CSV + Power BI architecture can create real value if it is
   structured properly.

3. User experience matters in automation.

   Non-technical users should not need to open source code. Launchers,
   documentation, and scheduling options are part of the solution.

4. OAuth is both technical and operational.

   The hardest part is not only writing the authentication code; it is making
   account selection, token storage, reauthentication, and permission errors
   understandable for the user.

5. CSV can be a valid first data layer.

   It is not the final architecture, but it can be the right intermediate step
   when maturity, budget, and tooling are limited.

6. AI readiness starts with boring foundations.

   APIs, clean exports, stable schemas, and documentation are what make future
   AI use cases realistic.


--------------------------------------------------------------------------------
FUTURE ROADMAP
--------------------------------------------------------------------------------

Near-term improvements:

  - Create normalized Mailchimp fact tables
  - Add consolidated GA4 + Mailchimp data dictionary
  - Add automated log files for every execution
  - Add validation checks after export
  - Add row-count comparison per run
  - Add error summary files for non-technical users
  - Add sample synthetic data for public GitHub version
  - Add unit tests for helper functions
  - Add CLI arguments for date ranges and force reauthentication

Medium-term improvements:

  - Add social media API extraction
  - Add event/action CSV standardization
  - Add automated scheduling
  - Add cloud storage layer
  - Add database layer
  - Add incremental partitioned storage
  - Add Power BI Service refresh strategy
  - Add Looker Studio / Google Sheets alternative architecture
  - Add Docker container for reproducible deployment

Long-term improvements:

  - Deploy to cloud function or containerized job
  - Add orchestration with cron, Airflow, Dagster, or Prefect
  - Add dbt-style transformation layer
  - Add semantic model / metric layer
  - Add anomaly detection
  - Add forecasting
  - Add automated management commentary
  - Add natural language analytics assistant


--------------------------------------------------------------------------------
PORTFOLIO POSITIONING
--------------------------------------------------------------------------------

This project can be positioned as:

  Marketing Analytics Automation Platform (API Based)


Suggested portfolio description:

  Designed and implemented a Python-based marketing analytics automation
  platform integrating Google Analytics 4 and Mailchimp APIs. The solution
  automated recurring extraction workflows, implemented OAuth authentication,
  supported multi-property GA4 processing, standardized data into reporting-
  ready CSV outputs, and enabled Power BI / Excel / Looker Studio reporting
  under low-budget, Mac-first client constraints.

Suggested CV bullet points:

  - Built a Python ETL automation platform integrating Google Analytics 4 and
    Mailchimp APIs for recurring marketing performance reporting.

  - Implemented OAuth-based GA4 authentication, token persistence, multi-
    property extraction, API pagination, monthly date chunking, and CSV export
    standardization.

  - Developed Mailchimp campaign reporting automation with API pagination,
    state tracking, filename sanitization, and campaign-level export logic.

  - Designed a reporting-tool neutral data foundation compatible with Power BI,
    Excel, Looker Studio, and future AI analytics use cases.

  - Produced AS-IS / TO-BE analysis, architecture diagrams, Power BI user
    guidance, and Python technical documentation to support autonomous client
    handover.


--------------------------------------------------------------------------------
CONTEXT AND CONFIDENTIALITY
--------------------------------------------------------------------------------

This project was delivered for a Brussels-based organisation active in economic
development, entrepreneurship, commerce, communication, and local project
promotion.

All client-identifying information has been anonymized in this portfolio
documentation.

The following have been excluded or replaced:

  - Real OAuth client secrets
  - Real access tokens
  - Real refresh tokens
  - Real Mailchimp API keys
  - Production data
  - Client-specific folder paths
  - Private campaign data
  - Internal stakeholder information

The architecture, implementation patterns, trade-offs, and technical decisions
are documented here as a portfolio demonstration.


--------------------------------------------------------------------------------
AUTHOR
--------------------------------------------------------------------------------

Mozart Mpia-Mu-Nzali
Senior Data & Analytics Consultant

Finance background combined with hands-on delivery in data analytics,
Power BI, Python automation, API integration, and AI-ready data foundations.

This project demonstrates the ability to go beyond dashboards and deliver an
end-to-end analytics automation solution: from AS-IS analysis and architecture
design to Python ETL development, reporting enablement, documentation, and
client handover.

================================================================================
