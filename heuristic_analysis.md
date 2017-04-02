## Heuristic Evaluation Function Analysis


| Search Algorithm | air\_cargo\_p1 | air\_cargo\_p2 | air\_cargo\_p3 |
| ------| ------ | ------ | ------|
| depth\_first\_graph\_search | N:21, G:22,<br>T:0.02s, O:False  | N:624, G:625<br>T:4.48s, O:False | N:408, G:409<br>T:2.21s, O:False |
| breadth\_first\_search | N:43, G:56,<br>T:0.04s, O:True | N:3343, G:4609,<br>T:17.35s, O:True | N:14663, G:18098,<br>T:129.49s, O:True
| uniform\_cost\_search| N:55, G:57,<br>T:0.06s, O:True | N:4853, G:4855,<br>T:75.23s, O:True | N:18223, G:18225,<br>T:809.35, O:True |

Table 1. Performance of different search algorithms on solving air cargo planning problems. N stands for node expansions, G for number of goal test, T for time elapsed, and O for optimality in each cell.





![Custom Score Win Ratio Histogram](./custom_score_win_ratio_hist.png)
*Custom Score Win Ratio Histogram*



