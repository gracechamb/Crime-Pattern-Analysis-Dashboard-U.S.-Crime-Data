# U.S. Crime Analysis Dashboard | Tableau

An interactive Tableau workbook analyzing reported crime incidents across five U.S. cities, built to help a police department's research team understand **what** crimes occur, **when** they happen, **how** patterns change over time, and **which** incidents lead to arrests.

**[View the interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/grace.chamberlain/vizzes)**

![Dashboard preview](dashboard-screenshot.png)

## The Question
How can crime data be presented so that law enforcement can quickly spot patterns and decide where prevention and enforcement efforts would have the most impact?

## Data
- **Source:** Sample crime dataset provided through the Fullstack Academy Data Analytics Bootcamp
- **Scope:** 100 incident records (230 reported crimes) from January 2018 to December 2023
- **Cities:** Chicago, Houston, Los Angeles, New York, Phoenix
- **Fields:** city, area type (Downtown, Industrial, Residential, Suburb), crime type, date, time of day, severity, number of crimes, number of arrests

## Dashboards
1. **Crime Overview:** a map of the five cities (pie size = total crimes, slices = area type), most common crimes broken down by severity, and a live feed of recent incidents with a running total
2. **Time Period Analysis:** crimes by day of week, month, and time block (Morning, Afternoon, Evening, Night), plus which crime types lead each time block
3. **Trend Analysis:** yearly crime totals and a month-by-month comparison across years
4. **Comparative Analysis:** crimes with vs. without an arrest by crime type, and the share of severe incidents in each category, with Crime Type and Location filters
5. **Crime Analysis Guide:** an about page explaining how to read each dashboard and the key findings

## Key Findings
- **Assault is the most reported and most severe crime.** It accounts for 61 of 230 crimes (27%), and 39% of assaults were severe, the highest rate of any crime type.
- **Most crimes did not lead to an arrest.** All five crime types had more crimes without an arrest than with one. Theft had the lowest arrest rate (15 of 55, or 27%), while vandalism came closest to even (21 with an arrest vs. 22 without).
- **Night has the most crime (30%),** but the split across time blocks is fairly even. Assault leads at Night and in the Morning, vandalism in the Evening, and fraud in the Afternoon.
- **No clear weekly, seasonal, or yearly trend.** Saturday and May are the peaks, but spikes on other days and months, along with yearly totals that rose and fell (highest in 2021 at 48, lowest in 2019 and 2022 at 33), mean no consistent pattern holds.

## Data Quality Fixes
While reviewing the project, I found and corrected three issues that had affected the original results:

1. **Map showed cities in the wrong places.** The dataset's latitude and longitude didn't match the city names (for example, Houston records plotted in Utah). I mapped each city by name using Tableau's built-in geographic data instead, so all five cities now appear in the correct locations.
2. **Severe crime percentages were too low.** The original calculation counted rows instead of crimes, but divided by total crimes. Since many rows contain more than one crime, every percentage was understated. After correcting it, assault's severe rate rose from 13% to 39%, making it the most severe crime type, not burglary.
3. **Arrest counts went negative.** Subtracting arrests from crimes produced negative values because some crimes had more than one person arrested. I changed the logic to count whether each crime had an arrest, which removed the negatives and showed that every crime type had more crimes without an arrest, not just four of five.

## Files
- `Tableau_crime_analysis.twbx`: the packaged Tableau workbook (open with Tableau Desktop or Tableau Public)

## Tools
Tableau Desktop and Public · geographic mapping · calculated fields · time series analysis · interactive filters · dashboard design and data storytelling
