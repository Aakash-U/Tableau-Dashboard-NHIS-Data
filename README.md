# Understanding Dynamics of Diabetes and Hyperlipidemia in the US Population

## Project overview

This repository contains a Tableau dashboard and supporting materials for an
exploratory analysis of the relationship between diabetes and hyperlipidemia in
the US population. The underlying data are drawn from five years of the
National Health Interview Survey (NHIS, 2017–2021). The dashboard allows users
to filter by age and sex and to observe how the two conditions co‑occur.

## Motivation

The goal of the project was to gain hands‑on experience with healthcare data
science tools and to investigate a well‑studied medical topic using a
publicly‑available survey. The dashboard is intended as a proof‑of‑concept
for interactive analysis of national survey data.

## Dataset

- **Source:** National Health Interview Survey, 2017–2021 (public‑use files).
- **Years included:** 2017, 2018, 2019, 2020, 2021 (five annual releases).
- **Key variables analysed:**
  - **AGEP** – age in years (capped at 85 in the public file for anonymity).
  - **SEX** – 1 = male, 2 = female.
  - **DIABETES** – 1 = diagnosed with diabetes, 2 = pre‑diabetic, 3 = no
    diabetes. (Values were recoded to 0/1/2 for clarity.)
  - **HYPEV** – high cholesterol (0 = no, 1 = yes).
- **Cleaning & transformation:**
  - Variable names were adjusted for readability.
  - Categorical responses were recoded consistently.
  - Records with invalid or missing responses (refused, unknown, etc.) were
    excluded.
  - Merged the five annual files into a single analysis dataset.

### Data prep tools

The raw NHIS files were processed using a mix of:

- **Python** (pandas, NumPy, Jupyter notebooks) for exploratory analysis.
- **SAS** for initial variable extraction and recoding.
- **SQL** (PostgreSQL) for joining and filtering the annual files.
- Tableau Desktop for building the final visualisations.

## Key findings

The dashboard and accompanying analyses reproduce patterns well documented in
the literature:

- **Age is the primary risk factor.** Diabetes prevalence increases sharply
  with age, rising from near‑zero in children to over 20 % in individuals
  aged 65+. The line graph in Worksheet 2 illustrates the steep upward trend
  in the 45‑ to 74‑year range.
- **Sex differences.** Males exhibit approximately 10–15 % higher rates of
  diagnosed diabetes than females across most age groups (see the “Only Males”
  and “Only Females” snapshots).
- **Comorbidity with hyperlipidemia.** A large proportion of respondents
  reporting diabetes also report high cholesterol; the horizontal‑line chart
  breaks out counts by hyperlipidemia status and shows the bulk of diabetic
  cases in the “yes” category.
- **Prediabetes is common in middle‑aged adults.** The age‑26 and age‑57
  snapshots highlight how pre‑diabetic classification is concentrated in the
  35–60 age range.

These insights are consistent with peer‑reviewed epidemiological studies of US
NHIS data.

## Technologies / tools used

- Tableau Desktop (authoring, v2021.4+)
- Tableau Public (optional for viewing)
- Python 3.x (pandas, NumPy, Jupyter)
- SAS 9.4
- PostgreSQL / SQL for data manipulation
- NHIS public‑use data files (2017–2021)

## Project structure

| Name                     | Description |
|--------------------------|-------------|
| `NHIS Dashboard.twb`     | Tableau workbook with two worksheets and one interactive dashboard. |
| `screenshots/`           | PNG images showing various views of the dashboard. |
| `README.md`              | This document. |

## Tableau dashboard overview

- **Worksheet 1:** demographic filters (age, sex) and cross‑tabulation of
  diabetes versus hyperlipidemia.
- **Worksheet 2:** horizontal line graph showing counts of diabetes cases by
  hyperlipidemia status.
- **Dashboard:** combines the two worksheets with interactive filters; users
  may select age ranges and sex to update both views simultaneously.

## Dashboard snapshots

### General overview

![General Overview](./screenshots/General%20Overview.png)  
*Full dashboard with age/sex filters, cross‑tab of diabetes vs. hyperlipidemia
(left) and the horizontal line graph (right).*

### Workbook views

![Workbook 1](./screenshots/Workbook%201.png)  
*Worksheet 1: counts by diabetes/hyperlipidemia status with demographic
filters.*

![Workbook 2](./screenshots/Workbook%202.png)  
*Worksheet 2: horizontal line graph showing diabetes counts stratified by
hyperlipidemia.*

### Gender‑based analysis

![Only Females](./screenshots/Only%20Females.png)  
*Dashboard filtered to female respondents; used to compare sex differences.*

![Only Males](./screenshots/Only%20Males.png)  
*Dashboard filtered to male respondents.*

### Age‑specific analysis

![Age 26](./screenshots/Age%3D%2026.png)  
*View restricted to 26‑year‑olds; pre‑diabetes category visible.*

![Age 57](./screenshots/Age%20=%2057.png)  
*View restricted to 57‑year‑olds; demonstrates higher diabetes/hyperlipidemia
prevalence in older adults.

## Installation / setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Aakash-U/Tableau-Dashboard-For-National-Health-Interview-Survey.git
   cd Tableau-Dashboard-For-National-Health-Interview-Survey
   ```

2. **Obtain the NHIS data.**  
   Public‑use data and documentation are available from the CDC:

   - 2017 & 2018 (archived page):  
     https://archive.cdc.gov/www_cdc_gov/nchs/nhis/1997-2018.htm
   - 2019, 2020 & 2021 (current documentation):  
     https://www.cdc.gov/nchs/nhis/documentation/2025-nhis.html

   (general NHIS page: https://www.cdc.gov/nchs/nhis/index.htm)

3. **Prepare the data (optional).**  
   Use SAS, Python, and/or SQL to clean and merge the annual files as
   described in the “Dataset” section. A sample Jupyter notebook is included
   in the repository.

4. **Open the Tableau workbook.**

   a. Download `NHIS Dashboard.twb` from this repository (using the **Download**
      button or `git pull`).

   b. Launch **Tableau Desktop** (2021.4 or newer).  
      - If the workbook references an external data source (CSV from step 3),
        Tableau will prompt you to locate it; navigate to the cleaned file on
        your machine.
      - If you only have the packaged data, the workbook will open immediately.

   c. Interact with the dashboard using the filters along the top and left
      panels; hover over marks to see tooltips.

   d. To publish or share, save the workbook to Tableau Public or export as
      PDF/image via the **File → Export** menu.

   If you do not have Tableau Desktop, you can still view the static
   screenshots or upload the workbook to Tableau Public (free) and browse in a
   web browser.

## How to view

With Tableau Desktop:

- Download the `NHIS Dashboard.twb` file from this repository.
- Open it in Tableau Desktop as described above and interact with the filters.

Without Tableau Desktop:

- Browse the `screenshots/` folder for static images.
- Optionally, upload the workbook to Tableau Public and view it in a web
  browser.

## Data source

National Health Interview Survey (NHIS) public‑use data, years 2017–2021.
Annual data and documentation are available from the CDC:

- 2017‑2018 archive: https://archive.cdc.gov/www_cdc_gov/nchs/nhis/1997-2018.htm
- 2019‑2021 documentation: https://www.cdc.gov/nchs/nhis/documentation/2025-nhis.html

## Author / contact

Aakash Upadhyay  
GitHub: https://github.com/Aakash-U  
LinkedIn: http://www.linkedin.com/in/aakash-upadhyay-524347137

## Acknowledgments

Credit to the National Center for Health Statistics (NCHS) and the NHIS
program for conducting the survey and providing the data.

---

*This README was updated to remove emojis, standardize formatting, correct
paths, add tool/instruction sections, and incorporate accurate dataset links
and contact information.*