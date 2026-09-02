# Architecture and Data Flow

## Overview

The LinkedIn Agent Analytics Platform follows an end-to-end analytics workflow that moves from source data through data preparation, dimensional modeling, analytical calculations, and Power BI dashboard reporting.

## End-to-End Data Flow

Source Data
↓
Power Query Data Cleaning and Transformation
↓
Star Schema Data Model
↓
DAX Measures and KPI Calculations
↓
Power BI Dashboards
↓
Performance, Account Health, and Risk Insights

## Data Model

The Power BI model uses a star-schema structure consisting of:

- Fact Lead Activity
- DimLead
- DimAgent
- DimDate
## Data Preparation Layer

The source data was prepared using Power Query.

Key preparation activities included:

- Cleaning and standardizing source fields
- Transforming date and time fields
- Handling missing values
- Converting the Accepted field from Yes/No to numeric values
- Creating the required analytical tables
- Preparing the data for Power BI modeling

## Star Schema Relationships

The model consists of one central fact table supported by three dimension tables.

Fact Lead Activity is the central activity table.

DimLead provides lead-level descriptive attributes.

DimAgent provides agent-level information.

DimDate provides calendar attributes for time-based analysis.

The dimensions provide descriptive context for the activity records in the fact table.

## Analytical Layer

DAX measures are used to calculate the main performance indicators, including:

- Total Leads
- Total Invites Sent
- Total Accepted
- Accepted Rate
- Total Connected
- Total Replied
- Reply Rate
- Invite Utilization

These measures support consistent KPI reporting across the Power BI dashboard.
