# Pewlett Hackard Analysis
HR Data Analysis

### Purpose
Pwelett Hackard is a large tech company that wants to make sure it is ready to tackle whatever the future may bring. The HR department recently decided to migrate all of their data from simple Excel files into the SQL database. While assisting in this move, I noticed that there are a very large number of employees near retirement age. I brought this up to the HR manager, and was tasked with diving deep into this data to determine if there is any way to prevent a sudden and massive loss of expertise if all retirement eligable employees retire at the same time. 

### Results
After sifting through the data, I determined the best way to break this down for HR would be to first pull all of the current employees who are of retirement age, then make sure there are no duplicates, and then to count up how many of each title will be retireing soon. 

* There are a massive number of retirement aged employees, but my initial pull used the database of all titles ever held by an employee, so there are several duplicate employee numbers. This happened every time an employee had a title change. Below is the top snip of the table from my first query.

![Retirement by Titles](https://github.com/caseykotowski/Pewlett-Hackard-Analysis/blob/main/retirement-titles.png)

* But once I had this data, I was able to write a new query to find just the unique employee numbers:

![Unique Retirements by Title](https://github.com/caseykotowski/Pewlett-Hackard-Analysis/blob/main/unique-titles.png)

* And I added a simple count of how many people with each title currently could retire soon. I am very concerned that so many senior engineers could be retiring soon. As that is a highly technical position, there is a great chance of knowledge loss between the Senior and Junior engineers. 

![Count of Titles Retiring](https://github.com/caseykotowski/Pewlett-Hackard-Analysis/blob/main/retiring-titles.png)

* When this data was presented to HR, they wanted to combat the loss of expertise, so they came up with a plan to add in a mentorship program. Those nearing retirement age can be paired with recent hires to make the transitions smoothe. By merging tables, I filtered the retirees for the youngest eligable for retirement. The thought here is that they have the potential to stay in the mentorship program the longest. Below is a snip from the top of the mentor list:

![Mentorship Eligibility](https://github.com/caseykotowski/Pewlett-Hackard-Analysis/blob/main/mentorship_eligibility.csv)

### Summary

90,398 people are eligible to retire. There are only about 1,500 people eligable to join the mentorship program with the current birthday restrictions. Over the 4 years, Pewlett-Hackard will have to either increase the workload of tens of thousand employees, or they will have to hire 90,000 new people. 

The 1,550 employees eligible to mentor will not be enough to handle the need, unless each mentor can take on up to 10 mentees each. I recommend expanding this program to include anyone within 10 years of retirement. It does not have to be all encompassing, and not everyone would have to participate, but I think that would be a more effective way to ensure business continuity. 

To dig a little deeper, I would want to querey the youngest/newest employees at the company. Which departments are they in? Has PH been hiring in right departments? Another query to run would be to find the proportions of retiring employees compared to mid and early career employees. If HR has the data, I think adding in averag time of service would be useful. You can hire 100,000 new employees, but if the average early career employee only stays a short number of years, then PH could stay under staffed. Regardless, Pwelett Hackard's HR department has a lot of recruiting to do!
