# Play Ball off of Payroll
MSDS 692 - Practicum Project

Author: Pat Kennedy

## Research Question
What effect does a MLB team’s payroll have on the success and output of the product on the field? 
- Are there correlations with:
  - Winning percentage?
  - Team statistics?
    - Hitting
    - Pitching
  - Postseason?

## About the Data
Two datasets:
- Historical Dataset: [MLB_HistoricalPayroll.csv](https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/files/14544075/MLB_HistoricalPayroll.csv)
  - 2019 – 2023
  - 1st half of dataset: Financial Data (Payroll Information & Ranking)
  - 2nd half of dataset: Performance Data (Win %, batting stats, pitching stats, Postseason - Y/N)
- Future Dataset: [MLB_FuturePayroll.csv](https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/files/14544088/MLB_FuturePayroll.csv)

  - 2024 Financial Data
  - No Performance Data (season has yet to start)
  - Goal: Make predictions for 2024 Performance Data

## Examining Relationships
(From Historical Dataset)
- Key:
  - Light Tan = Strong Positive correlation
  - Dark Purple = Strong Negative correlation
  
![PayrollRelationships](https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/assets/146998300/1c4f943b-1d9d-45ef-bb7e-a86fd97db6f8)

Findings: There are strong relationships between Pitching Stats (WHIP / ERA) & Postseason

## More Relationships
(From Historical Dataset)
Examining the relationship between Payroll Rank and Winning Percentage

- Key:
  - Red = Team made Postseason
  - Blue = Team did not make Postseason
 
![Rank:Win%](https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/assets/146998300/38c4866a-23b8-4fa6-9eb1-38263a760f30)

Findings:
- Teams that rank in the top 5 in payroll made the playoffs 14/20 times. That is 70%
- There have only been 3 instances of a team in the top 5 rank that had a below .500 winning percentage.

## Predictive Model
Since the goal of the project is to predict multiple outputs for the future dataset based on trends from the historical dataset, I decided to use a Random Forest Regressor wrapped in a Multi-Output Regressior.

From Historic Dataset:
- Features: Financial Data columns
- Targets: Performance Data columns

Scaled the historical dataset and used the same scale to the future dataset.

## Findings
In the MLB, 12 Teams make the Postseason in a given season (6 from each League).

The model I built selected the teams that had the highest percentage chance of making the postseason out of 30 teams for each League. Here, they are listed, with respects to their chance of making the postseason as well as where they would be positioned in the postseason clinchings:

American League
1) Kansas City Royals (94%) - Central Division Winner
2) Seattle Mariners (93%) - West Division Winner
3) Chicago White Sox (89%) - Wild Card Team #1
4) Houston Astros (75%) - East Division Winner
5) Toronto Blue Jays (71%) - Wild Card Team #2
6) Texas Rangers (66%) - Wild Card Team #3

National League
1) Los Angeles Dodgers (84%) - West Division Winner
2) Philadelphia Phillies (77%) - Central Division Winner
3) Atlanta Braves (75%) - East Division Winner
4) St. Louis Cardinals (68%) - Wild Card Team #1
5) New York Mets (58%) - Wild Card Team #2
6) Pittsburgh Pirates (54%) - Wild Card Team #3

## Predicted 2024 Postseason Bracket
<img width="1139" alt="PostseasonBracket" src="https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/assets/146998300/ae5eb181-8a98-46c6-822e-5d125c28bd87">

## All 2024 Predictions:
[2024_Predictions.csv](https://github.com/patkennedy11/MSDS692_PracticumProject--Play_Ball_off_of_Payroll/files/14544057/2024_Predictions.csv)
