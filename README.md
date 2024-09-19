# Road_accident_analysis_dashboard

<img width="484" alt="Final Dashboard Image" src="https://github.com/user-attachments/assets/05ae001d-8b98-4bf7-9b75-905beb6e0637">


Intro:<br/>
<br/>
Project Overview
This project, undertaken during my internship at SkillCraft Technology, focuses on developing a comprehensive Power BI Dashboard to generate insights on road accident data in the United Kingdom. The dashboard helps identify critical patterns in casualties and accidents to support data-driven decision-making for improving road safety measures.
<br/>
Dashboard Requirements:
The dashboard was designed to include the following key performance indicators (KPIs) and metrics:
<br/>
Primary KPI's:
Total Casualties and Total Accidents for the Current Year (CY) and Year-over-Year (YoY) Growth.<br/>
Total Casualties by Accident Severity (fatal, serious, slight) for the Current Year and YoY Growth.<br/>
<br/>
Secondary KPI's:
Total Casualties by Vehicle Type for the Current Year.<br/>
Monthly trends comparing casualties for the Current Year and Previous Year (PY).<br/>
Casualties by Road Type for the Current Year.<br/>
Current Year Casualties by Area (Urban/Rural) and Light Conditions (Day/Night).<br/>
Total Casualties and Accidents by Location (mapped).<br/>
<br/>
Key Findings<br/>
Total Casualties: 195.7K (↓11.9% YoY).<br/>
Total Accidents: 144.4K (↓11.7% YoY).<br/>
Fatal Casualties: 2.9K (↓33.3% YoY).<br/>
Serious Casualties: 27.0K (↓16.2% YoY).<br/>
Slight Casualties: 165.8K (↓10.6% YoY).<br/>
<br/>
Casualties by Vehicle Type:<br/>
Car: 155,804 (highest number of casualties).<br/>
Van: 15,905.<br/>
Bike: 15,610.<br/>
Bus: 6,573.<br/>
Agricultural Vehicles: 399.<br/>
<br/>
Casualties by Road Type:<br/>
Single carriage roads: 145K casualties.<br/>
Dual carriageway: 32K casualties.<br/>
Roundabout: 13K casualties.<br/>
<br/>
Urban vs. Rural Casualties:<br/>
Urban: 61.95% of total casualties.<br/>
Rural: 38.05% of total casualties.<br/>
<br/>
Day vs. Night Casualties:<br/>
Daylight: 73.8% of total accidents.<br/>
Dark conditions: 26.1% of total accidents.<br/>
Casualties by Location:
Mapped data: High-density accident zones in various parts of the UK.<br/>
<br/>
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
<br/>
Conclusion:
This project provided valuable insights into the road accident trends across the UK, which can aid in implementing targeted safety measures. The dashboard effectively visualizes crucial statistics on accident severity, vehicle types, road conditions, and location-based analysis, making it a vital tool for strategic planning.
