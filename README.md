# Corruption Perception Analysis

How do demographics, education, and national institutions shape people's perceptions of corruption? This project merges World Values Survey (WVS) Wave 7 data with World Bank indicators and tests three hypotheses in R. It also includes a case study of Afghanistan's economy from 2000 to 2023.

**[View the live report]()**

## Research Questions
1. Do men and women differ in how corrupt they perceive their country to be?
2. Do countries with stronger institutional control of corruption report lower perceived corruption?
3. Do more educated people report lower perceived corruption?
4. Case study: how did Afghanistan's GDP and growth change from 2000 to 2023?

## Key Findings
- **Sex:** No difference in perceived corruption (men 7.09, women 7.10; p = 0.85).
- **Institutions:** Countries with stronger control of corruption report lower perceived corruption (r = -0.69, p = 0.006). The result is suggestive rather than conclusive because the sample has only 14 countries and a gap in the middle of the distribution.
- **Education:** Higher education looks associated with lower perceived corruption when all respondents are pooled, but the gap disappears (and slightly reverses) when comparing people within the same country. The pooled result mostly reflects differences between countries.
- **Afghanistan:** GDP grew from about $3.5B (2000) to over $20B (2013), then contracted about 21% in 2021.

## Data
| Dataset | Description | Included in repo? |
|---|---|---|
| World Values Survey, Wave 7 (2017-2022) | Individual survey responses. This project uses the 2020 cross-section: 21,187 respondents from 14 countries. | No. The WVS conditions of use prohibit redistributing the data files. Download it yourself after registering: https://www.worldvaluessurvey.org/WVSDocumentationWV7.jsp |
| World Bank World Development Indicators | Country-level indicators, including Control of Corruption and GDP. Accessed: (month, year). | Yes, in `Data/` |

Variable definitions are in [`Data/codebook.md`](Data/codebook.md).

## Methods
- Cleaned survey data: recoded non-response codes to `NA`, renamed variables, built age categories
- Reshaped World Bank data from wide to long (`pivot_longer`, `pivot_wider`)
- Joined survey and country data on ISO-3 country codes with a relational `left_join()`
- Ran Welch t-tests, Pearson and Spearman correlations, and linear regression (pooled and with country baselines)
- Built visualizations with `ggplot2`

**Data note:** The WVS also provides Correlates of War country codes, but joining on them silently matched Mongolia to Montenegro's World Bank data. This project joins on ISO-3 codes instead.

## Limitations
- Only 14 countries appear in the 2020 WVS cross-section, so country-level results rest on 14 observations.
- Results are correlational and descriptive, not causal.
- GDP is in current US dollars and growth is in constant prices, so the two Afghanistan charts are not directly comparable.

## How to Reproduce
1. Install R, RStudio, and Quarto.
2. Install the packages: `tidyverse`, `ggplot2`, `stringr`, `maps`, `here`, `readr`.
3. Download WVS Wave 7 (R format) from the link above and save it as `WVS_W7.rds` in the `Data/` folder.
4. Open the `.qmd` file and render it.

## Tools and Skills
R, Quarto, tidyverse, ggplot2. Skills shown: data cleaning and reshaping, relational joins, hypothesis testing, regression, data visualization, and reproducible reporting.

## Data Sources and Citations
- Haerpfer, C., Inglehart, R., Moreno, A., Welzel, C., Kizilova, K., Diez-Medrano J., Lagos, M., Norris, P., Ponarin, E. & Puranen, B. (eds.). *World Values Survey: Round Seven, Country-Pooled Datafile.* Madrid, Spain & Vienna, Austria: JD Systems Institute & WVSA Secretariat. https://www.worldvaluessurvey.org
- World Bank. *World Development Indicators.* Washington, DC: The World Bank. https://databank.worldbank.org/source/world-development-indicators

## Author
Marshall Prizio
B.A. Sociology, Minor in Political Science, Data Analytics & Computational Social Science Certificate, UMass Amherst

GitHub: [@soundisclear](https://github.com/soundisclear)
