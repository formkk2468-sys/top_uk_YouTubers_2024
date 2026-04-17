# YouTube2024-Marketing-Analytics-Project

# Table of Contents

- [Project Overview](#Project-Overview)
- [Objective](#objective)
- [Key Metrics & Scope](#Key-Metrics-&-Scope)
- [Data Source](#Data-Source)
- [Steps of Project](#Steps-of-Project)
  



# Project Overview

This project aims to help the marketing team make effective decisions in selecting the Top UK YouTubers in 2024 for campaign collaborations as efficiently as possible.

It addresses the issue of scattered and inconsistent data through a systematic workflow, starting from collecting data from Kaggle, organizing and validating it using SQL, and presenting the results through a Power BI dashboard to analyze ROI and investment efficiency.

# Objective

To discover the top performing UK Youtubers to form marketing collaborations with throughout the year 2024.

# KPIs & Scope

This project focuses on analyzing the Top 100 YouTubers in the UK, using the following KPIs :

- subscriber count
- total views
- total videos, and
- engagement metrics

# Data Source 

Key data used in the analysis to achieve the project objectives.

- channel names
- total subscribers
- total views
- total videos uploaded

# Steps of Project

- Design
- Developement
- Testing
- Analysis

# Design 

## Dashboard Components Required 

1. Who are the top 10 YouTubers with the most subscribers?
2. Which 3 channels have uploaded the most videos?
3. Which 3 channels have the most views?
4. Which 3 channels have the highest average views per video?
5. Which 3 channels have the highest views per subscriber ratio?
6. Which 3 channels have the highest subscriber engagement rate per video uploaded?

## Dashboard mockup

## Tools

| Tool | Purpose |
| --- | --- |
| Excel | Exploring the data |
| SQL Server | Cleaning, testing, and analyzing the data |
| Power BI | Visualizing the data via interactive dashboards |

# Developement

## Project Workflow

1. Get the data
2. Explore the data in Excel
3. Load the data into SQL Server
4. Clean the data with SQL
5. Test the data with SQL
6. Visualize the data in Power BI
7. Generate the findings based on the insights

## Data Cleaning

Problem Identified : The NOMBRE column contains both the channel name and the handle (ID) concatenated together, separated by the "@" symbol. To ensure analytical accuracy, it is necessary to extract only the channel name.

![Problem_Identified](assets/images/Problem_Identified.png)

### Transform the data

```sql

SELECT
    CAST(SUBSTRING(NOMBRE, 1, CHARINDEX('@', NOMBRE) - 1) AS VARCHAR(100)) AS channel_name,
    total_subscribers,
    total_videos,
    total_views
FROM 
    top_uk_youtubers_2024

```

### Create the SQL view

```sql

CREATE VIEW view_uk_youtubers_2024 AS

SELECT
    CAST(SUBSTRING(NOMBRE, 1, CHARINDEX('@', NOMBRE) - 1) AS VARCHAR(100)) AS channel_name,
    total_subscribers,
    total_videos,
    total_views
FROM 
    top_uk_youtubers_2024

```

