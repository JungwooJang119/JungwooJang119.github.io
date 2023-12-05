# CALCULATING THE MOST DANGEROUS EPL GAME
## Project Group 30
### Emily Ngoc-Chau Nguyen Astillero, Avery Greer, Erica Izaguirre, Jungwoo Jang, Chae Hyun Kim
Introduction  
Among the many professional leagues of association football or soccer, the English Premier League (EPL) stands as the most valuable and popular of them all [2]. The literature in this field also states that the EPL is known to be one of the most dangerous leagues in the world, boasting a considerable number of injuries sustained within a season [1][3]. We seek to determine the most aggressive team possible (excluding a goalie), predicted using data on tackles and fouls per player from all seasons played by the league. This is because a tackle's purpose is defined as an attempt by the defensive team to steal the ball from the offensive team without creating a foul. Thus, an unsuccessful tackle signals that the player failed to steal the ball or received a foul from a referee. This aggressive team would create the most opportunities for injuries to occur since “tackles deemed as fouls are reportedly responsible for 21–69% of tackle-related injuries” [4].

Problem Definition  
As the most popular and richest soccer league, the EPL is known for its aggressive playstyle with its high level of tackles and corresponding fouls [4]. The dataset chosen includes full player statistics from 1993 to 2020; however, we will focus on the number of tackles attempted, the number of unsuccessful tackles and the number of fouls per player. The goal of this project is to determine a team of the most aggressive players.

Methods  
We will use linear regression to determine the relationship between unsuccessful tackle percentage and the number of fouls. Our input will be the percentage of unsuccessful tackles per player and our output will be the number of fouls each player obtained. Our linear regression model will be run 3 times total, once for each position we want to fill: defender, midfielder, and forward. We will not be choosing a goalie since goalies should not be tackling during games. 
We will utilize linear regularization techniques such as LASSO regression as it will help us improve the performance of our linear regression model by finding a balance between model simplicity and accuracy. The regression will help us avoid overfitting, increase model interpretation, select a subset of appropriate variables, and improve prediction accuracy.

Dataset  
We searched for sets that included data on a player basis and contained the total number of tackles, a metric for successful/unsuccessful tackles, the number of fouls, and player position. The All Time Premier League Player Statistics dataset (https://www.kaggle.com/datasets/rishikeshkanabar/premier-league-player-statistics-updated-daily) presents this information, which we can utilize to create a team with higher number of tackles and fouls and lead to the most chances for injury to occur. All players that were/are a part of the 20 teams in the league are listed in the dataset; this leads to a total of 571 unique football players and their statistics from each match played.

Model 1: Defenders

Linear Regression Initial Setup

We cleaned our dataset within Kaggle. Using the notebook feature, we were able to use pandas and its drop() method to remove all unnecessary columns/features such as club, appearances, total number of shots, and other metrics that we do not need for our analysis. Since we are choosing players by position and excluding goalies, we also removed all goalies using the drop() method. Finally, we split the composite dataset into three datasets based on player position: defender, forward, midfielder. This filtering was done using pandas DataFrame loc method. Our end result is 3 datasets that we saved as CSV files.

![Screenshot (606)](https://github.com/JungwooJang119/JungwooJang119.github.io/assets/113401325/413635d3-6f2d-4911-a921-ba7bc42a7fe2)

We preprocessed our data by using the “tackles success %” column to approximate the number of failed tackles by multiplying the percentage of successful tackles with the total tackles, and then subtracting the result from the total number of tackles. For our first model we focus on the defenders dataset.

![Screenshot (607)](https://github.com/JungwooJang119/JungwooJang119.github.io/assets/113401325/48b33cde-0f4d-44ca-ab42-6199d6fa4d7b)


We then used scikit-learn’s LinearRegression class to create the linear regression model, randomly selecting 80% of the data as training data and testing on the remaining 20%.  We then plotted the data points and the regression line using matplotlib. We then calculated the difference between actual fouls and predicted fouls (including negative differences), appended that difference as a column in the dataset, sorted the dataframe by this new “Difference” column in descending order, and picked the top four entries with the maximum difference values.


Linear Regression Results

A majority of our models calculate regression lines for each soccer team position based on the number of unsuccessful tackles and fouls each player is given. As aforementioned, tackles are attempts from defensive players to steal the ball from an offensive player without receiving a foul by the referee. So, we are coding linear regression models to first determine if there is a correlation between the number of fouls and unsuccessful tackles for each player. This is due to an unsuccessful tackle being classified as either the defensive player failing to steal the ball or receiving a foul. We want to make it clear that the number of failed tackles is due to receiving fouls rather than the player falling short of stealing the ball.

The linear regression model for defenders returns the following graph and a R^2 coefficient of determination of 0.81422. The following graph takes the approximate number of tackles failed in the X-axis and the number of fouls called by the referee along the Y-axis.

![Defendersver 2](https://github.com/JungwooJang119/JungwooJang119.github.io/assets/113401325/02eee400-a20a-4c00-8721-5faad49b0b9c)

The linear regression model for midfielders was created using data from failed tackles vs. number of fouls. The returned R^2 coefficient of determination was 0.84779. The graph below lists the approximate number of failed tackles in the X-axis and the number referee-called fouls along the Y-axis.



The linear regression model for forwards used data from the number of fouls vs. the number of yellow cards. This is because a majority of the data for forwards in the "tackles" and "tackles success" columns was NaN or 0. A reason for this is due to forwards being offensive players. Tackles are classified as a defensive player category, so forwards do not have many opportunities to tackle other players in soccer matches. Furthermore, we used yellow cards as metrics instead of tackles because the dataset has information on the number of yellow cards for forwards. Yellow cards are issued by referees during soccer games to signal that a minor offense has been committed. Persistent fouling leads to yellow cards [5]. Since fouls lead to yellow cards, a dangerous player is determined by the higher number of fouls they have that maximizes their yellow card elgibility. Increased fouling and yellow cards leads to more injuries. The returned R^2 coefficient of determination was 0.88563. The graph hosts the number of fouls along the X-axis and number of yellow cards along the Y-axis.

insert pic here

The last graph mapped the correlation between the number of fouls and number of red cards. The R^2 coefficient of determination was 0.35591. The graph has the number of fouls along the X-axis and number of red cards along the Y-axis.

insert pic here

Analysis and Discussion

The results and the first model for defenders show the clear linear correlation that we expected from running this model. Most Premier League defenders who committed a certain number of failed tackles were called out for committing fouls at a predictable rate. In this model, we can identify the defenders that we considered the most dangerous, ones who commit more fouls than predicted from their number of failed tackles. By choosing the points that have the greatest distance from the linear regression line created from the model, we can see that the four defenders that are the most dangerous are the following players: Phil Jagielka, Andrew Robertson, Patrick van Aanholt, and Aaron Wan-Bissaka. This is because the outliers have a higher number of fouls per tackle failed. Knowing that tackles deemed as fouls are responsible for a great percentage of tackle-related injuries, the four chosen players have a higher chance of creating more fouls when they fail more tackles. Thus, leading to more tackle-related injuries. We chose four defenders as our team will follow a 4-3-3 formation, a typical formation in the Premier League.

The second model for midfielders highlights a linear correlation between the number of failed tackles and number of fouls. The midfielders that committed a higher number of failed tackles were typically assigned more fouls by the referees. Therefore, we know that a majority of midfielder-related failed tackles were due to referee-assigned fouls. Accordingly, the points that have the greatest positive distance from the linear regression line represent the most dangerous midfielders. As previously mentioned, these outlier midfielders have a greater chance of earning more fouls by failing more tackles. The most dangerous midfielders are Erik Lamela, Moussa Sissoko, and James Milner. Three midfielders were chosen to follow the Premier League's team formation consisting of 4 defenders, 3 midfielders, and 3 forwards.

The third model detailing the correlation between the number of yellow cards and number of fouls is for determining the 3 most dangerous forwards. As evidenced by the R^2 correlation determinant, this graph highlights a positive correlation where the increased number of fouls leads to more yellow cards. As the fouls increase for a player, so do the chances of the player causing possible injuries to occur during a match. Thus, we find the 3 most aggressive forwards by calculating the points with the greatest positive distance from the linear regression line. As each point corresponds to a unique player, the three forwards added to our team are Diogo Jota, Sergio Agüero, and Willian Borges da Silva.

The last graph encapsulates the correlation between red cards and fouls for forwards in the EPL. With a R^2 determinant correlation of 0.35591, we can conclude that there is a weak linear correlation between the two categories. Red cards are typically used in extreme cases of violent playing and EPL players know when to stop so they do not get ejected from the game. As a result, little information can be obtained from this model.

Comparing the first two graphs, we see that there is a positive correlation between failed tackles and fouls. Therefore, most of the failed tackles are labeled as failed due to referees issuing fouls rather than the players failing to steal the ball. Given that tackles deemed as fouls are responsible for a significant amount of tackle-related injuries, the 3 midfielders and 4 defenders chosen from the linear regression models are the 7 best players to be in team designed to be most dangerous.

Unlike the models for midfielders and defenders, the graph for forwards uses yellow cards and the number of fouls to find a positive correlation between the two categories. Fouls are offenses that signal that the player is playing in a way that can harm others. Although this model does not use tackles, we can still calculate the most aggressive forwards by first searching for a correlation between the number of yellow cards and fouls. If there is a correlation, then we use our knowledge on what fouls are used for to find the 3 forwards needed for the team. And since there is a positive correlation with a R^2 value of 0.88563, we can conclude that the players with the greatest positive distance from the regression line are more likely to earn more fouls, leading to more yellow cards and more injuries.

Conclusions

The most dangerous team crafted from the English Premier League is composed of Phil Jagielka, Andrew Robertson, Patrick van Aanholt, Aaron Wan-Bissaka, Erik Lamela, Moussa Sissoko, James Milner, Diogo Jota, Sergio Agüero, and Willian Borges da Silva.

Citations:  
[1] Argibay-González, J.C., Vázquez-Estévez, C., Gutiérrez-Santiago, A., Paramés-González, A., Reguera-López-de-la-Osa, X., & Prieto-Lage, I. (2022) Analysis of Injury Patterns in Men’s Football between the English League and the Spanish League. International Journal of Environmental Research and Public Health, 19(18), 
 https://doi.org/10.3390/ijerph191811296.  

[2] Badiella, L., Puig, P., Lago-Peñas, C., & Casals, M. (2023). Influence of Red and Yellow cards on team performance in elite soccer. Ann Oper Res, 325, 149–165. 
 https://doi.org/10.1007/s10479-022-04733-0.  

[3] Henderson, G., Christopher, B., & Portas, M. (2010). Factors associated with increased propensity for hamstring injury in English Premier League soccer players. Journal of 
 Science and Medicine in Sport, 13(4), 397-402. https://doi.org/10.1016/j.jsams.2009.08.003. 

[4] Sapp, R., Spangenburg, E., & Hagberg, J. (2018) Trends in aggressive play and refereeing among the top five European soccer leagues. Journal of Sports Sciences, 36(12), 1346-1354. https://doi.org/10.1080/02640414.2017.1377911 

[5] "A Guide to Yellow and Red Cards in Soccer." soccer.com. www.soccer.com/guide/guide-to-soccer-yellow-and-red-cards (Accessed December 4, 2023).

Contribution Table
| Group Member | Contribution |<br />
|--------------|--------------|<br />
| Emily Ngoc-Chau Nguyen Astillero | Potential Results & Discussion, Citations, Model 1 Cleaning & Pre-Processing |<br />
| Avery L Greer |Potential Results & Discussion, Model 1 Coding |<br />
| Erica Izaguirre | Methods & Potential Dataset, Model 1 Cleaning & Pre-Processing |<br />
| Jungwoo Jang| Introduction & Background, Problem Definition, Model Results Evaluation & Analysis |<br />
| Chae Hyun Kim | Methods & Potential Dataset, Model 1 Selection & Coding |<br />
| All | Midterm Report |<br />

Timeline
![Screenshot (570)](https://github.com/JungwooJang119/JungwooJang119.github.io/assets/113401325/ff6d4f2c-3e4e-4882-8fa4-ee8ffe791d7b)


