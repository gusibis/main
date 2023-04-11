# main_project_1
Module 7, project 1
David Calero,
Tyler Allen, 
Gustavo Bustillos

Use Pandas to clean and format your dataset or datasets. 
Create a Jupyter notebook describing the data exploration and cleanup process.
Create a Jupyter notebook illustrating the final data analysis.
Use Matplotlib to create 6 to 8 visualizations of your data 
(ideally, at least 2 visualizations per “question” that you ask your data).
Save PNG images of your visualizations to distribute to the class and instructional team—and for 
inclusion in your presentation.
Create a write-up summarizing your major findings. This should include a heading for each “question” 
that you asked your data as well as a short description of your findings and any relevant plots.
Bonus Use at least one API—if you can find one with data pertinent to your primary research questions.


Data collection and analysis
- 30 Year Fixed Rate Mortgage Average from https://api.stlouisfed.org/fred/series/observations?
- Average Hourly Earnings of All Employees from https://api.stlouisfed.org/fred/series/observations?
- Unemployment rate. Data obtained from https://fred.stlouisfed.org
- Single Family Home value average (ZSFH) from Zillow
- Consumer Price Index for All Urban Consumers. Data source https://fred.stlouisfed.org


Data set used independently in our analysis. Could not perform a data regression with it due to the set returned in quarters instead of monthly.  
- Gross domestic product from https://fred.stlouisfed.org 


Three of the datasets were obtained via API
The other 3 were obtained using the library 
Nasdaq-Data-Link
That simplified the collection by eliminating the need of adding, headers or other parameters. The API key was still required. 

From 2010 to 2019, the US unemployment rate went through a period of significant change. The US was recovering from the 2008 financial crisis, which had led to high levels of unemployment, and the policies implemented in response to the crisis impacted the unemployment rate over the years that followed. In 2010, the unemployment rate was between 9%-10%, which was a high level that reflected the impact the financial crisis on the job market. Over the years, the unemployment rate gradually decreased as the economy recovered. By 2019, the unemployment rate dropped below 4%.
AVERAGE HOURLY EARNINGS 2010-2019
From 2010 to 2019, the US average hourly earnings also experienced significant changes. In 2010, the average hourly earnings in the US were at about $20, and by 2019, they had increased to $28.29. This is about a 40% increase. This increase represents a significant improvement in the earning potential of US workers over this period.  The increase in average hourly earnings over this period reflects a trend towards higher wages in the US economy, which could have positive impacts on economic growth.
AVERAGE HOURLY EARNINGS 2010-2021
There are several reasons why there was a spike in average hourly earnings during the pandemic.
One of the main reasons is that the pandemic led to widespread job losses, with many low-wage jobs being eliminated and high-paid workers remaining employed. This could have created what’s called a composition effect.  The median wage spiked due to low-wage jobs being eliminated and high-paid jobs remaining intact. Additionally, many workers who were able to continue working during the pandemic were in essential industries such as healthcare, grocery stores, and delivery services, and these industries started paying higher wages to attract workers during a time of increased demand. This spike was momentary because it leveled out in the 3rd quarter.
Sources:
https://www.pewresearch.org/fact-tank/2021/12/22/many-u-s-workers-are-seeing-bigger-paychecks-in-pandemic-era-but-gains-arent-spread-evenly/
https://www.pewresearch.org/fact-tank/2021/09/07/despite-the-pandemic-wage-growth-held-firm-for-most-u-s-workers-with-little-effect-on-inequality/
https://www.whitehouse.gov/cea/written-materials/2021/04/19/the-pandemics-effect-on-measured-wage-growth/
30-Year fixed mortgage
From 2010 to 2019, the 30-year fixed mortgage interest rate in the US experienced a general trend of decline. In 2010, the average interest rate for a 30-year fixed mortgage was around 5%, while by 2019, the average rate had dropped to 3.1%.
Additionally, low inflation and low unemployment rates also helped to keep mortgage rates low by reducing upward pressure on interest rates.
https://www.moneygeek.com/mortgage/analysis/historical-mortgage-interest-rates/#:~:text=2010s,Great%20Financial%20Crisis%20of%202008.&text=The%20decrease%20in%20mortgage%20rates,the%20Great%20Recession%20in%202008.
Pew Research CenterPew Research Center
Many U.S. workers are seeing bigger paychecks in pandemic era, but gains aren’t spread evenly
American workers in some sectors and industries are seeing far smaller wage gains than those in others.
Est. reading time
6 minutes
Written by
Drew DeSilver
https://www.pewresearch.org/fact-tank/2021/12/22/many-u-s-workers-are-seeing-bigger-paychecks-in-pandemic-era-but-gains-arent-spread-evenly/

Pew Research CenterPew Research Center
Despite the pandemic, wage growth held firm for most U.S. workers, with little effect on inequality
Earnings overall have held steady through the pandemic in part because lower-wage workers experienced steeper job losses.
Est. reading time
11 minutes
Written by
Rakesh Kochhar and Jesse Bennett
https://www.pewresearch.org/fact-tank/2021/09/07/despite-the-pandemic-wage-growth-held-firm-for-most-u-s-workers-with-little-effect-on-inequality/

The White HouseThe White House
The Pandemic’s Effect on Measured Wage Growth | CEA | The White House
By Chair Cecilia Rouse and Martha Gimbel Usually when we see rising wages, the economy is growing. So how is it that April 2020 – the month when the U.S. economy lost 21 million jobs – saw some of the fastest wage growth in recent memory? And if wage growth slows in the coming months,…


API keys obtained from: 
https://fred.stlouisfed.org/docs/api/fred/ 
https://www.bls.gov/developers/home.htm 
https://data.nasdaq.com/api/v3/datatables/
https://api.stlouisfed.org/fred/series/observations?


Cleaning and preparing the data.
We had to rename the 'Date' columns to match proper capitalization. 
We had to remove the 'Unamend' column after saving and opening the CSV file, Pandas was creating this new index column.
Also to make sure the data was correct from opening the CSV file we had to reset the index. 
We also had to invert the x-axis for some of the plots so they were correct
For better presentation we removed the day from the date and left the Year and the Month. 
Unsuccessfully to convert some of the datasets to quarterly to create a linear regression plot. 
For better presentation used the plt.MaxNLocator() function to set a maximum number of tickers for the x axis that displays the years. 
Created a function generate the linear regression plots that takes the 2 data frames, the Y and X axis labels as arguments.  
Had to revert some data so the plot went from left to right, older to newer date. 



Questions:
Does the price index of a basket of goods and services paid by urban consumers affect the unemployment rate, how? 
The linear regression plot showed the relationship was strong and negative, even with the disruption of 2020 it was evident, the P value was very small and the R value including 2020 was 0.55504
Excluding 2020, it was -0.9565, a strong negative relationship

Does the price index of a basket of goods and services paid by urban consumers affect the single family home value?
The P value was too small, the R value of 0.9209, plus the consistency in the plot shows there is a strong positive relationship. 


Does the price index of a basket of goods and services paid by urban consumers affect the hourly earnings of all employees? 
The p-value was too small like the other 2 previous evaluations, so the R value is the one to be used, with 0.9808, very close only about 2 percent variation in the sample obtained until 2019 
We can say there is strong evidence of a positive relationship. 

Does the price index of a basket of goods and services paid by urban consumers affect the 30 year fixed mortgage interest rate? 
The relationship was not as strong, although the P value was small and the R value (Standard deviation) was -.2478, close to zero the plot showed too much variation. 
Values were too scattered so we considered these 2 datasets had the list relationship 

The disruption in the economy that occurred in 2020 was stabilized in about 1.5 year, It increased the unemployment by over 10%, GDP dropped over 3 billion dollars, the hourly wages increased by about 2 dollars.
Average Single family home prices increased by about 20 thousand dollars in average and kept going up well after 2020, so we are not sure if it really made an impact 
The 30 year fixed interest rate could not be related to the 2020 disruption.

Does the price index of a basket of goods and services paid by urban consumers affect the unemployment rate? 
The year 2020 shows a spike in unenployment rate but even with the spike the realtionship is evident. 


Does the price index of a basket of goods and services paid by urban consumers affect the single-family home value ? 
There is a definite strong relationship between the Single family value and the Consumer price index. 


Does the price index of a basket of goods and services paid by urban consumers affect the hourly earnings of all employees? 
Even with the disruption produced by the pandemic the relationship was very strong with an R value of over -0.98, very close to 1 


Does the price index of a basket of goods and services paid by urban consumers affect the 30-year fixed mortgage interest rate? 
We concluded that the relatioinship between these was not evident, the fixed rate was all over the place in relation to cosumer prices. The P value was too small to be relevant and the R value was very small -0.6 with including the pandemic and 0.24 without including the pandemic year 2020


The Consumer Price Index is a powerful data set for the relationships of Unemployment, Hourly wage, and Home values

The interest rates of 30-year mortgages prove to be unaffected

With these insights we can see where certain market trends may be heading





