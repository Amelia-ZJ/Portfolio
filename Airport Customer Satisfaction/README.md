# Airport Customer Satisfaction
  

## Overview
Examines the surge in U.S. airport complaints since 2020, focusing on Orlando International Airport (MCO), where CLEAR’s Expedited Passenger Screening Program has driven dissatisfaction, unlike at airports like Dallas Love Field. Using Department of Transportation data, it proposes to MCO Board Members via PowerPoint that decommissioning CLEAR could cut complaints, boost morale, and raise profits, despite some unfiled complaint data gaps.

## Table of Contents
- [Requirements](#Requirements)
- [Dataset](#Dataset)
- [Steps](#Steps)
- [Features](#Features)
- [Results](#Results)
- [Challenges](#Challenges)
- [Limitations](#Limitations)
- [Future Work](#future-work)
- [Acknowledgements](#Acknowledgements)

## Requirements
- Tableau or python for data manipulation, idenifing patterns, and visualizations.


## Dataset
Source: U.S. Department of Transportation (DOT) complaint datasets, available at transtats.bts.gov.

Additional Data: Passenger counts from DOT, IATA/ICAO codes, and community feedback from platforms like Reddit.

Scope: Complaints data from 2015–2023 across U.S. airports, with a focus on MCO and Florida airports.

Key Features
- Complaint Categories: Expedited Passenger Screening Program, TSA PreCheck, CLEAR, etc.
- Temporal Data: Monthly complaint trends at MCO.
- Comparative Data: Passenger volumes and complaint rates at MCO vs. Miami International Airport (MIA) and Dallas Love Field (DAL).

Processing: Data was filtered to exclude categories with fewer than 10 complaints for clarity in visualization.

## Steps
- Data Collection: Downloaded DOT complaint datasets and passenger statistics.
- Data Cleaning: Filtered and organized data by airport, category, and time.
- Analysis: Identified complaint trends, focusing on Expedited Passenger Screening Program post-CLEAR implementation.
- Visualization: Created 6 PowerPoint slides with charts (e.g., bar graphs, time series) to illustrate trends and comparisons.
- Proposal Development: Formulated the recommendation to decommission CLEAR based on data insights.
- Presentation Design: Built a PowerPoint using Gestalt principles and MCO branding for clarity and impact.

## Features
Visualizations:
- Complaint counts by state and airport.
- MCO complaint trends over time.
- Expedited Passenger Screening Program sub-category breakdown.
- CLEAR implementation impact analysis.

Design: Aligned text and visuals, consistent spacing, and color coding (red for high complaints, green for low).
Audience Focus: Tailored to MCO Board Members with emphasis on customer satisfaction and profitability.

## Results
Key Findings:
- Florida ranks among the top states for airport complaints, with MCO leading in most categories.
- Complaints spiked after CLEAR’s implementation at MCO, unlike airports like DAL, which never adopted CLEAR.
- Expedited Passenger Screening Program accounts for 94.47% of MCO screening complaints (5,925 total).

Impact of CLEAR:
- Sharp increase in complaints post-launch, with community feedback highlighting longer lines and minimal time savings (~2 minutes).

Proposed Outcome:
- Decommissioning CLEAR could reduce complaints, boost staff morale, lower turnover, and increase profitability.

| Metric                 | Pre-CLEAR | Post-CLEAR | Notes                                            |
|------------------------|-----------|------------|--------------------------------------------------|
| Expedited Complaints   | Moderate  | High       | Significant spike after CLEAR launch             | 
| Passenger Volume (2023)|  57.74M   | 57.74M     | Comparable to MIA (52.34M) with fewer complaints |
| Complaint Rate (DAL)   | Low       | Low        | No CLEAR implementation                          |

Sample Prediction:
- Test URL classified as "Phishing" with 100% probability, validating real-world applicability.

## Challenges
- Missing verbal complaints not filed online, potentially underrepresenting total dissatisfaction.
- Limited granularity in sub-category complaint data.
- Community feedback (e.g., Reddit) is anecdotal and not systematically quantified.

## Limitations
- Dataset lacks unfiled complaints, skewing the full scope of customer frustration.
- Focus on CLEAR may overlook other contributing factors (e.g., staffing issues).
- Proposal assumes immediate complaint reduction post-decommissioning, which requires validation.

## Future Work
- Validation: Monitor complaint trends post-CLEAR decommissioning to confirm effectiveness.
- Broader Analysis: Include verbal complaint data or surveys for a comprehensive view.
- Comparative Study: Expand to other airports with CLEAR to strengthen the hypothesis.
- Policy Impact: Track California’s potential ban on third-party checks for regulatory context.

## Acknowledgements
- Data Source: U.S. Department of Transportation, Bureau of Transportation Statistics.
- References: Tampa Bay Business Journal, TSA press releases.