# Board Game Ranking Analysis

## Overview
Using the boardgamegeek data found on kaggle, I hvae used machine learning models to identify the most successful mechanics in published games. 

## Resources
- Data Sources: games_detailed_info.csv
- Software/Tools: Jupyter Lab(pandas)
- Languages: Python 3

## Results
### Labelling
The first task was to appropritately label the data. I chose to use a rating of 6.5/10 to be the cut off for good vs. bad games. This was chosen to ensure there was a large enough set of 'good' games without needing to employ under/over sampling for the machine learning process. 

### Transformations
I chose to limit the input columns to strictly the board game mechanic, ignoring other contributors such as, year published, designer, artist, etc. The board game mechanic was one hot encoded into 53 columsn, each representing a unique board game mechanism. Finally, for the machine learning process, the 'good' an d'bad' games were split into two spereate tables.

### Models
Two models were used: a neural network and logistic regression. The neural network is expected to yield the best results but opacity is a side-effect. Hopes are that this project will help identify which mechanisms are popular, so this is less than ideal. It does however give us a black box to plug in combinations of mechanisms after the model has run. For some clarity, the logistic regression model has the upper hand. After running the model one can output the relative weights for each mehanism when deciding which category it belongs to, good or bad. 

### Results
The neural network had an accuracy rating exceeding 90% and a loss of 0.26, suggesting it did a reasonably good job at identifying what games are rated highly. This can now be used to try out new combinations before getting deep into a design process. 

The logistic regression only showed an accuracy score of 50%. From the confusion matrix one can see it had trouble putting many games into the 'good' games category, with only 3 true positives. Clealry this is an area that can be improved though the weights of the mechanisms are interesing to examin none the less. 

One can see the top of the list is highlighted by mechanisms such as card drafting, hand management, worker placement, and variable player powers: suggested strategic card and euro games are the current favourites for gamers. The bottom of the list is popuated by chit-pull system with hex-and-counter, also take-that, memory and rock-paper-scissors; suggesting older war games and simple mass market games are not for the masses. Despite a 50% accuracy rating it seems the logistic regression has  good handle on the current trends in board gaming but confused with the other mechanisms that may appear in both good and bad games.
