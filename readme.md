# Prosper Loan Data Exploration
## by Michael Wei

## Dataset

The data consists of information for 114,000 Prosper loans, of which we explored Loan Status, Borrower APR, Lender Yield, Estimated Effective Yield, Prosper Score, Term, Credit Grade, Credit Rating, Listing Category (numeric), Borrower State, Occupation, Employment Status, Homeowner Status, Credit Range, and Income Range. The dataset can be found [here](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv).

The main question I looked at was "How to obtain the highest Borrower APR", using data.

## Methods Used

Basic Data Visualization

## Getting Started

1. Clone this repository ([Instructions](https://help.github.com/en/articles/cloning-a-repository) for cloning)

2. Download the data [here](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv). Since our dataset is somewhat large, we have opted to give a link instead of uploading the file.

3. Package requirements can be found in the requirements.txt file.

## Limitations

This project was focused primarily on creating basic data visualizations. We created a lot of visualizations in the Exploratory Data Analysis part.

## Summary of Findings

In the exploration, I found the following relationships amongst primary variables:

* Borrower APR vs Loan Status - Borrower APR increases as Loan Status worsens
* Lender Yield vs Loan Status - Lender Yield increases as Loan Status worsens
* Estimated Effective Yield (EEY) vs Loan Status - EEY increases as Loan Status worsens
* Prosper Score vs Loan Status - Generally lower Prosper Scores as Loan Status worsens
* Borrower APR vs Prosper Score - Moderately negative correlation

Next, I looked at secondary variables to look for more interactions:

* Borrower APR vs Credit Grade - As Credit Grade improves, Borrower APR decreases.
* Borrower APR vs Prosper Rating - As Prosper Rating improves, Borrower APR decreases.
* Borrower APR vs Credit Rating (Combined Credit Grade/Prosper Rating variable we made; We looked at this variable for the rest of the analysis) - As Credit Rating improves, Borrower APR decreases
* Prosper Score vs Credit Rating - As Credit Rating improves, Prosper Score increases
* Borrower APR vs Listing Category - Lowest Borrower APRs for Not Available (0), Personal Loan (4), and Boat (9) loans. Highest Borrower APRs for Cosmetic (10) and Household Expenses (13)
* Borrower APR vs Borrower State - Lowest Borrower APR in IA and ME. Highest Borrower APR in AL, AR, and SD.
Prosper Score vs Borrower State - Highest for DC (The Prosper Algorithm must think politicians are trustworthy...)
*  Borrower APR vs Occupation - Lowest Borrower APR for Professionals and Students
* Prosper Score vs Occupation - Lowest for Food Services
* Borrower APR vs Employment Status - Highest Borrower APR for "Not Employed" category
* Prosper Score vs Employment Status - Highest for "Full-time" and "Part-time" borrowers. Lowest for "Self-Employed", "Other", and "Not employed" borrowers.
* Borrower APR vs Homeowner Status - Generally lower for homeowners
* Prosper Score vs Homeowner Status - Both at the mean Prosper Scores
* Borrower APR vs Credit Range - After Credit Score of 640, Borrower APR decreases as Credit Range improves.
* Prosper Score vs Credit Range - After 700, Prosper Score improves as Credit Range improves.
* Borrower APR vs Income Range - Borrower APR improves as Income Range improves; Lower than average Borrower APR for "$0" and "Not displayed" ranges.
* Prosper Score vs Income Range - Prosper Score improves above average for the "$100,000+" income ranges
* Borrower APR vs Debt-to-Income Ratio (DTIR) - No meaningful relationship, and lots of outliers at DTIR = 10. For DTIR < 2, we wee Borrower APRs between 5 % and 40 %.
* Prosper Score vs Debt-to-Income Ratio (DTIR) - No meaningful relationship; This shows Prosper Scores range from 1 to 11.
* Debt-to-Income Ratio (DTIR) vs Income Range - No meaningful assessment for "Not Employed" borrowers (Too many null values); However, DTIR generally decreases as we increase Income Range.

More cool plots we made:

* Credit Rating vs Listing Category (numeric) (Counts) - Most loans are within Listing Categories 0 through 10, with Credit Rating between A and E
* Credit Rating vs Employment Status (Counts) - Most borrowers are Employed or Full-time, with Credit Rating between A and E.
* Credit Rating vs Credit Score Range (Counts) - Most loans between Credit Scores 600 and 760, with Credit Rating between A and D.
* Credit Rating vs Income Range (Counts) - Most borrowers between $25,000 and $80,000, with a Credit Rating between A and E.

Multivariate Exploration Plots we looked at:

* Borrower APR vs Loan Status (3rd Variable = Homeowner Status) - Same as Bivariate version, but Homeowners generally have lower Borrower APR
* Prosper Score vs Loan Status (3rd Variable = Homeowner Status) - Same as Bivariate version; No consistent Homeowner trend
* Borrower APR vs Credit Range (3rd Variable = Homeowner Status) - Same as Bivariate version; Homeowners have slightly higher Borrower APRs across Credit Ranges
* Borrower APR vs Income Range (3rd Variable = Homeowner Status) - Same as Bivariate version; Homeowners seem to have slightly lower Borrower APRs across Income Ranges
* Borrower APR vs Debt-to-Income Ratio (3rd Variable = Homeowner Status) - No meaningful relationship
* Borrower APR vs Listing Category (numeric) (3rd Variable = Homeowner Status) - No meaningful relationship; Most data are for Listing Categories 0 through 7
* Borrower APR vs Listing Category (numeric) (3rd Variable = Loan Status Current/Completed) - Completed loans end up with consistently higher Borrower APR
* Borrower APR vs Listing Category (numeric) (3rd Variable = Loan Status Defaulted/Chargedoff) - Average Borrower APR for most listing categories are above the overall average
* Borrower APR vs Credit Range (3rd Variable = Loan Status Current/Completed) - Borrower APR appears to be lower when the loan is completed
* Borrower APR vs Credit Range (3rd Variable = Loan Status Defaulted/Chargedoff) - These loans have Borrower APRs above the overall average; Not sure why there are so many loans with good credit (Above 700) that have Defaulted/Chargedoff.
* Borrower APR vs Prosper Score (3rd Variable = Loan Status Current/Completed) - Borrower APR decreases as Prosper Score increases (well below the overall average for Scores 10 and 11)
* Borrower APR vs Prosper Score (3rd Variable = Loan Status Defaulted/Chargedoff) - Same trend as the Current/Completed loans, but mostly over the overall average; Not sure why we have a subset of data with high Prosper Scores (9 and above) and Defaulted/Chargedoff statuses.
* Borrower APR vs Income Range (3rd Variable = 4 Loan Statuses) - Borrower APRs decrease as Income Range increases, for each Loan Status
* Borrower APR vs Prosper Score (Faceted by Income Range) - No meaningful relationship
* Borrower APR vs Monthly Loan Payment (Faceted by Income Range) - Same clustering of data for top three Income Ranges ($50,000 and above)
* Credit Rating vs Listing Categories (Average Borrower APR) - Focus on Listing Categories 0 through 10; Highest Borrower APRs for E and HR loans across these Listing categories
* Credit Rating vs Employment Status (Average Borrower APR) - Focus on Employed, Full-time, Not available, and Self-employed statuses; Highest Borrower APRs for E and HR loans
* Credit Rating vs Credit Score Range (Average Borrower APR) - Focus on Credit Scores between 600 and 760; Highest Borrower APRs for Credit Rating E.
* Credit Rating vs Income Range (Average Borrower APR) - As Credit Rating worsens, Borrower APR increases. With Credit Ranges A, B, C, D, E, and HR, average Borrower APR increases as we increase income range.

## Key Insights for Presentation

While we explored a bunch of potential relationships, we chose to focus on a few variables for the Explanatory Data Analysis portion. We focus on variables that influence Borrower APR and Prosper Score, optimizing for the highest (Worst) Borrower APR.

To start, we looked at the distribution of variables to get an idea of where most of the data lie, using histograms and count plots. Next, we look at possible relationships between the variables using box plots, scatter plots, point plots, and heat maps. At the end, we zoomed in on areas of the heat maps to gauge borrower APRs. In this study, we optimized for the highest Borrower APR. We also looked at Prosper Scores to see if they related to Borrower APRs.

In the end, we show the following plots:

### Univariate Distributions

* Loan Status
* Borrower APR
* Prosper Score
* Credit Rating
* Listing Category
* Employment Status
* Credit Score Range
* Income Range
* Homeowner Status

### Bivariate Plots

* Borrower APR vs Loan Status
* Prosper Score vs Loan Status
* Borrower APR vs Prosper Score
* Borrower APR vs Credit Rating
* Prosper Score vs Credit Rating
* Borrower APR vs Listing Category
* Prosper Score vs Listing Category
* Borrower APR vs Employment Status
* Prosper Score vs Employment Status
* Borrower APR vs Credit Range
* Prosper Score vs Credit Range
* Borrower APR vs Income Range
* Borrower APR vs Homeowner Status
* Prosper Score vs Homeowner Status

### Other Cool Plots (For Counts)

* Credit Rating vs Listing Category
* Credit Rating vs Employment Status
* Credit Rating vs Credit Score Range
* Credit Rating vs Income Range

### More Cool Heat Maps (Average Borrower APRs)

* Credit Rating vs Listing Category
* Credit Rating vs Employment Status
* Credit Rating vs Credit Score Range
* Credit Rating vs Income Range

## Credits

* Example readme file template 1: https://github.com/sfbrigade/data-science-wg/blob/master/dswg_project_resources/Project-README-template.md

* Prosper Loan Dataset: www.prosper.com/‎

* Udacity Data Analyst Program contents
