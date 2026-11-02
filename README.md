# King County House Price Analysis

An analysis of the relationship between interior living space and home sale prices in King County, Washington, using R and simple linear regression.

**Author:** Adrian Cheung

## Research Question

Is living space a statistically significant predictor of home sale price? What is the estimated difference in price associated with an additional 100 square feet of living space?

## Dataset

The analysis uses the [House Sales in King County, USA](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction) dataset from Kaggle, containing over 21,000 home sale records from May 2014 to May 2015.

The two main variables are:

- **`price`**: Home sale price in US dollars.
- **`sqft_living`**: Interior living space in square feet.

## Methods

- Filtered records to retain positive, nonmissing prices and living areas.
- Summarized sale prices and living space.
- Visualized the relationship using a scatterplot and fitted regression line.
- Fit a simple linear regression model: `price ~ sqft_living`.
- Examined residual plots, normality, unequal variance, and influential observations.
- Calculated a slope estimate, hypothesis test, confidence interval, and R-squared.

## Main Finding

Larger living spaces were associated with higher sale prices. The fitted model estimated approximately **$28,000 higher sale prices per additional 100 square feet**.

This estimate describes an association in the observed data and should not be interpreted as the causal effect of adding space to a home.

## Limitations

The model includes only living space. Location, property condition, waterfront access, and other characteristics may also explain differences in price.

Diagnostic plots indicate unequal residual variance and departures from normality. The report uses conventional regression standard errors and confidence intervals, so its inference should be interpreted cautiously. A large sample alone does not resolve unequal variance.

The analysis does not evaluate prediction accuracy on held-out data, and findings may not generalize beyond the location and period studied.

## Repository Files

- [house_price_data_analysis.Rmd](house_price_data_analysis.Rmd): R Markdown source containing the analysis and code.
- [house_price_data_analysis.html](house_price_data_analysis.html): Rendered report with plots and results. Download and open in a web browser to view.

## How to Run

1. Download `kc_house_data.csv` from the dataset link above.
2. Create a `data` folder in the repository and place the CSV inside it.
3. Ensure the data-loading line in the R Markdown file is:

   ```r
   house_data <- read_csv("data/kc_house_data.csv")
   ```

4. Install the required R packages:

   ```r
   install.packages(c("tidyverse", "scales", "knitr", "rmarkdown"))
   ```

5. Open `house_price_data_analysis.Rmd` in RStudio and click **Knit** to generate the HTML report.

## Tools

R, R Markdown, tidyverse, ggplot2, and knitr.
