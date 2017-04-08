## Air Cargo Planning Search Analysis


| Search Algorithm | air\_cargo\_p1 | air\_cargo\_p2 | air\_cargo\_p3 |
| ------| ------ | ------ | ------|
| depth\_first\_graph\_search | N:21, G:22,<br>T:0.02s, O:False  | N:624, G:625<br>T:4.48s, O:False | N:408, G:409<br>T:2.21s, O:False |
| depth\_first\_graph\_search<br> with\_limit\_15 | N:234, G:939,<br>T:0.486s, O:False | N:24208, G:222729,<br>T:171.42s, O:False | cannot find answer within 10 min |
| breadth\_first\_search | N:43, G:56,<br>T:0.04s, O:True | N:3343, G:4609,<br>T:17.35s, O:True | N:14663, G:18098,<br>T:129.49s, O:True
| a\_star\_search\_ignore\_preconditions | N:41, G:43,<br>T:0.03s, O:True | N:1506, G:1508,<br>T:15.62s, O:True | N:5118, G:5120,<br>T:114.56, O:True |
| a\_star\_search\_level\_sum | N:8, G:10,<br>T:1.33s, O:True | N:13, G:15,<br>T:34.24s, O:True | N:23, G:25,<br>T:87.69, O:True |

Table 1. Performance of different search algorithms on solving air cargo planning problems. N stands for node expansions, G for number of goal test, T for time elapsed, and O for optimality in each cell.

* Strategy for choosing the optimal search plan is first based on whether the search plan can find the optimal solution. Any extra action can cause at least hours of time and huge money in real world air cargo problems. So, optimality is primarily considered. For all search methods that provide the optimal solution, the strategy picks the fastest one. According to Table 1, the optimal search plan for problem 1 and 2 would be a-star-search with ignore-prediction heuristic, while a-star-search with level-sum heuristic would be the optimal choice for problem 3 in heuristic method. For non-heuristic method, breadth first search is the best choice.

* For non-heuristic search method, depth-first-graph-search can find an answer really quickly but the answer is not even close to optimal. It provides an answer with hundreds of actions for problem 2 and 3, which cannot be used in real air cargo situation. Depth-first-search also expand much less node. Depth-first-search-with-limited-depth still cannot find an optimal answer, but it can restrict its actions number within certain value. Only breadth-first-search can find an optimal answer and within reasonable time. So, breadth-first-search would be the best choice among all the non-heuristic search methods.

* Level-sum heuristic with planning graph is really powerful. The expanded search node is much less than all the other search methods. But it also requires some extra time to build the planning graph. For easy problems, ignore-preconditions-heuristic is a better choice because it does not need to build the planning graph. When problem get harder, level-sum-heuristic outperforms the ignore-preconditions-heuristic for much-less-expanded nodes. 

* A-star-search with ignore-preconditions heuristic outperforms breadth-first-search in all 3 problems because the extra computational time for the heuristic value is really small, but it can spare large amount of nodes from expanding in problem 2 and 3.






