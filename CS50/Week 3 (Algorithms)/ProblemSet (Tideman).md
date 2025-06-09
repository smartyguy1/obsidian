The goal is to complete the program that calculates the winner of an election using the Tideman method. 

# Tideman Method

The voting will be undertaken using the ranking method, where candidates are given more than one choice and will vote by assigning a ranking or preference order to each candidate(1 to the most preferred and n to the least one). 
Now we write the name of each candidate and compare them 1v1 based on ranking, then we draw an arrow with its tail on the winner(more preferred of the two(eg: 7out of  9 prefer this candidate more than the other.)) and the head on the loser. The order of drawing the arrows should be based on the strength of the victory in each comparison(eg: 7-2 must be drawn first and then 6-3). If on drawing the last arrow, the graph ends up becoming a cycle, we don't draw it. Now the candidate that looks like the source of the graph is the winner.

# Distribution Code
In the distribution code the preferences\[i]\[j] array will store the no. of candidates that prefer candidate\[i] more than candidate\[j]. 
The Bool lock will store true or false \[i] wins over \[j]. 
The new data structure pair will store the winner and loser of each pair.
The Ranks[] will store the preference order of each voter