# J124 Final Project - Matthew Rich
My Data Journalism final project, focused on California vaccination rates. This repository includes all necessary screenshots, instructions, and data visualization files for recreation of conclusions.

## Story Pitch
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; As the pandemic continues to linger globally and the long-term effectiveness of vaccines comes into question, it is worth taking a look back at the hyperpolarized issue that was vaccine efficacy/implementation. I intend to use a combination of two datasets provided by the California Secretary of State’s office to assess whether there is decisive evidence of vaccine efficacy along party lines in the state of California. These datasets are a comprehensive documentation of vaccine dose counts by county from 2020-present, and a recording of voting records by county in the 2020 election. Paired with accessible statistical tests for significance, I aim to establish whether vaccination rates are clearly divided along ideological lines regardless of what individuals may say for themselves. I will also confirm the efficacy of vaccines by pairing rate of hospitalization (from a statewide dataset) with rates of vaccination by county– a likely consequence of the seemingly correlated vaccine politicization. 

## Individuals for Interviews
* Amy Mitchell - Director of Journalism Research, Pew Research Center
  * Contact: Twitter @asmitch (no other contact info readily available)
  * Email: info@pewresearch.org (suggested email to contact staffers)
  * Reason for contact: Has engaged with considerable amounts of data relating to vaccines and political affiliations. Has also authored many related articles for Pew Research Center. As such, she would serve as a great expert source on my chosen subject matter, and can speak more specifically about vaccine politicization as it relates to California.
* California Department of Public Health (CPDH) - General Request for Comment
  * Contact: CDPHpress@cdph.ca.gov
  * Reason for contact: the CDPH played a large role in helping to compose all of the available COVID health datasets available through the California Secretary of State. As such, I would like to try to establish contact with a representative of the department to see if they have any comment on the apparent political correlation.
* Alex Messick - vox populi source
  * Contact: 760-698- 8457
  * Reason for Contact: Alex is an individual I know who had formerly not received the vaccine but later opted in favor of receiving a full dose. His opinion would serve as a humanizing voice for this article, while providing light on whether his initial decision and change of heart was personally affected by politics in any way.

## Additional Sources
* Third Dataset: COVID-19 Post-Vaccination Statewide Stats Dataset
  * Source: California Department of Public Health (CDPH)
  * https://data.ca.gov/dataset/covid-19-post-vaccination-infection-data/resource/83bd2549-63b8-4e3c-b663-80baccea9e96
  * Rationale: This data set specifically breaks down vaccinated versus unvaccinated hospitalizations over time in the state of California. It would be useful in making my final comparison of vaccination rates versus hospitalizations.
* Pew Research Article: Americans who relied most on Trump for COVID-19 news among least likely to be vaccinated.
  * Source: Pew Research Center
  * https://www.pewresearch.org/fact-tank/2021/09/23/americans-who-relied-most-on-trump-for-covid-19-news-among-least-likely-to-be-vaccinated/
  * Rationale: This article was co-authored by one of the individuals who I would intend to interview. It provides a necessary preliminary glimpse at correlation between political beliefs and position on vaccine efficacy.

## Data Analysis & Questions
### 1) What are the top five counties in terms of percentage of the population that fully vaccinated? 
  1. Acquire county population data. I found this data through a California Demographics report. Use VLOOKUP function to add county population data to vaccination data.
  2. Create a pivot table in your spreadsheet application of choice. Add county to the rows section, then County_Population and cumulative_fully_vaccinated.
  3. Upon getting these statistics into the table, create a spreadsheet formula that divides the cumulative statistic by the county population. Multiply by 100 to acquire the percentage.
  4. Copy and paste the county names alongside their percentage vaccinated as plain text. Sort by percentage. This will denote the vaccination rates by county in descending or ascending order, and provide you the answer to these questions!

**Pivot Table Example**

![Q1Pivot](https://user-images.githubusercontent.com/109619733/183390775-b4d21612-c077-45e9-a3ef-d155a02294e2.png)

**Answer (in %):**

![Q1Answer](https://user-images.githubusercontent.com/109619733/183390895-29dba36c-4514-4514-83c1-334006490bfe.png)

### 2) What is the worst county in terms of the percentage of the population that is fully vaccinated? Is there any offhand intuition as to why this might be the case (e.g. rural county, healthcare accessibility, etc.)?
  1. You can essentially use the same methodology as the previous question, but reverse the sort function or analyze the opposite end of the list.
  
  **Answer:** Lassen County, sitting at 29.4% fully vaccinated. Being that this county is more rural with a population of only just over 30,000, it is plausible that its remote nature plays a part in the low rate of county vaccinations.
  
### 3) What counties (top 5) were the most concentrated in terms of right-leaning voters? (as percent of total county voters.)
  1. Acquire data set on voter statistics in the 2020 election. I secured mine from the California Secretary of State webpage on election statistics.
  2. Clean dataset by simplifying the “Party Name” variable to a political ideology identifier. I used Find & Replace to simplify all included parties as either “Left” leaning or “Right” leaning. Independent parties/candidates with no affiliated parties are left out since they only represent a very small portion of total vote allocations.
  3. Add a variable titled “total_registered_voters” to the table. Using another datasheet from the CA Secretary of State, acquire the number of total registered voters by county for the 2020 election. NOTE: There may be a simpler document available, but I had to copy this data by hand from a PDF.
  4. Use VLOOKUP function to stitch the new variable values into the original sheet.
  5. In a new pivot table, add a filter for party ideology that only allows values stemming from “Right” leaning parties.
  6. Add county name to the Rows section. Add Vote Total and total_registered_voters to the values section. Sort by sum of vote total.
  7. Divide SUM of Vote Total by MAX of total_registered_voters. Multiply by 100 for percentage. Copy paste as plain text alongside county names, then sort by greatest to least. 
  
**Pivot Table Example**

![Q3Pivot](https://user-images.githubusercontent.com/109619733/183392011-a36f9b9d-45ae-4050-815d-dc7abf5e2c17.png)

**Answer (in %):**

![Q3Answer](https://user-images.githubusercontent.com/109619733/183391913-8cdfdd68-3f75-47b4-b0c8-b37a09e75179.png)

### 4) What counties (top 5) were the most concentrated in terms of left-leaning voters? (as a percent of total county voters.)

  1. Again, you can follow the same procedure outlined for the previous question. This time, however, flip your sorting methodology or look to the opposite end of the pivot table.
  
**Pivot Table Example**

![Q4Pivot](https://user-images.githubusercontent.com/109619733/183392487-43d7e317-a1ef-4bd2-ae81-ddf34e110aea.png)

**Answer (in %):**

![Q4Answer](https://user-images.githubusercontent.com/109619733/183392552-ce264926-d16a-48b2-abd6-dd1b6eddf155.png)

### 5) Do you see any overlap in terms of a county’s overarching political preference and vaccination rate? Limit your analysis to the counties assessed in prior questions.

**Answer:**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Without running any definitive statistical tests for significance, we can still easily assess some correlation between the answers to the above questions. For instance, Marin ranks as the county with the second highest full vaccination rate in CA while also having been the county that most predominantly voted for Left-leaning candidates in the 2020 election.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Additionally, Lassen County sits on the exact opposite side of this spectrum. It retains the lowest vaccination rate for any CA county and was the most supportive of right-leaning candidates (by percent of population) during the 2020 election. While we definitely cannot claim causation, we can at least recognize some semblance of correlation between the two variables (political preference and rate of vaccination).

## Data Visualization

<img src="https://user-images.githubusercontent.com/109619733/183393283-f39eee03-c41b-483d-a98e-73200948d8d3.png" width="550" height="670">

<p float="left">
<img src="https://user-images.githubusercontent.com/109619733/183393300-68944a78-875a-43c1-b100-a3f941aac4ae.png" width="400" height="520">

<img src="https://user-images.githubusercontent.com/109619733/183393309-5adf544c-334e-47a2-b3db-55262530e76b.png" width="400" height="520">
</p>

**Links to Original Visualizations in DataWrapper:**

* https://www.datawrapper.de/_/kcmTk/
* https://www.datawrapper.de/_/yonsI/
* https://www.datawrapper.de/_/uZu7A/
