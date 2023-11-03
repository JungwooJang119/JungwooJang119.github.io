# CALCULATING THE MOST DANGEROUS EPL GAME
## Project Group 30
### Emily Ngoc-Chau Nguyen Astillero, Avery Greer, Erica Izaguirre, Jungwoo Jang, Chae Hyun Kim
Introduction  
Among the many professional leagues of association football or soccer, the English Premier League (EPL) stands as the most valuable and popular of them all [2]. The literature in this field also states that the EPL is known to be one of the most dangerous leagues in the world, boasting a considerable number of injuries sustained within a season [1][3]. We seek to determine what is the most aggressive team possible (excluding a goalie), predicting using data on tackles and fouls per player from the seasons starting in 1993 and ending in 2020. This aggressive team would create the most opportunities to occur since “tackles deemed as fouls are reportedly responsible for 21–69% of tackle-related injuries” [4].

Problem Definition  
As the most popular and richest soccer league, the EPL is known for its aggressive playstyle with its high level of tackles and corresponding fouls [4]. The dataset chosen includes full player statistics from 1993 to 2020; however, we will focus on the number of tackles attempted, the number of unsuccessful tackles and the number of fouls per player. The goal of this project is to determine a team of the most aggressive players.  

Methods  
We will use linear regression to determine the relationship between unsuccessful tackle percentage and the number of fouls. Our input will be the percentage of unsuccessful tackles per player and our output will be the number of fouls each player obtained. Our linear regression model will be run 3 times total, once for each position we want to fill: defender, midfielder, and forward. We will not be choosing a goalie since goalies should not be tackling during games. 
We will utilize linear regularization techniques such as LASSO regression as it will help us improve the performance of our linear regression model by finding a balance between model simplicity and accuracy. The regression will help us avoid overfitting, increase model interpretation, select a subset of appropriate variables, and improve prediction accuracy.

Potential Dataset  
We searched for sets that included data on a player basis and contained the total number of tackles, a metric for successful/unsuccessful tackles, the number of fouls, and player position. The All Time Premier League Player Statistics dataset (https://www.kaggle.com/datasets/rishikeshkanabar/premier-league-player-statistics-updated-daily) presents this information, which we can utilize to create a team with higher number of tackles and fouls and lead to the most chances for injury to occur. 

Potential Results & Discussion  
We will examine the correlation between unsuccessful tackles and fouls by calculating the correlation coefficient of our regression line with minimal Mean Squared Error. When creating our teams, we will pick the players with highest predicted foul counts from the models of the three positions. One team consists of 4 defenders, 3 midfielders, and 3 forwards each with the highest predicted fouls. 
We’re expecting players with a higher percentage of unsuccessful tackles to obtain more fouls and create more opportunities for injury to occur, leading to a more dangerous match. 

Citations:  
[1] Argibay-González, J.C., Vázquez-Estévez, C., Gutiérrez-Santiago, A., Paramés-González, A., Reguera-López-de-la-Osa, X., & Prieto-Lage, I. (2022) Analysis of Injury Patterns in Men’s Football between the English League and the Spanish League. International Journal of Environmental Research and Public Health, 19(18), 
 https://doi.org/10.3390/ijerph191811296.  

[2] Badiella, L., Puig, P., Lago-Peñas, C., & Casals, M. (2023). Influence of Red and Yellow cards on team performance in elite soccer. Ann Oper Res, 325, 149–165. 
 https://doi.org/10.1007/s10479-022-04733-0.  

[3] Henderson, G., Christopher, B., & Portas, M. (2010). Factors associated with increased propensity for hamstring injury in English Premier League soccer players. Journal of 
 Science and Medicine in Sport, 13(4), 397-402. https://doi.org/10.1016/j.jsams.2009.08.003. 

[4] Sapp, R., Spangenburg, E., & Hagberg, J. (2018) Trends in aggressive play and refereeing among the top five European soccer leagues. Journal of Sports Sciences, 36(12), 1346-1354. https://doi.org/10.1080/02640414.2017.1377911 

Contribution Table
| Group Member | Contribution |<br />
|--------------|--------------|<br />
| Emily Ngoc-Chau Nguyen Astillero | Potential Results & Discussion, Citations |<br />
| Avery L Greer |Potential Results & Discussion |<br />
| Erica Izaguirre | Methods & Potential Dataset |<br />
| Jungwoo Jang| Introduction & Background, Problem Definition |<br />
| Chae Hyun Kim | Methods & Potential Dataset |<br />

Timeline
![Screenshot (570)](https://github.com/JungwooJang119/JungwooJang119.github.io/assets/113401325/ff6d4f2c-3e4e-4882-8fa4-ee8ffe791d7b)


