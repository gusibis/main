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

