# PSA Game Info Extracted From Cards

## Card KC1

### Title
REPORT -HEALTHCARE

### Text

In the three affected cities, weekly pediatric hospital admissions for infection-related complications have increased over the last three weeks from 2 to 10 per 100K children under 12.

No hospitalizations over age 12 or deaths at any age have been attributed to the virus.

## Data from Card KC1

### Number of Population Group

| 3 | Cities |
|---|--------|

### Population Group Characteristics

| Age | Under 12 |
|-----|----------|

### Hospital Admissions

> per 100k

| Timeframe | Daily Admissions (Approx) | Weekly Admissions |
|-----------|---------------------------|-------------------|
| Current   | 1.43                      | 10                |
| -14 Days  | 0.3                       | 2                 |

### Test Results

| Timeframe  | Positive Test Results |
|------------|-----------------------|
| Current    | 0                     |
| Cumulative | 0                     |

## Card KC3

### Title

REPORT – PATHOGEN 

### Text
Type:
- Influenza A H9N2

Disease Characteristics:
- Onset: 7 days (estimated mean)
- Acute symptoms: mild to severe, typical of influenza; more serious forms involve bronchitis, pneumonia, dehydration, febrile convulsions
- Duration: 7 days (estimated mean)

Reservoir: 
- Similar H9N2 detected in wild avian populations
- Unknown for poultry

## Card KC4

### Title

PROFILE – GREY LAND

### Text

Political factors:
- System: Democracy
- International relations: Collaborative
- Transparency index: Good

Demographic factors
- Population: 18M
- Population over age 65: 20%
- Population under age 14: 11%

Socioeconomic factors 
- Income: medium
- Relative poverty: low
- Unemployment rate: low-medium
- Health systems:  effective, good accessibility and medium inequality


## Card KC5

### Title

PREDICTION – MOLECULAR

### Text

Clustering analysis of pathogen sequences indicates: 
- Potential high mortality rate in adults 
- Potential low transmission rate in all ages


## Card KC7

### Title

PROFILE – TESTING CAPACITY

### Text

National labs can run approximately 200 high accuracy test per day, with a 24-36 hour turn around. 

Home tests for influenza are widely available but may not detect H9N2 infections.

## Data From Card KC7

### Testing Rate Limits

| Timeframe | Test Count Limit |         |
|-----------|------------------|---------|
| Current   | 200              | per day |

### Test Results Lag Time

| Lag Time | Time |     |
|----------|------|-----|
| Min      | 1    | day |
| Max      | 1.5  | day |

### Other Testing Available

Maybe?

## Card KC8

### Title

PREDICTION – HOSPITALIZATION CAPACITY

### Text

Based on the data available four plausible scenarios have been analyzed for possible emergence of the virus in Blue Land.  The likelihood of each scenario is not yet clear.

### Graph

![image](https://user-images.githubusercontent.com/57882845/188958265-d91d1248-d231-41a9-9be5-29d045d495d1.png)

## Data From Card KC8

### Peak Hospitalizations

> Note: Blue Land

| Severity/Transmissibility | Peak Hospitalizations | Per  |
|---------------------------|-----------------------|------|
| Low/Low                   | 11                    | 100k |
| Low/High                  | 13                    | 100k |
| High/Low                  | 29                    | 100k |
| High/High                 | 42                    | 100k |

### Estimated Surge Capacity

> Note: Blue Land

| Peak Hospitalizations | Per  |
|-----------------------|------|
| 26                    | 100k |

## Card KC9

### Title

PROFILE - AIR TRAVEL

### Text

On average week, 22,500 people take three-hour direct flights from Grey Land to Blue Land, primarily for business.

In two weeks, we expect a 23% increase in travel from Grey Land to Blue Land for a four-day holiday.

## Data From Card KC9

### Visitation Rates

| Visitors (Total) | Per  |
|------------------|------|
| 22,500           | week |

### Holiday Visitation Modifier

- Visitors from Grey to Blue incease by 23% on (some) holidays
- Weekly correction should be:
  > (Rate * 0.23 * 4/7) + Rate

| Visitors (Total) | Per  |
|------------------|------|
| 25,457           | week |
