# Overview of the Election Audit
The purpose of this election audit is to tally up all the votes by county and by candidate, to find out which counties had the most votes cast as well as which candidate has won the election.  Votes are supplied in *.csv* format, and a simple Python [script](PyPoll_Challenge.py) will be able to read in the data, perform the calculations and output the final results both in real time to the console as well to a text file.

# Election Audit Results
- The total turnout for all counties was **369,711** votes
- The counties cast, in descending order of total votes (winners in ***bold***):
  - **306,055** votes, *82.8%*, ***Denver County***
  - **38,855** votes, *10.5%*, Jefferson County
  - **24,801** votes, *6.7%*, Arapahoe County
- The candidates received, in descending order of total votes:
  - **272,872** votes, *73.8%*, ***Diana DeGette***
  - **85,213** votes, *23.0%*, Charles Casper Stockham
  - **11,606** votes, *3.1%*, Raymon Anthony Doane

## Final Results Output

You can find the text file output for this analysis [here](/analysis/election_analysis.txt).

Here is what the final results would look like, outputted to the console:
![Final results of election, outputted to console.](/analysis/election_analysis_console.png)

# Election Audit Summary
Currently, this script is already setup to audit any election, with any number of counties and candidates, that follows the same *.csv* format.  However, there are some potential improvements that could be made.
## Robustness and Flexibility
- Currently, the script has the name of the election input and output files hard-coded.  Instead, creating a main(argv) function and giving the option to pass the input file path as an argument could make the code easier to run on different files, should there be multiple elections.
- The output file could be named based on the input file, assuming that the data is better named than "election_results.csv" - perhaps "senate_election_2022_results.csv".
- Additional columns in the *.csv* file won't actually affect the functionality of the current code, as long as the county remains at the second index and the candidate remains at the third index.  However, using the names in the header to determine which column is which, rather than just indices '1' or '2,' could be a handy way of determining flexibility, in case the column order or numbering of the *.csv* changes in the future.

## Additional Features
- Automatically sorting the counties and candidates by descending numbers of votes in the results would be a sensible adjustment to make, rather than simply by the order in the *.csv* file.
- If additional columns were added, we could also tally votes by individual town, whether the vote was cast in person or via mail-in ballot, etc.
- Additional statistics could be performed as well, calculating the performance of candidates in particular counties and outputting those in a table.
