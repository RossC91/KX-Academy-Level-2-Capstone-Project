# KX-Academy-Level-2-Capstone-Project

 This file was made using AI.
 
This is a KDB+/Q trading analysis project for analyzing options trading data. Here's what each section does:
1. Data Loading

Loads a trading database into the current process
Connects to a reference data service (port 5457) to fetch option and instrument reference data
Imports a CSV file containing exchange messages
Creates tables for trades, options reference data (optRef), and instrument reference data (instRef)

2. Data Cleaning

Converts the expiry dates in the options reference table to proper date format
Extracts broker IDs from exchange messages (handles different exchange formats like CME and ISE)
Adds broker IDs as a new column to the messages table
Converts trade and exchange message IDs to string format

3. Data Analytics and Reporting

Creates tradeContext by joining trade data with NBBO (National Best Bid and Offer) data
Implements a classifyTrades function that identifies trades with poor execution quality by checking if:

Buy trades were executed above the ask price
Sell trades were executed below the bid price


Exports bad trades (poor execution quality) to a CSV file

4. Profitability Analysis

Aggregates trading edge, quantity, and number of trades into 15-minute intervals
Creates a returnN function to retrieve top/bottom N records based on any column
Finds the top 5 time periods by edge and bottom 5 by quantity
Calculates correlation between edge, quantity, and number of trades

5. Profiling and Outlier Analysis

Creates profiles for each option showing trade counts, average edge, and quantity ranges
Generates a special profile (edgeProfile) focusing only on trades with above-average edge for each option
Joins this profile with reference data to create a comprehensive view (edgeProfileFull)

Purpose: This is a capstone project analyzing trading execution quality, profitability, and identifying patterns in options trading data.
