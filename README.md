This project analyzes import trade data for household steel products (e.g., lunch boxes, containers, scrubbers) from January 2017 to October 2025. It derives insights into trade patterns, HSN code contributions, product categories, per-unit economics, duty structures, and supplier trends using Excel.

Table of Contents
Overview
Data Source
Project Structure
Technical Requirements
Analysis Performed
Formulas Used
Usage
Evaluation Criteria
Overview
The goal is to process raw import data, clean and parse it, and create summary sheets and visualizations to support business intelligence decisions. The analysis covers macro trends, cost breakdowns, and supply chain dynamics.

Data Source
The primary data source is the sample data 2.xlsx file provided with the assignment, containing raw trade records in the Sheet1 sheet.

Project Structure
The Excel workbook contains the following sheets:

Raw Data: An exact copy of the data from sample data 2.xlsx.
Cleaned Data: The raw data with additional calculated columns for year, grand total, parsed model/quantity/unit price from the description, HSN description, category, per-unit cost, duty percentage, etc.
Lookup Tables: Static reference tables for HSN codes, descriptions, categories, and potentially sub-category keywords.
Year Summary: Aggregated data by year (Total Value, Duty, Grand Total, YoY Growth).
HSN Summary: Aggregated data by HSN code (Total Value, Duty, Grand Total, % Contribution, Top 25).
Model Summary: Aggregated data by product model (quantity, value, average unit price).
Charts: Visualizations (line charts, pie charts, bar charts) based on summaries.
Notes: Explanations of formulas used, assumptions made during parsing, and key findings.
Technical Requirements
Software: Microsoft Excel (2016 or later recommended).
Skills: Proficiency in Excel formulas (e.g., YEAR, SUMIFS, VLOOKUP, MID, FIND, SEARCH, IF, ISERROR), PivotTables, and charting.
Analysis Performed
Data Cleaning & Parsing: Extracted model name, quantity, and unit price from the GOODS DESCRIPTION field.
HSN Code Mapping: Mapped HSN codes to their standard descriptions and categories using lookup tables.
Category Creation: Classified products into Main and Sub-categories based on HSN and description.
Grand Total Calculation: Calculated Grand Total_INR = TOTAL VALUE_INR + DUTY PAID_INR.
Year-wise Summary: Summarized trade value, duty, and calculated YoY growth by year.
HSN-wise Summary: Summarized trade value and duty by HSN code, calculated % contribution, identified top 25 codes.
Detailed Computations:
Per-unit cost analysis (with and without duty).
Duty % calculation and flagging of exceptional duty structures.
Year-wise model-wise quantity and value analysis.
Supplier trend analysis (based on IEC code).
Formulas Used
Key formulas are documented in the Notes sheet and used in the Cleaned Data and summary sheets. Examples include:

Year Extraction: =YEAR(B2)
Grand Total: =Q2+T2
Text Parsing (Quantity): =IF(ISERROR(SEARCH("QTY:", G2)), RawData!N2, TRIM(MID(G2, SEARCH("QTY:", G2)+4, SEARCH(" ", G2, SEARCH("QTY:", G2)+4) - SEARCH("QTY:", G2) - 4)))
HSN Lookup: =VLOOKUP(E2, 'Lookup Tables'!$A$2:$B$100, 2, FALSE)


Use of Excel features (PivotTables, formulas, charts).
Clarity and organization of the workbook.
