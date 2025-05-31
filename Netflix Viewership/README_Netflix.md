# Netflix Viewership Analysis: Recommending the Next Hit

## Overview
This project analyzes trends in Netflix’s most-watched and highest-rated content in the United States to determine what characteristics drive engagement. With Netflix’s share of U.S. streaming viewership declining from 8.4% to 7.5% (as of October 2024), this analysis aims to support strategic content creation that can increase viewership, ad revenue, subscriptions, and ultimately shareholder value. The findings are intended for Netflix’s C-suite decision-makers.

## Table of Contents
- [Requirements](#requirements)
- [Business Problem](#business-problem)
- [Data Sources](#data-sources)
- [Feature Selection](#feature-selection)
- [Findings](#findings)
- [Recommendations](#recommendations)
- [Ethical Considerations](#ethical-considerations)
- [Future Work](#future-work)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Requirements
This project was built and visualized using:
- pandas  
- numpy  
- seaborn  
- matplotlib  
- PowerPoint (for executive presentation)

## Business Problem
Netflix's market share in U.S. streaming has been stagnant, with a noted decline in recent months. To combat this, Netflix must understand which types of content drive the most consistent viewership and engagement. The goal is to reverse the market share decline by identifying attributes of successful content and applying those insights to content development and release strategies.

## Data Sources
- Netflix U.S. viewership data from 7/4/2021 to 3/31/2024
- Metrics included weekly viewing hours, top-10 appearances, TV parental ratings, category, and season information
- Nielsen’s The Gauge (2024) data on streaming trends

## Feature Selection
Key attributes analyzed:
- **Category** (e.g., English TV, Non-English, Movies)
- **Runtime**
- **Subsequent Seasons** (first vs. follow-up seasons)
- **TV Rating** (e.g., TV-14, TV-MA)

## Findings

- **English TV Shows** outperform other categories in average weekly viewership and top-10 frequency.
- **TV Ratings of TV-14 and TV-MA** are most common among long-lasting hits like *Stranger Things* and *Cocomelon*.
- **Runtime** has minimal impact on viewership.
- **Subsequent Seasons** do not consistently perform better than original seasons (e.g., *Bridgerton Season 2* underperformed Season 1).
- Hits like *Wednesday* achieved early success potentially due to strong marketing and cultural relevance.

## Recommendations
To increase U.S. viewership:
- Focus on **English-language TV shows**.
- Target a **TV rating between TV-14 and TV-MA**.
- Invest in pilot seasons over assuming follow-up season success.
- Further analyze content strategy around shows like *Wednesday* and *Stranger Things* to identify additional creative factors.

## Ethical Considerations
- Prioritizing English-language content may sideline global voices. To mitigate this:
  - Ensure diverse casts and offer multilingual accessibility.
- Content aimed purely at engagement must still align with Netflix's brand values around inclusivity, accessibility, and cultural responsibility.

## Future Work
- Conduct viewer sentiment analysis and survey feedback on top content.
- Analyze content success patterns from competitors (e.g., Prime Video, Hulu, Disney+).
- Create predictive models for show performance based on early viewer data.
- Develop a content planning dashboard for Netflix executives.

## License
This project is intended for educational purposes under fair use and is not affiliated with or endorsed by Netflix.

## Acknowledgements
- Nielsen’s The Gauge (2024)
- Netflix public and proprietary data
