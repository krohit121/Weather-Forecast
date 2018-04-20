# Weather-Forecast
Predicting incoming weather pattern based on past records.

Objectives:

1. Introducing the weather dataset and outlining its exploratory analysis
2. Building logistic regression models for 9am and 3pm weather forecasts
3. Making Additional models in order to predict further variables such as tomorrow’s Rainfall, Humidity3pm, Sunshine variables 




dataset: https://www.biz.uiowa.edu/faculty/jledolter/datamining/dataexercises.html




Data_Discription:

Date: The date of observation (a date object).
Location: The common name of the location of the weather station.
MinTemp: The minimum temperature in degrees centigrade.
MaxTemp: The maximum temperature in degrees centigrade.
Rainfall: The amount of rainfall recorded for the day in millimeters.
Evaporation: Class A pan evaporation (in millimeters) during 24 h.
Sunshine: The number of hours of bright sunshine in the day.
WindGustDir: The direction of the strongest wind gust in the 24 h to midnight.
WindGustSpeed: The speed (in kilometers per hour) of the strongest wind gust in the 24 h to midnight.
WindDir9am: The direction of the wind gust at 9 a.m.
WindDir3pm: The direction of the wind gust at 3 p.m.
WindSpeed9am: Wind speed (in kilometers per hour) averaged over 10 min before 9 a.m.
WindSpeed3pm: Wind speed (in kilometers per hour) averaged over 10 min before 3 p.m.
Humidity9am: Relative humidity (in percent) at 9 am.
Humidity3pm: Relative humidity (in percent) at 3 pm.
Pressure9am: Atmospheric pressure (hpa) reduced to mean sea level at 9 a.m.
Pressure3pm: Atmospheric pressure (hpa) reduced to mean sea level at 3 p.m.
Cloud9am: Fraction of sky obscured by cloud at 9 a.m. This is measured in ”oktas,” which are a unit of eighths. It records how many eighths of the sky are obscured by cloud. A 0 measure indicates completely clear sky, while an 8 indicates that it is completely overcast.
Cloud3pm: Fraction of sky obscured by cloud at 3 p.m; see Cloud9am for a description of the values.
Temp9am: Temperature (degrees C) at 9 a.m.
Temp3pm: Temperature (degrees C) at 3 p.m.
RainToday: Integer 1 if precipitation (in millimeters) in the 24 h to 9 a.m. exceeds 1 mm, otherwise 0.
RISK_MM: The continuous target variable; the amount of rain recorded during the next day.
RainTomorrow: The binary target variable whether it rains or not during the next day.




Solution:

The said model is capable of describing tomorrow's weather foreecast at 9AM and 3PM followed by explaining additional variables like  such as tomorrow’s Rainfall, Humidity3pm, Sunshine variables with an accuracy of 80% and above.




Limitations:

-The accuracy could have been increased with a larger historical dataset and use of models like Time Series analysis & Random forest.
 
-The data could produce additional insights but could not be modeled due to time constraint.

-The models are limited to within the city, i.e. these models cannot be used to forecast weather of a different city.





Output:

1. 9AM Weather Forecast Model Output

Deviance Residuals: 
    Min       1Q   Median       3Q      Max  
-1.7667  -0.5437  -0.3384  -0.1874   2.7742  

Coefficients:
            Estimate Std. Error z value Pr(>|z|)    
(Intercept) 96.01611   33.57702   2.860 0.004242 ** 
Cloud9am     0.17180    0.07763   2.213 0.026893 *  
Humidity9am  0.06769    0.02043   3.313 0.000922 ***
Pressure9am -0.10286    0.03283  -3.133 0.001729 ** 
Temp9am      0.10595    0.04545   2.331 0.019744 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

    Null deviance: 234.90  on 247  degrees of freedom
Residual deviance: 177.34  on 243  degrees of freedom

#Confusion Matrix:

Reference
Prediction No Yes
       No  80  12
       Yes  6   7
                                          
               Accuracy : 0.8286          
                 95% CI : (0.7427, 0.8951)
    No Information Rate : 0.819           
    P-Value [Acc > NIR] : 0.4602          
                                          
                  Kappa : 0.3405          
 Mcnemar's Test P-Value : 0.2386          
                                          
            Sensitivity : 0.9302          
            Specificity : 0.3684          
         Pos Pred Value : 0.8696          
         Neg Pred Value : 0.5385          
             Prevalence : 0.8190          
         Detection Rate : 0.7619          
   Detection Prevalence : 0.8762          
      Balanced Accuracy : 0.6493          
                                          
       'Positive' Class : No 
AIC: 187.34

Number of Fisher Scoring iterations: 5

-----------------------------------------------------------------------------3Pm Forecast Model--------------------------------------------------------------

2. 3PM Forecast Model

Deviance Residuals: 
    Min       1Q   Median       3Q      Max  
-2.3065  -0.5114  -0.2792  -0.1340   2.6641  

Coefficients:
             Estimate Std. Error z value Pr(>|z|)    
(Intercept) 122.56229   35.20777   3.481 0.000499 ***
Cloud3pm      0.27754    0.09866   2.813 0.004906 ** 
Humidity3pm   0.06745    0.01817   3.711 0.000206 ***
Pressure3pm  -0.12885    0.03443  -3.743 0.000182 ***
Temp3pm       0.10877    0.04560   2.385 0.017071 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

    Null deviance: 234.90  on 247  degrees of freedom
Residual deviance: 159.64  on 243  degrees of freedom
AIC: 169.64

Number of Fisher Scoring iterations: 6


#Confusion Matrix:

 Reference
Prediction No Yes
       No  82   8
       Yes  4  11
                                          
               Accuracy : 0.8857          
                 95% CI : (0.8089, 0.9395)
    No Information Rate : 0.819           
    P-Value [Acc > NIR] : 0.04408         
                                          
                  Kappa : 0.58            
 Mcnemar's Test P-Value : 0.38648         
                                          
            Sensitivity : 0.9535          
            Specificity : 0.5789          
         Pos Pred Value : 0.9111          
         Neg Pred Value : 0.7333          
             Prevalence : 0.8190          
         Detection Rate : 0.7810          
   Detection Prevalence : 0.8571          
      Balanced Accuracy : 0.7662          
                                          
       'Positive' Class : No


-----------------------------------------------------------------------Tomorrow’s Rainfall Prediction Model--------------------------------------------------------------

3. Tomorrow’s Rainfall Prediction Model

Residuals:
    Min      1Q  Median      3Q     Max 
-10.363  -4.029  -1.391   3.696  23.627 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
MaxTemp         0.3249     0.1017   3.196 0.002225 ** 
Sunshine       -1.2515     0.2764  -4.528 2.88e-05 ***
WindGustSpeed   0.1494     0.0398   3.755 0.000394 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.395 on 60 degrees of freedom
Multiple R-squared:  0.6511,	Adjusted R-squared:  0.6336 
F-statistic: 37.32 on 3 and 60 DF,  p-value: 9.764e-14

#Coefficients:
      MaxTemp       Sunshine  WindGustSpeed  
       0.3249        -1.2515         0.1494 



-----------------------------------------------------------------------Tomorrow's Sunshine Prediction Model--------------------------------------------------------------

4. Tomorrow's Sunshine Prediction Model

Residuals:
    Min      1Q  Median      3Q     Max 
-9.9701 -1.8230  0.6534  2.1907  7.0478 

Coefficients:
                      Estimate Std. Error t value Pr(>|t|)    
Sunshine              0.607984   0.098351   6.182 1.82e-09 ***
Humidity3pm           0.062289   0.012307   5.061 6.84e-07 ***
Cloud3pm             -0.178190   0.082520  -2.159 0.031522 *  
Evaporation           0.738127   0.245356   3.008 0.002822 ** 
I(Evaporation^2)     -0.050735   0.020510  -2.474 0.013862 *  
WindGustSpeed         0.036675   0.013624   2.692 0.007453 ** 
Sunshine:Humidity3pm -0.007704   0.002260  -3.409 0.000729 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 3.134 on 340 degrees of freedom
Multiple R-squared:  0.8718,	Adjusted R-squared:  0.8692 
F-statistic: 330.3 on 7 and 340 DF,  p-value: < 2.2e-16

#Coefficients:
            Sunshine           Humidity3pm              Cloud3pm           Evaporation      I(Evaporation^2)         WindGustSpeed  
            0.607984              0.062289             -0.178190              0.738127             -0.050735              0.036675  
Sunshine:Humidity3pm  
           -0.007704  



-----------------------------------------------------------------------Tomorrow's Humidity Prediction Model--------------------------------------------------------------

5. Tomorrow’s Humidity 3pm Prediction Model

Residuals:
    Min      1Q  Median      3Q     Max 
-30.189  -9.117  -2.417   7.367  45.725 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 34.18668    5.45346   6.269 1.09e-09 ***
Humidity3pm  0.37697    0.06973   5.406 1.21e-07 ***
Sunshine    -0.85027    0.33476  -2.540   0.0115 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 14.26 on 344 degrees of freedom
Multiple R-squared:  0.2803,	Adjusted R-squared:  0.2761 
F-statistic: 66.99 on 2 and 344 DF,  p-value: < 2.2e-16

#Coefficients:
(Intercept)  Humidity3pm     Sunshine  
    34.1867       0.3770      -0.8503

