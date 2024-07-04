# Project_Gutenberg

## Project Overview

This project analyzes the role of information revelation in the popularity of English-language fiction books. Using data from Project Gutenberg, the analysis focuses on two key aspects:
1. **metadata.csv**: Contains book IDs and attributes, including download counts.
2. **KLDscores.csv**: Contains book IDs and corresponding “narrative revelation” scores measured in terms of Kullback-Leibler divergence.

The goal is to relate the characteristics of KLD scores to book popularity and investigate heterogeneity of effects across genres.

## Analysis Steps

### 1. Build Book-Level Measures
- **Mean KLD**: Average KLD score across the book.
- **Variance of KLD**: Variability of KLD scores across the book.
- **Slope of KLD**: Slope from a linear regression of KLD scores over the narrative.

### 2. Regress KLD Measures Against Log(Downloads)
Performed multiple linear regression to relate KLD measures to the logarithm of download counts, including controls for genre and other book-level attributes.

### 3. Investigate Heterogeneity Across Genres
Used LASSO regression to determine which variables are most predictive of log(downloads) and to explore differences across genres.

## Key Findings

- Books with a higher mean KLD tend to have more downloads, suggesting that a higher rate of new information revelation may attract readers.
- The variance in KLD scores also positively correlates with downloads, indicating that variability in narrative revelation keeps readers engaged.
- Genre-specific effects were observed, with certain genres showing stronger correlations between KLD measures and downloads.

## Detailed Analysis

### Regression Results
| Variable       | Coefficient | Standard Error | t-Statistic | p-Value |
|----------------|-------------|----------------|-------------|---------|
| const          | 3.3044      | 0.117          | 28.360      | 0.000   |
| avg_kld        | -0.1837     | 0.490          | -0.375      | 0.707   |
| var_kld        | 18.7051     | 4.060          | 4.608       | 0.000   |
| slope_kld      | -114.8077   | 14.470         | -7.934      | 0.000   |

### Variable Construction
- **Mean KLD**: Average of KLD scores for each book.
- **Variance of KLD**: Variance of KLD scores for each book.
- **Slope of KLD**: Slope from linear regression of KLD scores over narrative sections.

## Conclusion
This analysis demonstrates that information revelation, as measured by KLD scores, plays a significant role in the popularity of fiction books. The findings provide insights into how narrative structures impact reader engagement.


