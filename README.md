# LMB_wRC

## Project Description

Saying that a double is worth more than a single, and hitting a home run is better than hitting a single is one of the most intuitive statement in baseball. But let's say that we wanted to measure HOW much is every outcome of a plate appearance worth, how would we do it? and what is the value that we are using to compare their worth? This questions are the foundations of advanced stats like wOBA, wRAA, wRC+ and oWAR, that aim to evaluate the player based on the value that contribute to run scoring of the team.

Now, in order to calculate this values, we must answer the questions previously posed. The last question is easy to answer, since baseball is a run scoring game we want to know how many runs is every event worth. But now, how can we calculate every event's value? Normaly and ideally what we would do is create an RE24 matrix, which gives us the run expectancy of every possible situation in a baseball regarding runners on the bags and the outs in the inning. After that, we would calculate how much impact each event has in changing the run expectancy value. That way we can evaluate a player and their hitting abilities based on the effect they have on the run expectancy based on their run scoring enviroment.

This is in an ideal world, however in the LMB (Liga Mexicana de Beisbol) or the mexican summer league, not all the data is available to build an RE24 matrix. So some might say that this is the end of the road then. Because we need the matrix to put on the weights of each event to then calculate this advanced stats. However, there is a way of calculating this information. According to the Buckeye and Sabermetrics we can simulate any run enviroment with the base runs formula. I'm not going to dive to deep on the calculations performed, but to sum it up, basicaly with our base run equation we can use the "+1 method" that consists of adding one to all the events individually, and see how many runs the base run equation changes. After some mathematical calculations we can determine the Linear weights of each event. This weights are then used to calculate our advanced stats. After doing this calculations considering the events of the 2024 season of LMB we get the weights of each event based on the running enviroment of the mexican summer league. For more information on this method please visit Buckeyes and Sabermetris [article](https://gosu02.tripod.com/id108.html).

Once we have this weigths we are able to calculate our first stat, wOBA. wOBA aims to provide the same level of detail that OPS provides. OPS is the sum of OBP and SLG, however OPS gives the same weight to all events and values both OBP and SLG on the same level when in reality OBP is worth al most as twice as OBP. In order to solve this, wOBA uses the weight of each event in regards to how much it contributes to a team offensive based on how many runs it is worth to give the proper value to each outcome of a plate appearance. In order to make wOBA easier to interpret we need to scale it to look like OBP. To do this we calculate the "wOBA scale" which consists in summing all the event multiplied by their weights and divide it by the sum of plate appearances, we can call this number X. After that we calculate the leagues OBP and divide it by X. Now have our wOBA scale to get the weight that are going to be used in our wOBA equation we then need to multiply every weight by the wOBA scale, then we can proceed to calculate wOBA using this weights. This process is explained in more detail in [here](https://library.fangraphs.com/the-beginners-guide-to-deriving-woba/). Here is the line of code that was used to calculate each player's wOBA:

IMAGE OF wOBA CODE

Now that we have wOBA calculated for each player in the league, we can proceed to calculate wRAA (weighted runs above average), wRC (weighted runs created) and wRC+ (weighted runs created plus). This stats are the ones that help us answer the simpler questions of baseball: How many runs is a batter worth? and if we can determine their value in runs we can determine their value in wins which is even easier to understand. First we are going to start with wRAA which give us the ammount of runs that a player makes compared to an average replacement level player. Replacement level refers to any other player that is available to the organization, for example someone on their farm system. This replacement level is considered 0 in this stat, so a player with a 3 wRAA is worth 3 runs more than a replacement level player. However, this value can also be negative, indicating that the player is worse than replacement level. wRAA is the main stat that is used when calculating offensive WAR, since we only need to divide it by the ammounts of runs per win. And as you can see in the image below, we are able to calculate wRC using almost the exact same formula with just one modification.

IMAGE OF WRC AND WRAA CODE

This two stat give us a better understanding of each offensive ability of each player. However, we are forgetting something: Some ballparks increased run scoring and some worsen it. So in order to account for this adjustments we can calculate wRC+ which give us the wRC value but taking into account the park factor of each of the home ballpark of every player and comparing it to the average wRC per plate appearance of the league. So in simplier terms, wRC+ help us compare each player on equal grounds, disregarding the home ballpark of the player. Lastly, same as OPS+ this statistic considers 100 to be the average.

IMAGE OF WRC+ CODE 

By adapting advanced metrics like wOBA, wRAA, wRC, and wRC+ to the run environment of the mexican summer league, we unlock a deeper, more accurate understanding of player performance. One that goes beyond traditional stats and adjusts for context, like park factors and league averages. Even without access to specific data like RE24, the use of base runs and linear weights allows us to create meaningful evaluations that reflect how each player truly contributes to run scoring. With these tools in hand, we not only measure what a player does, but how much it’s worth—bringing us closer to answering baseball’s most fundamental question: how much does this player help his team win?

## Leaderboards

### wOBA


### wRAA


### wRC


### wRC+
