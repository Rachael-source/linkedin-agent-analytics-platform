# Database Schema

## Overview

The LinkedIn Agent Analytics Platform uses a star-schema data model designed to support agent performance, lead activity, outreach, engagement, and risk analysis.

## Fact Table

### Fact Lead Activity

**Grain:** One record represents the activity/status information associated with a lead.

Key fields include:

- Lead ID
- Agent ID
- Added On
- Last Contacted Date/Time
- Invite Sent At Date/Time
- Connected At
- Accepted
- SDR Status
- Comment
- Status
- Hot
- Cold
- Source
- Prioritize

## Dimension Tables

### DimLead

Contains descriptive information about each lead.

Fields:

- Lead ID
- Name
- Job Title
- Company
- Industry
- Location
- Source
- Prioritize
- LinkedIn
- URL

### DimAgent

Contains agent information.

Fields:

- Agent ID
- Agent Name

### DimDate

Provides date attributes for time-based analysis.

Fields:

- Date ID
- Date
- Year
- Month
- Month Name
- Day

## Relationships

The model follows a star-schema structure:

- DimLead → Fact Lead Activity
- DimAgent → Fact Lead Activity
- DimDate → Fact Lead Activity

Dimension tables provide descriptive context, while Fact Lead Activity contains the measurable activity data.

## Data Transformation

The source data was cleaned and transformed in Power Query before loading into the Power BI data model.

The `Accepted` field was converted from Yes/No values to numeric values:

- Yes = 1
- No = 0

This allows acceptance metrics and rates to be calculated consistently in Power BI.

## Key Measures

Examples of analytical measures include:

- Total Leads
- Total Invites Sent
- Total Accepted
- Accepted Rate
- Total Connected
- Total Replied
- Reply Rate
- Invite Utilization

## Data Model Purpose

The schema supports:

- Agent performance analysis
- Lead activity monitoring
- Invitation and acceptance analysis
- Reply and engagement analysis
- Account health monitoring
- Risk and anomaly analysis
- Power BI dashboard reporting

## Known Data Limitations

- The source dataset contains a limited observation period.
- The available time series is insufficient for statistically meaningful long-term trend or reply-decay analysis.
- Campaign identifiers, campaign costs, and revenue fields are not available; therefore, true Campaign ROI cannot be calculated.
- The Source field contains only one observed value, `Build Search`, preventing meaningful source/campaign comparison.
