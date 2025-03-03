# Analyzing Voting Difficulty
This repo contains code for the report: [Analyzing Voting Difficulty](https://drive.google.com/file/d/1d_LIj2fJ6ix8VHUcpy8ViZv7QVBW8G50/view). 
It uses Wilcox test to understand whether Democratic voters or Republican voters experience more difficulty voting.

All code can be found under: analyzing_voting_diff.Rmd
All data used in the project can be found under the data folder.

## Overview
This project investigates whether Democratic or Republican voters experience more difficulty voting in U.S. elections. The analysis is based on data from the **American National Election Studies (ANES) 2022 Pilot Study**, which includes responses from 1,585 participants. The goal is to provide transparency and insights into voting difficulties, which can help improve political and civic engagement.

## Research Question
**Do Democratic voters or Republican voters experience more difficulty voting?**

## Data Source
The dataset used is the **ANES 2022 Pilot Study**, collected by YouGov. It includes responses from 1,585 participants, with 85 unweighted cases removed as recommended by the study.

## Methodology
### Data Preparation
1. **Voter Classification**:
   - Voters are defined as those who are registered to vote (`reg` = 1 or 2) or answered the "how difficult was it to vote" question (`votehard` ≠ -1).
   - Democrats are classified as those who responded "Democrat" to `pid1d`, `pid1r`, or `pidlean`.
   - Republicans are classified as those who responded "Republican" to the same questions.

2. **Voting Difficulty**:
   - The variable `votehard` measures voting difficulty on a scale from 1 (Not difficult at all) to 5 (Extremely difficult).
   - After filtering, the dataset contains 976 rows (525 Democrats and 451 Republicans).

### Statistical Test
- **Wilcoxon Rank-Sum Test**:
  - Used to compare the voting difficulty between Democrats and Republicans.
  - Assumptions:
    1. Data is independent and identically distributed (I.I.D.).
    2. Data is ordinal and non-parametric.
  - **Null Hypothesis**: The probability of Democrats experiencing more difficulty voting is equal to the probability of Republicans experiencing more difficulty voting.
  - **Alternative Hypothesis**: The probabilities are not equal.

## Results
- **Summary Statistics**:
  - Democrats: Mean `votehard` = 1.28, Standard Deviation = 0.66.
  - Republicans: Mean `votehard` = 1.12, Standard Deviation = 0.47.

- **Wilcoxon Rank-Sum Test**:
  - The test results show a statistically significant difference (W = 1.306215 × 10^5, p = 3.6163904 × 10^-6).
  - **Conclusion**: The probability of Democrats experiencing more difficulty voting is not equal to the probability of Republicans experiencing more difficulty voting.

- **Visualization**:
  - Figure 1 shows the distribution of voting difficulty scores by party.
  - Figure 2 shows the reasons for voting difficulty by party.

## Discussion
The study found evidence that the probability of Democrats experiencing more difficulty voting is not equal to that of Republicans. However, the test does not indicate which group experiences more difficulty. Future studies could:
1. Conduct additional statistical tests (e.g., two-proportion test) on specific reasons for voting difficulty.
2. Use ANES-provided weights to make better inferences about the general population.

## Requirements / Dependencies
### Software
- **R** (version 4.0 or higher)
- **RStudio** (optional, but recommended for ease of use)

### R Packages
- `ggplot2`
- `dplyr`
- `tidyverse`
- `tidyr`
- `knitr`
- `kableExtra`

### Data
- **ANES 2022 Pilot Study Dataset**: Available from the ANES website. Ensure the dataset is downloaded and placed in the working directory.

### Code Execution
1. Install the required R packages using the following command:
   ```R
   install.packages(c("ggplot2", "dplyr", "tidyverse", "tidyr", "knitr", "kableExtra"))
Load the dataset and run the provided R code to reproduce the analysis.

### References
Hartig, H., Daniller, A., Keeter, S., & Green, T. V. (2023, July 12). Voter turnout, 2018-2022. Pew Research Center.

American National Election Studies (ANES). (2022). ANES 2022 Pilot Study.

This report is completed as part of a collaboration project for a Berkeley class called Statistics for Data Science. If you would like to learn more, please check out UC Berkeley master's programs.
