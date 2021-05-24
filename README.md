# Nigeria-COVID-19-Data-Analysis-Using-Python
Data Scientist Microdegree Capstone Project - Ustacky

The project is an analysis of datasets related to COVID19 in Nigeria. It is expected  to test ability to explore data, prepare data, and carry out certain analysis procedures.

It invloved 3 major steps:

### 1. Data Collection
Data was obtained by web scraping as well as, direct Pandas reading of CSV files.
    For web scraping, BeautifulSoup was used to obtain data table from the website of Nigeria Center for Diseases Control. This required understanding how to utilize the inspect option after right-clicking an object on a webpage. The inspect option allowed visualization of the HTML lines surrounding the webpage, which made it easy to select the sections of interest on [COVID-19 Nigeria](https://covid19.ncdc.gov.ng/) - Confirmed Cases By States.

For the dataset on the [John Hopkins Repository](https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series), the Pandas method pd.read_csv('url') was used for importation. For easy readability, the country name was used as the index with parameter "index_cols" == Country/Region. This method was used to obtain information on daily confirmed cases, daily recovered cases, and daily deaths, across 275 countries of the world.

Other datasets were locally available, and were saved into a dataframe using the pd.read_csv(). Their names: 
* `Budget data.csv` which has initial and revised budgets by states in Billions.
* `covid_external.csv` which contains overall Covid19 Community Vulnerability Index for Nigeria, with other factors considered.
* `RealGDP.csv`, which contains the quarterly GDP of Nigeria from 2014 to 2020.
    
In total, 7 dataframes were used to initiate the analysis process.

NB: All datasets from the web contains information up until 24/05/2021.

### 2. Data Exploration, Cleaning & Preparation
All datasets were explored for basic information using df.head(), df.isnull().sum(), df.info(), and df.tail(). 
From the displayed results, 5 of 6 datasets had appropriate data types. The COVID 19 dataset obtained from NCDC had the 'number of cases' in `object` datatype, and this was corrected using appropriate Pandas method to convert to `numeric`.

From the general daily updated data in John Hopkins repository, data specific to Nigeria was extracted using Pandas method to select a row feature specific to Nigeria. The extracted data were saved to new dataframes for easy analysis.

All lines of code for this process are detailed in the jupyter notebook.

### 3. Analysis
From Nigeria's Covid19 Cases dataset, Bar plots were generated to show the top 10 states in terms of laboratory confirmation, discharge,and deaths.
Using the datasets extracted from the daily updates repository, 3 line plots were generated for the total confirmed, recovered, and death cases, over the last 10 days documented in the data.
Infection and recovery rate in Nigeria was also visualized using line plots. Pandas methods like `.diff`, `.pct_change`, and `.tail` were used.
Comparative graphs were also generated (barplots and lineplots) to highlight the relationship between certain factors such as: vulnerability index and laboratory confirmed cases; population density and confirmed cases, and so on.

#### * Insights from Analysis
* In Nigeria, 27th of April, 2021 has the highest number of confirmed cases over the past 30 days. 8th of May, 2021 has seen the highest number of recovery, and 5th of May, 2021 with the highest deaths (2 deaths).
* In terms of lab confirmed cases in Nigeria, the top 10 states are Lagos, FCT, Kaduna, Plataeu, Rivers, Oyo, Edo, Ogun, Kano, and Ondo. Among these, Kaduna appears to have felt the impact the most, with vulnerability index of `0.7`.
* There is a linear relationship between the population density and confirmed cases, as displayed by the regression plot.
* There is a daily increase in confirmed cases. To prevent a more intense wave, it is important for protective measures to continue to be strictly followed.
* Nigeria's real GDp was greatly impacted by the COVID19 outbreak. In comparison to the past year, 2020 (the year of the outbreak) has a clear reduction during the second quarter, Q2, as opposed to the expected increase as seen in previous years.

### Conclusion
COVID 19 pandemic has affected several economies, including Nigeria's. The country is a highly populated one with the majority of its citizens in the underprivileged category. The obvious fall in Nigeria's GDP would have affected the masses, in terms of opportunities and overall survival conditions, since this kinds of change usually affects the poor. This clearly indicates that in addition to health complications, there was also financial issues.
This could be one of the reasons why citizens were more concerned with feeding their families, regardless of the health restriction put in place by the health and government officials to reduce the spread of the coronavirus. The resulting free mixing in certain states (in addition to factors like age, socioeconomy, and transportation) could have also contributed to a high overall vulnerability index.

A clearer impact of COVID 19 on Nigeria may be visualized with a more detailed version of the GDP's data, including factors employed in computing such information.

#### * This project has added to the knowledge gotten from lesson videos. The ability to use Google to understand better the principle of some methods, as well as platforms like StackOverflow to get solutions to certain problems. t also brought to light the importance of studying and understanding the documentation of the libraries used in analysis.
