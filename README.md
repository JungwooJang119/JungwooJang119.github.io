# JungwooJang119.github.io
Introduction  
Among the many professional leagues of association football or soccer, the English Premier League (EPL) stands as the most valuable and popular of them all.  
Problem Definition  
As the most popular and richest soccer league, the EPL is known for its aggressive playstyle with its high level of tackles and corresponding fouls [4]. The dataset chosen includes full game statistics during the 2020-21 and 2021-22  seasons, with the focus primarily on the number of fouls, yellow cards, red cards, and more. The goal of this project is to determine the most dangerous soccer game possible, with two of the most aggressive teams in the league and the most lenient referee.  
Methods  
We will use linear regression to predict the degree of danger with the weighted features (yellow cards, red cards, fouls, penalty kicks, etc.) as our input. These weighted input points would act as independent variables for us to observe how much influence each variable has on the degree of danger of a match.  
Linear regression will also allow us to analyze the referees of the Premier League. After we calculate an average for each referee of how many red cards, yellow cards, and fouls they call on each team. Our second independent variable for this second analysis will be the average amount of red cards, yellow cards, and fouls. This method will allow us to determine a coefficient of leniency for each referee that we can then compare to all others.  
We will utilize linear regularization techniques such as LASSO regression as it will help us improve the performance of our linear regression model by finding a balance between model simplicity and accuracy. The regression will help us avoid overfitting, increase model interpretation, select a subset of appropriate variables, and improve prediction accuracy.  
Potential Dataset  
We searched for sets that included the number of yellow cards, red cards, fouls, free kicks given, the teams that played, and the referee for the game. The English Premier League dataset (https://www.kaggle.com/datasets/saife245/english-premier-league) presents this information, which we can utilize to compare the performance statistics of each team and referee to create the most hazardous combination possible.  
Potential Results & Discussion  
Our potential results will be measured by the computed danger scores. We’re expecting teams with a higher amount of fouls, yellow cards, and red cards to lead to a more dangerous match.  Since our data set has a booking points statistic counting yellow cards as 10 points and red cards as 25 points, we will use these as weights, and we will give fouls an arbitrary weight of 3 since fouls are less severe than yellow cards but still lead to penalty kicks. We will normalize these three values to get a standardized score.  
Each team will be evaluated individually. Since we are also accounting for referee in each match, the more lenient the referee is, the better.  

Citations:  
Argibay-González, J.C., Vázquez-Estévez, C., Gutiérrez-Santiago, A., Paramés-González, A., Reguera-López-de-la-Osa, X., & Prieto-Lage, I. (2022) Analysis of Injury Patterns in Men’s Football between the English League and the Spanish League. International Journal of Environmental Research and Public Health, 19(18), 
 https://doi.org/10.3390/ijerph191811296.  
Badiella, L., Puig, P., Lago-Peñas, C., & Casals, M. (2023). Influence of Red and Yellow cards on team performance in elite soccer. Ann Oper Res, 325, 149–165. 
 https://doi.org/10.1007/s10479-022-04733-0.  
Henderson, G., Christopher, B., & Portas, M. (2010). Factors associated with increased propensity for hamstring injury in English Premier League soccer players. Journal of 
 Science and Medicine in Sport, 13(4), 397-402. https://doi.org/10.1016/j.jsams.2009.08.003. 
Sapp, R., Spangenburg, E., & Hagberg, J. (2018) Trends in aggressive play and refereeing among the top five European soccer leagues. Journal of Sports Sciences, 36(12), 1346-1354. https://doi.org/10.1080/02640414.2017.1377911 

