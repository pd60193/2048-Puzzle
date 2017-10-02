{\rtf1\ansi\ansicpg1252\cocoartf1265\cocoasubrtf210
{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
\margl1440\margr1440\vieww8160\viewh12900\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural

\f0\fs24 \cf0 The ComputerAI.py and PlayerAI.py programs implement the minimax algorithm with alpha-beta pruning to automate the game 2048 on a 4x4 grid. Depth limited search has been applied.\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 \ul \ulc0 Player AI:\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 \ulnone Here max is played by the PlayerAI who\'92s goal is to maximize the score. Min is played by the ComputerAI who\'92s goal is to minimize the score.\
\
For Max\'92s turn, we check for all available moves - up, down, left, right and for each of the available moves check what min\'92s response would be and so on. The evalfn is triggered when either a leaf node is reached or depth = 0.\
At this point the utility factor is calculated based on the defined Heuristics.\
\
Heuristic: Three criteria have been taken into consideration while calculating the heuristic with optimal weights (tested empirically) -\
1. Number of empty cells\
2. Sum of top four max tiles in the grid at that point\
3. Weighted distance of each cell from the bottom left corner.\
\
If there is any branch who\'92s utility value is such that beta is less than or equal to alpha, we will not explore those branches i.e. those branches will be pruned as min will select a move with at least that utility, and max in it\'92s turn will definitely not select that move as it has better alternative moves.\
\
Thus, based on the utility values generated, the Player chooses the moves that will maximize it\'92s potential score. As the recursive function unfolds, this move will be selected for the PlayerAI.\
\
Alternately for Min\'92s turn, the ComputerAI\'92s move will be selected.\
\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 \ul Computer AI:\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 \ulnone Here max is played by the ComputerAI who\'92s goal is to minimize the score. Min is played by the PlayerAI who\'92s goal is to maximize the score.\
\
For Min\'92s turn, we check for all available cells that can be populated with either a 2 (90% probability) or a 4 (10% probability). We then check what Min\'92s response would be to that cell and so on and so forth till we reach a leaf node or a depth = 0.\
At this point the utility factor is calculated based on the defined Heuristics.\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 Heuristic: Three criteria have been taken into consideration while calculating the heuristic with optimal weights (tested empirically) -\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural
\cf0 1. Number of populated cells\
2. Sum of top four min and max tiles in the grid at that point\
3. Weighted distance of each cell from the bottom left corner.\
\
If there is any branch who\'92s utility value is such that beta is less than or equal to alpha, we will not explore those branches i.e. those branches will be pruned as min will select a move with at least that utility, and max in it\'92s turn will definitely not select that move as it has better alternative moves.\
\
Thus, based on the utility values generated, the Player chooses the moves that will minimize it\'92s potential score. As the recursive function unfolds, this move will be selected for the ComputerAI.\
\
Alternately for Min\'92s turn, the PlayerAI\'92s move will be selected.\
\
\
\
\
\
}
