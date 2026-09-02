# Analytics Summary

## Overview

This analysis evaluates LinkedIn agent outreach performance using the prepared lead activity dataset and Power BI data model.

## Key Performance Areas

The analysis focuses on:

- Total leads
- Total invites sent
- Total accepted
- Acceptance rate
- Total connected
- Total replied
- Reply rate
- Invite utilization
- Ghosting status
- Account health
- Risk and anomaly indicators

## Analytical Approach

The source data was cleaned and transformed using Power Query before being modeled in Power BI.

The analysis uses a star-schema structure consisting of:

- Fact Lead Activity
- DimLead
- DimAgent
- DimDate

DAX measures were created to calculate the core performance indicators.

## Risk Intelligence

The dashboard supports identification of potential risk signals, including:

- Low invitation acceptance
- Low reply activity
- Ghosting behavior
- Differences in agent performance
- Outreach activity relative to configured account limits

## Key Data Limitations

The dataset has a limited observation period, so long-term reply-rate decay cannot be reliably established.

The available time-series depth is insufficient for statistically meaningful trend or decay analysis.

Campaign identifiers, campaign costs, and revenue fields are not available, so true Campaign ROI cannot be calculated.

The Source field contains only one observed value, `Build Search`, preventing meaningful source/campaign comparison.

## Purpose

The analysis provides a practical view of LinkedIn outreach performance and supports account-health monitoring, risk identification, and data-driven decision-making.
