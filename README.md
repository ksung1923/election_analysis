# Election Analysis 

## Overview of Election Audit
A Colorado Board of Elections employee, Tom, has given me the following tasks to complete the election audit of a recent local congressional election. 

1. Calculate the total number of votes cast.
2. Get a complete list of county and candidates who received votes.
3. Calculate the total number of votes each candidate received and each county received. 
4. Calculate the percentage of votes each candidate won and each county won.
5. Determine the winner of the election based on popular vote.
6. Determine the largest county turnout based on popular vote.

## Resources
-Data Source: [election_results.csv](Resources/election_results.csv)

-Software: 
  1. Python 3.6.1
  2. Visual Studio Code, 1.38.1

## Election Audit Results
The analysis of the election show that: 
- There were 369,711 votes cast in the election. 

- The candidates were: 
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane

- The candidate results were: 
  - Charles Casper Stockham received 23.0% of the votes and 85,213 number of votes. 
  - Diana DeGette received 73.8% of the votes and 272,892 number of votes.  
  - Raymon Anthony Doane received 3.1% of the votes and 11,606 number of votes.  

- The winner of the election was: 
  - Diana DeGette, who received 73.8% of the votes and 272,892 number of votes.  

- The counties were: 
  - Jefferson
  - Denver
  - Arapahoe

- The county results were: 
  - Jefferson received 10.5% of the votes and 38,855 number of votes. 
  - Denver received 82.8% of the votes and 306,055 number of votes.  
  - Arapahoe received 6.7% of the votes and 24,801 number of votes.  

- The largest county turnout was: 
  - Denver, which received 82.8% of the votes and 306,055 number of votes.  

Please see [election_analysis.txt](analysis/election_analysis.txt) for the fully Election Audit Report.

## Election Audit Summary
The election audit script has been written in a way that it can easily be used for future congressional election audits as well as senatorial election audits or any local election audits. If the data for senatorial elections provides a “Ballot ID”, “County”, and “Candidate” information, we should easily be able to import other election data into this script in the future. The portion of the script that would be modified for any other elections is: 


```

# Add a variable to load a file from a path.
file_to_load = os.path.join("Resources", "election_results.csv")
# Add a variable to save the file to a path.
file_to_save = os.path.join("analysis", "election_analysis.txt")

```

A second modification to the script so it can be used for other elections would be updating how I got the candidate and county name. In my current script it is a hard-coded index. A modification could be doing a name search in the headers for the words “County” and “Candidate”. Data from other elections may not come in the exact format as our current congressional data. The portion of the script that can be modified to be used for other elections is: 

```
# Get the candidate name from each row.
candidate_name = row[2]

# 3: Extract the county name from each row.
county_name = row[1]

```

Lastly, the congressional election data did not provide any indication of how the vote was casted. There are three voting methods that were taken into an account: 

1.	Mail-In Ballot, which was hand counted
2.	Punch Cards, which was machine counted
3.	Direct Recoding Electronic, which was computer counted

If future election data provides information on how the vote was casted, a future modification to the script could be providing analysis on the most popular method of voting in certain counties. This analysis could be helpful when deciding how to allocate resources before the election. 




