# Soccer-Data-Analysis


In the world of sports, it is always difficult to predict the outcome of a match. This is more evident
in an unpredictable sport like soccer where its nearly impossible to predict the outcome of a match
even after the available data like team configuration, player attributes and other such features.Being
soccer enthusiasts, we would like leverage the learning methods of
Machine Learning for an in-depth analysis of European Soccer data.


Data set- https://www.kaggle.com/hugomathien/soccer.


# Challenges and Methodologies

The functional application of this research question is to help managers find a better player for a bargain during a transfer window.

Our initial approach was to segregate players based on their playing positions. So, we wanted cluster players into Goal Keepers, Defenders, Defensive Mid-fielders, Attacking mid-fielders, and strikers. 

But we faced a couple of issues with this approach. 
1)	Our dataset did not have the playing positions of all the players who were involved during these seasons. 
2)	We just had the playing coordinates of each player, so we were trying to infer the playing positions based on these co-ordinates. But this approach was intractable as well, as with change in time, a player can serve the same purpose in a different co-ordinate. So it was hard to capture the temporal change in positions.

So, we realized that we’re approaching the question in a wrong.

Since, our problem was to find a better player for a bargain, we decided to find groups of similar players, and then analyze the attributes between the players in each group that would lead to a bargain.  

So, we resorted to using an unsupervised clustering algorithm called k-means clustering.
The K-Means clustering algorithm groups data into clusters based on Eucledian distances between data points. So, we decided to use the following Player attributes as parameters for clustering -

*	Height
*	Weight
*	overall_rating
*	potential
*	crossing
*	finishing
*	heading_accuracy
*	short_passing
*	volleys
*	dribbling
*	curve
*	free_kick_accuracy
*	long_passing
*	ball_control
*	acceleration
*	sprint_speed
*	agility
*	reactions
*	balance

Now the next issue was to choose the value of k. Since, we initially wanted to cluster players based on their playing positions we chose a value of 5. The algorithm clustered data points into five clusters and as we suspected a major portion of the players in each group had the same playing positions. For example- 
1)	 Lionel Messi, and Cristiano Ronaldo were in the same group.
2)	Also, David Da Gea, and Jan Oblak were clustered in the same group.

To compare our results, we tested the results for different values of k. (The elbow method). And as can be seen in the graph, the error or dispersion function elbows at k=4/5.

To compare our results, we also observed the data points in two dimensions. 

We could have also used PCA to use visualize the data points, but the variance captured in the two principal components of this dataset was too low to be representative of the entire dataset.

The results were not bad, so we decided to explore the monetary aspects of players in each of these groups. 

But we did not have data of valuations of these players. So, we decided to scrap data from the source of this dataset, sofifa.com. We then got the value, wage, and release contract value of each of these players.

For analyzing the monetary aspects, we choose the top twenty players in each group. 
Now, among the top twenty players in the group dominated by goalkeepers, we have successfully observed that between the highest and second highest rated goalkeeper there’s a huge gap in value.








