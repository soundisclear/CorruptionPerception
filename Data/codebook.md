# Codebook

Variables used in `Corruption_Perception_Project.qmd`. Variable names for the WVS follow the Wave 7 dataset; see the official WVS documentation for full question wording.

## World Values Survey, Wave 7

| Variable | Renamed to | Description | Values |
|---|---|---|---|
| `A_YEAR` | | Year of survey | 2020 used |
| `B_COUNTRY_ALPHA` | | ISO-3 country code | e.g., CAN, NZL, SGP |
| `D_INTERVIEW` | | Interview ID | |
| `Q260` | `sex` | Respondent sex | 1 = Male, 2 = Female |
| `Q262` | `age` | Respondent age | Years |
| `Q275R` | `education` | Education level (3 categories) | 1 = Lower, 2 = Middle, 3 = Higher |
| `Q112` | `corruption_perception` | Perceived corruption in own country | 1-10 (higher = more corruption perceived) |

**Derived variable:** `age_category` is built from `age`: young (16-29), middle (30-49), senior (50+).

**Missing values:** WVS codes -1, -2, -4, and -5 (non-response codes) are recoded to `NA`.

## World Bank World Development Indicators

| Variable | Description | Units |
|---|---|---|
| `ControlCorruption` | Control of Corruption estimate | Index, roughly -2.5 to +2.5 (higher = stronger control) |
| `GDP` | Gross domestic product | Current US dollars |
| `GDPgr` | Annual GDP growth | Percent, constant prices |

**Missing values:** The World Bank marks missing values with `..`, which are converted to `NA`.
