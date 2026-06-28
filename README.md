# The Declining Birth Rate in the United States: Systemic Forces or Personal Choice?

**Hugo Mosso** · University of Massachusetts Dartmouth, College of Engineering · May 2026

---

## Overview

Over the past two decades, birth rates across all 50 U.S. states have declined steadily and significantly. This project investigates whether that decline is the product of deep structural forces: economic, temporal, institutional, or whether it reflects intentional personal choice. The answer, as this research argues, is both, and the two reinforce each other in ways that resist simple policy solutions.

The project is structured in two parts:

1. **Socioeconomic Analysis**: A multi-decade, state and national-level analysis of four structural forces driving birth rate decline: economic precarity, time scarcity, family formation friction, and psychological climate.
2. **Discourse Analysis**: An NLP-driven analysis of over 720,000 Reddit posts and comments across four ideologically distinct communities (r/Natalism, r/Childfree, r/Parenting, r/Economics), examining how Americans talk about fertility decline and whether their framing aligns with structural evidence.

---

## Key Findings

- Economic precarity is the dominant cross-ideological driver. The Economic framing frame was the only one present at significant levels across all four Reddit communities (ranging from 22.0 to 51.9 points per 1,000 words), regardless of ideological stance, mirroring the structural data.
- The meaning of economic anxiety varies by community. r/Economics and r/Natalism frame economic precarity as a systemic crisis requiring policy intervention. r/Childfree reframes the same economic reality as a rational basis for personal choice.
- Housing costs and homeownership collapse among younger cohorts are among the strongest structural correlates of birth rate decline, the national House Price Index rose roughly tenfold between 1975 and 2024, while homeownership among the under-35 cohort has seen a steep, only partially recovered decline since 2008.
- Consumer sentiment has not recovered to pre-2008 levels, and as of 2024–2026, pessimism has converged across age groups, income terciles, and regions, suggesting a generational shift in economic outlook rather than a cyclical dip.
- Structural barriers interact and reinforce each other. Rising housing costs compound student loan burdens, delayed homeownership delays marriage, delayed marriage delays first birth, reduced time from family formation window lowers completed fertility. No single cause explains the decline.

---

## Data Sources

| Dataset | Source |
|---|---|
| U.S. Birth Rates by State (2003–2024) | CDC WONDER Natality Data |
| National Poverty Rate (1980–2024) | U.S. Census Bureau SAIPE |
| House Price Index (1975–2024) | Federal Housing Finance Agency |
| Homeownership Rate (1982–2024) | U.S. Census Bureau Housing Vacancy Survey |
| Household Debt by Age Cohort (1999–2025) | Federal Reserve Bank of New York |
| Mortgage Originations by Age (2000–2025) | Federal Reserve Bank of New York |
| Student Loan Delinquency (2000–2025) | Federal Reserve Bank of New York |
| Unemployment & Job Finding Rate (1976–2025) | U.S. Bureau of Labor Statistics |
| Labor Force Participation (1948–2025) | U.S. Bureau of Labor Statistics |
| Multiple Jobholders (1994–2025) | U.S. Bureau of Labor Statistics |
| Childcare Costs by County (2018, 2023) | U.S. Department of Labor |
| Consumer Sentiment Index (2000–2026) | University of Michigan Surveys of Consumers |
| Reddit Posts & Comments (2015–2025) | Keyword-sampled via Reddit API |

---

## Methods

### Socioeconomic Analysis
- State and national-level time series analysis across four analytical forces
- Recession-period shading to contextualize trend inflections
- Age cohort decomposition for debt, homeownership, and mortgage origination data
- Geographic overlap analysis between HPI growth and birth rate decline

### Discourse Analysis (NLP)

| Technique | Purpose |
|---|---|
| TF-IDF with bigrams | Identify community-distinctive vocabulary |
| LDA Topic Modeling | Surface latent thematic patterns within each subreddit |
| Keyword Framing Analysis | Quantify prevalence of five discourse frames (Economic, Cultural/Lifestyle, Political/Policy, Demographic, Emotional/Psychological) normalized per 1,000 words |

**Preprocessing pipeline:** lowercasing → URL/artifact removal → punctuation stripping → stopword removal → lemmatization

**Dataset after cleaning:**

| Subreddit | Posts | Comments |
|---|---|---|
| r/Natalism | 2,293 | 27,557 |
| r/Childfree | 35,594 | 619,205 |
| r/Parenting | 2,815 | 71,391 |
| r/Economics | 177 | 2,630 |

---

## Tech Stack

- Python: core analysis and data pipeline
- NLTK: text preprocessing and tokenization
- Scikit-learn: TF-IDF vectorization, LDA topic modeling
- Matplotlib: all data visualizations
- Pandas / NumPy: data manipulation and aggregation

---

> **Note:** Raw Reddit data is not included in this repository due to size constraints. Data was collected via keyword-based sampling across 22 fertility/birth rate-related terms from 2015–2025.

---

## Visualizations

The project includes 21 figures and 6 data tables, including:

- U.S. birth rate change by state (2003–2024)
- National House Price Index and annual change (1975–2024)
- Homeownership rates by age cohort (1982–2024)
- Total household debt and mortgage originations by age cohort
- Consumer Sentiment Index by region, age group, and income tercile (2000–2026)
- Infant childcare cost as share of family income by county (2018 vs. 2023)
- TF-IDF word clouds for all four subreddits
- Cross-subreddit framing heatmap

---

## Limitations

- Reddit's user base is younger and more politically engaged than the general U.S. population, discourse findings may not generalize broadly.
- Significant size asymmetry across subreddits (r/Childfree has 200× more posts than r/Economics), smaller community findings should be interpreted with caution.
- Keyword-based sampling may exclude relevant posts using different terminology.
- Framing dictionaries are predefined and may not capture evolving community-specific language.
- Confounding variables not addressed include: migration patterns, religious affiliation, racial/ethnic demographic transitions, and social media effects on reproductive intent.
