# Thompson Sampling Implementation for Ad Click Optimization

This repository contains a Python implementation of the **Thompson Sampling** algorithm, applied to the **multi-armed bandit** problem for optimizing ad clicks. The goal is to maximize the total reward (clicks) by selecting the best ads for each user based on previous interactions.

## Overview

Thompson Sampling is a popular algorithm for solving the multi-armed bandit problem, which involves balancing exploration (trying new ads) and exploitation (focusing on the best-performing ads). The algorithm uses a probabilistic approach, specifically the **Beta distribution**, to model the likelihood of success for each ad.

This repository demonstrates the use of Thompson Sampling in a simulated ad-click environment. The code selects ads for 10,000 users based on their historical click-through rates, and tracks the total number of clicks for each ad.

## Table of Contents

- [Dependencies](#dependencies)
- [Dataset](#dataset)
- [Code Overview](#code-overview)
- [Results](#results)
- [Visualizations](#visualizations)

## Dependencies

To run this project, you will need to install the following Python libraries:

- `numpy`
- `matplotlib`
- `pandas`

You can install the required libraries using pip:

```bash
pip install numpy matplotlib pandas
```
## Dataset
The dataset used in this project is `Ads_CTR_Optimisation.csv`, which contains data on 10 ads and 10,000 user interactions. The dataset is structured with the following columns:

- Rows represent individual users (10,000 users in total).
- Columns represent the ads (10 ads in total).
- Each cell contains a `1` (ad was clicked) or `0` (ad was not clicked).
You can download the dataset from the source where it is provided, or use a similar dataset for testing the Thompson Sampling algorithm.

## Code Overview
1. Data Loading: The dataset is loaded using `pandas` into a DataFrame.
2. Thompson Sampling Implementation:
  - We initialize the counts of rewards (clicks and no-clicks) for each ad.
  - For each user, we simulate the process of selecting the ad with the highest probability of being clicked using the Beta distribution.
  - The ad is selected based on the highest sampled probability, and the reward (click or no-click) is recorded.
3. Reward Calculation: The total reward is computed based on the sum of all clicks (1s) across all users.
4. Ad Selection Tracking: We track which ads were selected and how often.

## Results
After running the algorithm, the total reward (clicks) and the frequency of ad selections are displayed. The histogram shows how often each ad was selected based on the Thompson Sampling algorithm.
```plaintext
Total Reward: 2600
Histogram of ad selections
Ad 7 was selected the most (375 times), while Ad 4 was selected the most often (9131 times).
```
## Visualizations
A histogram is generated to visualize the number of times each ad was selected during the experiment. This helps to understand the distribution of ad selections and the effectiveness of Thompson Sampling.
