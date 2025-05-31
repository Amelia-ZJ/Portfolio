# Nike Sentiment
  

## Overview
Exploring customer sentiment about Nike through discussions on Reddit (2022 to 2025). This analysis seeks to understand the root of customer perception issues through Reddit comments using sentiment analysis and topic modeling. Results will help inform Nike’s product strategy, branding, and investor relations by identifying key pain points and areas of customer enthusiasm.

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
- Python & Libraries: pandas, nltk, seaborn, matplotlib, BERTopic, scikit-learn, & praw.

## Dataset
Source: Reddit API (https://www.reddit.com/prefs/apps)

Scope:
- Reddit posts and comments from January 2022 to March 2025 containing the keyword "Nike"
- 116 Reddit posts, yielding 18,000+ comments after expansion
- Final filtered dataset includes 11,319 comments with measurable sentiment

Key Features:
- Text fields: post title, comment body, upvotes, timestamp
- Sentiment scores from VADER (compound score)
- Topic clusters from BERTopic for both positive and negative comments

## Steps
- Data Collection: Retrieved Reddit posts using PRAW (Reddit API wrapper) and stored to CSV
- Cleaning: Removed off-topic, null, or non-text comments; converted nested comment lists to rows
- Sentiment Analysis: Used VADER (via NLTK) to generate polarity scores
- Topic Modeling: Applied BERTopic separately on positive and negative comments
- Visualization: Plotted sentiment trends over time and distribution histograms; identified key discussion peaks (e.g., Kyrie Irving fallout, viral AI ad)

## Features
Visualizations:
- Sentiment score distributions by month
- Top 10 negative and positive comment spikes by event
- BERTopic clusters with keywords per topic

Design:
- Color-coded plots and histograms
- Visual differentiation between neutral, positive, and negative sentiments
- Code structured for reusability and clarity

Audience Focus:
- Tailored for Nike’s C-Suite to inform innovation, marketing, and brand strategy based on authentic user voice


## Results

Findings:
| Metric                 | Pre-CLEAR | Post-CLEAR | Notes                                                                        |
|------------------------|-----------|------------|------------------------------------------------------------------------------|
| Total Posts Analyzed   | Moderate  | High       | 116 Reddit posts with ~18K comments                                          | 
| Avg. Comments per Post |  57.74M   | 57.74M     | 152.2                                                                        |
| Most Negative Month    | Low       | Low        | November 2022 (Nike ends relationship with Kyrie Irving)                     |
| Most Positive Month    | Low       | Low        | December 2023 (Viral AI-generated Nike ad praised)                           |
| Top Negative Topics    | Low       | Low        | Sponsorship backlash, quality complaints (e.g., hoodie stitching errors)     |
| Top Positive Topics    | Low       | Low        | Hauls, kits, nostalgic appreciation for older models, AI branding excitement |

Key Takeaways:
- Sponsorships Drive Sentiment: Nike’s lowest sentiment spike in November 2022 was triggered by the termination of its relationship with Kyrie Irving. This highlights that endorsements and athlete partnerships are not just marketing tools—they significantly impact customer trust and loyalty.
- Quality Control Matters: A sewing error on a $100 sweatshirt was a top complaint, emphasizing that customers expect flawless quality, especially on premium products. High price points demand higher scrutiny.
- Creative Advertising Drives Engagement: Nike’s highest sentiment occurred in December 2023 after a viral AI-generated advertisement, proving that innovative digital engagement resonates strongly with the online community.
- Brand Comparisons Are Insightful: Reddit users consistently compared Nike to Reebok (more than Adidas), suggesting that Reebok may be Nike’s perceived rival among this user base. This insight can shape competitive benchmarking and messaging.
- Fit & Function Over Fashion in Performance Segments: Negative comments flagged a perception that Nike shoes are increasingly fashion-focused and less performance-oriented—especially among runners. This signals a need to realign product strategy in technical segments.
- Product Lines Like Kits Need Refinement: Adidas was frequently favored over Nike in discussions about sports kits, especially around quality. Nike should reevaluate its kit partnerships and production standards.

## Challenges
- Informal Reddit language (slang, sarcasm, emojis) complicated sentiment scoring
- Distinguishing Nike-specific sentiment from mentions of Adidas, Reebok, etc.
- Temporal sentiment spikes caused by external events required context to interpret

## Limitations
- No demographic data available for Reddit users
- Reddit’s U.S.-centric, younger demographic may not reflect global sentiment
- VADER’s rule-based approach may misclassify nuanced emotions or sarcasm

## Future Work
- Expand analysis to include Twitter, Instagram, or TikTok data for demographic comparison
- Integrate a neural sentiment classifier (e.g., RoBERTa) for improved nuance detection
- Conduct brand comparison modeling (Nike vs. Adidas/Reebok) directly in topic clusters
- Track impact of sentiment-informed decisions (e.g., campaign tweaks, product launches)

## Acknowledgements
- Reddit API & Developer Community
- NLTK and BERTopic Documentation
- Inspiration from "Shoe Dog: A Memoir by the Creator of Nike" by Phil Knight & Nike’s commitment to performance and innovation
