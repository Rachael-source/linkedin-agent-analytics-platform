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
