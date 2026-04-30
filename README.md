# Central Bank Communication in Times of Crisis: Linguistic Complexity Analysis
This repository contains a fully reproducible pipeline for analyzing monetary policy statements from multiple central banks. Using natural language processing tools, the project examines how linguistic complexity — including readability, abstractness, informativeness, and disunity — evolves across economic conditions, with particular attention to crisis periods. Specifically, complexity tends to rise during periods of low growth or monetary stimulus, and communication aimed at households and firms accounts for a substantial share of this variation. The dataset spans from 2000-2025, across 18 different countries.

# Repository Structure
## 00_DataConstruction.ipynb
-Imports monetary policy statements (press releases) from multiple central banks (raw text files omitted; CBRaw.csv is provided instead)

-Adds policy rate decisions and saves as CB.csv

-Computes linguistic complexity and additional textual characteristics. Saves extended dataset as CB2.csv

## 01_CleaningAndDescriptive.ipynb
-Imports CB2.csv

-Checks recession indicators across different types

-Merges topic proportions from Notebook 03

-Adds additional textual characteristics

-Converts data to monthly frequency and merges macroeconomic variables. Produces: CBQuarterly.csv (quarterly version) and CBMonthly.csv (monthly version)

-Generates descriptive statistics: correlation tables; complexity trends; macroeconomic variable trends; topic proportion graphs

## 02_ImportMissing.ipynb
-Fills missing macroeconomic variables not available on FRED

-Data sourced directly from central bank websites (with translation where necessary)

-Updates CBMonthly.csv and CBQuarterly.csv

## 03_Topics.ipynb
-Performs topic modelling using LDA

-Computes topic proportions

-Saves combined dataset as CBTopic.csv

## 04_MainRegressions.ipynb
-Imports CBMonthly.csv and CBQuarterly.csv (main specifications use quarterly data)

-Constructs: quantile macro variables; principal components; descriptive tables and graphs; Runs main regression specifications

-Includes exploratory work on document‑distance measures (not included in the research report due to methodological limitations)

## 05_FindingExamples.ipynb
-Short script to extract illustrative examples for presentations and appendices (e.g., high‑complexity vs low‑complexity statements)

## References for Data Sources
-Monetary Policy Statements (Primary Text Corpus): Multiple Central Banks. (Various years). Monetary Policy Statements and Press Releases. Retrieved directly from official central bank websites

-Policy Rate Decisions: Bank for International Settlements (BIS). (n.d.). Policy Rate Series. Retrieved from the BIS Statistics Explorer

-Real GDP: Federal Reserve Bank of St. Louis. (n.d.). FRED: Federal Reserve Economic Data. Real GDP series for relevant countries

-Recession Indicators, 2 sources: National Bureau of Economic Research (NBER). (n.d.). US Business Cycle Dating. Retrieved from https://www.nber.org/research/data/us-business-cycle-dating and Organisation for Economic Co‑operation and Development (OECD). (n.d.). Composite Leading Indicators / Recession Indicators. Retrieved from https://data.oecd.org/  

-Consumer Price Index (CPI): Bank for International Settlements (BIS). (n.d.). CPI and Price Level Statistics. Retrieved from the BIS Statistics Explorer.

-Unemployment Rate: Organisation for Economic Co‑operation and Development (OECD). (n.d.). Unemployment Rate (Monthly). Retrieved from https://data.oecd.org/unemp/unemployment-rate.htm

-Additional Macroeconomic Variables (Country‑Specific). For variables missing from FRED, OECD, or BIS: Multiple Central Banks. (Various years). Macroeconomic Indicators and Statistical Releases. Retrieved directly from official central bank websites
