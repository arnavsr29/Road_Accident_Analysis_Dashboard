# Road_accident_analysis_dashboard

Intro:<br/>
This project is aimed at developing a Power BI Dashboard for generating insights about road accident data in the United Kingdom.<br/>

Dashboard_requirements:<br/>
Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth.<br/>
Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth.<br/>
Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year.<br/>
Monthly Trend showing comparison of Casualties for Current Year and Previous Year.<br/>
Casualties by Road Type for Current Year.<br/>
Current Year Casualties by Area/Location & Day/Night.<br/>
Total Casualties and Total Accident by Location.<br/>

DAX Formulas Used in Measures:<br/>
1. Total Casualties For Current Year and Year on Year Growth:<br/>
(a) Current Year To Date Casualties -- CY Casualties Measure<br/>
CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])<br/>
(b) Previous Year Casualties -- PY Casualties Measure<br/>
PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))<br/>
(c) Year on Year Growth of Casualties - YoY Casualties Measure<br/>
YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]<br/>
<br/>
2. Total Accidents for Current Year and Year on Year Growth:<br/>
(a) Current Year Accidents Count -- CY Accidents Count Measure<br/>
CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])<br/>
(b) Previous Year Accidents Count -- PY Accidents Count Measure<br/>
PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))<br/>
(c) Year on Year Growth of Accidents - YoY Accidents Measure<br/>
YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]<br/>
