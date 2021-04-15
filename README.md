# Air-Quality-Index-Prediction
## Introduction
* Air pollution is a complex mixture of different gases particles perceived as a modern- day curse, due to the increased amount of urbanization and industrialization across the world.
* Several countries have taken some serious measures to maintain the air quality. India, which holds largest amount of human population, also took various measures to improve the air quality. A report by WHO shows, about 43% of all lung disease and lung cancer are attributable to Air Pollution. As per World Bank study released in 2016 revealed that India lost more than 8.5% of its GDP in 2013 due to the cost of increased welfare and lost labor due to air pollution. Various studies performed previously on the Air quality shows the Particulate Matters (PM2.5 and PM10) as the most dangerous and life-threatening pollutant among the group of pollutants. Particulate matter contributes to approximately 800,000 premature deaths each year.
* This analysis explores the factors which are influencing the Air pollution, this will help us analyze the trend in air quality across the years which help us to derive some business solutions. Also, we believe that forecasting the air quality of cities helps us to prevent before it impacts our environment.


## Business Problem
*	Air pollution levels in most of the urban areas have been a matter of serious concern. It is the right of the people to know the quality of air they breathe. In view of this, we took initiative for developing a national Air Quality Index (AQI) for Indian cities. AQI is a tool to disseminate information on air quality in qualitative terms (e.g., good, satisfactory, and poor) as well as its associated likely health impacts. There are six AQI categories, namely Good, Satisfactory, Moderately polluted, Poor, Very Poor, and Severe. The AQI considers eight pollutants for which short-term (up to 24-hourly averaging period) standards are prescribed, however, AQI can be calculated if monitoring data are available for minimum three pollutants of which one should necessarily be PM2.5 or PM10. Based on the measured ambient concentrations, corresponding standards and likely health impact, a sub-index is calculated for each of these pollutants.
*	WHO reports, particulate matter (PM) contributes to approximately 800,000 premature deaths each year. If the situation continues, this might have some serious not only on country’s GDP but also on the health of our future generations. Several studies were previously done to study the Air quality of Delhi, which is the most polluted city India. But for a large metropolitan city, where the growth of corporate companies is in exponential order, a proper study has to be done in order to increase the quality of lives. So, in the above context we planned to analyze the Air quality of India. This report explores the factors influencing the Air pollution; help us analyze the trend in air quality across the years which help us to derive some business solutions. Also, we believe that forecasting the air quality helps us to prevent before it impacts our environment, which in turn increase the production level of the industries and other companies, which in turn increase the country’s GDP.


## Problem Statement
As India is developing economy from Industrialization perspective. Development may be good for the nation in terms of GDP and economic gain, but it also has a flipside as more and more industries are being established, they are emitting more smoke, pollutants and Particulate Matter (PM) into the air which is increasing Air pollution. Air Pollution is causing diseases such as Asthma, Lung Cancer and other cardiovascular diseases. Air pollution is being measured by AQI (Air Quality Index) and higher the AQI higher the air pollution. In this project we will analyze the air quality data of major developed/ developing cities in India to find some underlying principles or patterns which will help us in predicting the AQI with the given data. Since this data has been captured at specific intervals over a period of time, we will be conducting a Time Series Analysis to predict the AQI of a city at a point in time.


## Methodology
###	Data Collection: 
* The data has been made publicly available by the Central Pollution Control Board: https://cpcb.nic.in/ which is the official portal of Government of India.

###	Data Understanding: 
* The dataset contains air quality data and AQI (Air Quality Index) at hourly and daily level of various stations across multiple cities in India. 
* I will be focusing on monthly data of cities for forecasting the AQI all over India. 
* It contains different types of pollutants like PM2.5, PM10, NO, CO, Benzene, Toluene, and Xylene etc.

###	Data Cleaning: 
* The missing values are present in all variables in the dataset except City and Datetime variables. Below heatmap shows missing values in variables.
 


![image](https://user-images.githubusercontent.com/78426725/114754272-045f7a80-9d76-11eb-936b-d260df5d7a40.png)




* I imputed the missing values in the data by the following methods : First the data was segregated according to city and datetime. Then I imputed 5 day average, then monthly average and remaining missing values were filled by backward and forward fill. The distribution of variables after imputing missing values was not much changed.
 
###	Univariate Analysis: 

* All the variables in dataset are numerical variables. So, I checked the distribution of all the variables and skewness of the data.



![image](https://user-images.githubusercontent.com/78426725/114753021-a1211880-9d74-11eb-841f-d2299735341c.png)




* From the plot, we can say that all the variables are right skewed. Skewness of the Benzene, Toluene and CO is on higher side than other variables.
 

###	Multivariate Analysis:

* For multivariate analysis, I plotted the correlation plot and scatter plots to check the impact of all variables with AQI. 
* It shows that the PM2.5, PM10, NO2 and CO are positively correlated with AQI. It is visualized by heatmap shown below.
* All other variables are also positively correlated with AQI but the correlation between them is weak, which means they have less impact on AQI.





![image](https://user-images.githubusercontent.com/78426725/114753060-ada57100-9d74-11eb-9876-51a26225ac38.png)

 

 






* I checked relationship of all the pollutants with AQI and plotted scattered plot. And we see that CO, PM2.5, NO2 has the strong visual relation with AQI.
 
![image](https://user-images.githubusercontent.com/78426725/114753134-bdbd5080-9d74-11eb-92e5-314191e48f46.png)
![image](https://user-images.githubusercontent.com/78426725/114753161-c3b33180-9d74-11eb-9ca5-0031f1f3e5b1.png)
![image](https://user-images.githubusercontent.com/78426725/114753184-c9a91280-9d74-11eb-95e1-c82f2f114984.png)


#### City wise AQI for India
* It shows that, Ahmedabad city have a higher average of AQI in last five years due to population and increasing industrialisation in the area. And Aizawl have very low average of AQI, the reason might be low population and more mountainious region.


![image](https://user-images.githubusercontent.com/78426725/114753287-ea716800-9d74-11eb-9e3d-8446c433fd68.png)




#### City wise representation of AQI on map of India




![image](https://user-images.githubusercontent.com/78426725/114753317-f5c49380-9d74-11eb-81f4-7ad1a061f57d.png)




* According to the map we can see the top 5 cities with the highest AQI and top 5 cities with the lowest AQI
* Cities with the highest AQI are represented by the red marker and the cities with the lowest AQI are represented by the green marker. We can infer that places towards the north region have high AQI whereas the AQI falls as we come down in the south.
* Ahmedabad is the city with the highest AQI and Aizwal has the lowest AQI
 

###	Time Series Visualization

#### Monthly and yearly visualisation of AQI



![image](https://user-images.githubusercontent.com/78426725/114753369-04ab4600-9d75-11eb-9c1c-2cae45aa0f32.png)

 


* We can see that the AQI has decreased after January 2020, this might be because of the COVID Pandemic. Industries were completly closed; Transport was halted for 5-6 months. So due to that we can see the Decline in AQI During 2020.


#### Hourly visualisation of AQI 




![image](https://user-images.githubusercontent.com/78426725/114753416-0f65db00-9d75-11eb-9791-1179dd13bebd.png)



 
* It is surprising to see that the AQI and all other pollutants decrease at night and high at the mid of the day.
* As per the scientific analysis, higher the temperature, lower the AQI. As temperature is high in the day, the air expands and move upwards which results in reduction of AQI on earth's surface. The wind flow is low during night due to which all the pollutants settle down on the earth surface leading to increase in AQI levels.


### Statistical Tests

* Here I performed ANOVA test with all the columns and checked which pollutants are affecting more on AQI. From the P values, I could infer that the highly significant features were CO, PM2.5 and NO2.

### Stationarity

* Stationarity is an important concept in time series analysis. Stationarity means that the statistical properties of a time series do not change over time. Stationarity is important because many useful analytical tools and statistical tests and models rely on it.
* I checked for stationarity with adfuller (Dickey Fuller) test for AQI. The Hypothesis was aa follows.
* $H_0$: Data is not stationary
* $H_1$: Data is Stationary
* I could infer from the test that the pvalue is < 0.05, hence we reject the H0. This means that data is stationary.

### Time Series Decomposition

* We can also visualize our data using a method called time-series decomposition that allows us to decompose our time series into three distinct components like trend, seasonality, and noise.

* The below graph gives us observed values in the data. Next three graphs are Trend, Seasonality and Residuals. 
* By looking at the trend in the data, we can see that the trend is decreasing gradually year by year and there is sudden decrease after 2019.  
* The seasonal graph shows the cyclic changes in the data. 
* The data points which doesn’t follow trend as well as seasonality, are plotted in the residual graph.
 
 
 

 ![image](https://user-images.githubusercontent.com/78426725/114814523-fb9c9200-9dd1-11eb-8fdc-204b34999d6f.png)






## Base Model

* Here we chose ARIMA model for building a base model. We are taking order (p,d,q) as (1,1,1) and built ARIMA model as our basemodel. 
* For finding the best values for order (p,d,q), I used Auto Arima. It performs the step wise search to minimize AIC value and build a model for that. 
* Auto ARIMA gave the best order (3,0,2). ARIMA (3,0,2) gave good result than ARIMA (1,1,1). Its AIC value is also low than the ARIMA (1,1,1) and log-likelihood is higher than the ARIMA (1,1,1).

## Month wise Univariate analysis of AQI
* After the auto ARIMA we used the order (3,0,2) and we add the seasonality order(m) as 12 to build the SARIMAX model. SARIMAX model is the same as an ARIMA model but it also takes into account the seasonality factor. 
* Seasonality is the presence of variations that occur at specific regular intervals less than a year. 
* Seasonality may be caused by weather and consists of periodic, repetitive, and generally regular and predictable patterns in the levels of a time series.
 




 ![image](https://user-images.githubusercontent.com/78426725/114839823-d7ea4380-9df3-11eb-94bb-0d388abce147.png)






* From the above graph we have observed and forecasted value. The predicted value of 2020 is very high on the basis of previous data. But the actual value of AQI seems less the reason for decrease might be pandemic.



## Month Wise Multivariate analysis with VAR

* VAR is similar to the AR and MA models the only difference that AR and MA are used for univariate analysis whereas VAR is a multivariate analysis. The AR and MA models are unidirectional and VAR model is a bidirectional model. 
* The algorithm calculates the vectors of the coefficients and multiplies it to the vectors of (t-1) value and adds the vectors of errors to it. It gives us the accuracy for all the variables.


## Week wise Univariate Analysis with AQI
* In week wise analysis, first I have built the auto ARIMA model and find the best order. By using this order SARIMAX model was built.

With the output of SARIMAX and ARIMA model I forecasted the AQI value for year 2020/21 same as monthly analysis.
 
 
 
 
![image](https://user-images.githubusercontent.com/78426725/114754652-71731000-9d76-11eb-817b-53fbe2b55e09.png)

 
 


From the above graph we have observed and forecasted value. And forecasted the value of AQI for 2021.


##	Week Wise Multivariate analysis with VAR

Same as Monthly analysis, VAR was built for Weekly data. there was not much difference in RMSE and MAPE values.

## Comparative analysis

Model_Name                       	RMSE	               MAPE
0	SARIMAX Month wise	          45.747235          	39.102799
1	VAR MONTH Wise	              62.862111	          55.323994
2	SARIMAX Week Wise	           20.914404	          15.322581
3	VAR week Wise	               61.936899	          52.768557

* We can see that the RMSE and MAPE values of SARIMAX model are less than the VAR model. 
* It means SARIMAX model is performing best in forecasting AQI values.
* We have chosen SARIMAX model as our final model, therefore the forecasted values are visualised through graphical respresentation.
 
## Conclusion

* We have done a Univariate and Multivariate analysis on AQI.
* Surprisingly we could see that AQI is increasing at night and is less in the day. The reason is that the wind decraese at night due to which the pollutants tend to settle down on the earth's surface leading to increase in AQI.
* Univariate Analysis is done by using ARIMA, Auto-ARIMA and SARIMAX models.
* Multivariate Analysis is done by using VAR model.
* We have recieved the best results for predicting AQI through SARIMAX, therefore we chose SARIMAX as our final model and the forecasted values are visualized through graphical representation.
* From the predicted values we could observe that the AQI for 2020 is predicted to be very high on the basis of the previous data, but the actual values of AQI are very less in 2020. The reason for the decrease might be the pandemic which lead to lockdown and hence decrease in pollutants.
* From the forecasted graph we can conclude that AQI will be high for coming year 2021. The focus should be on how the pollutants affecting AQI can be reduced.
* According to our analysis the pollutants affecting the most on AQI are PM2.5, NO2 and CO on the basis of Correlation and Statistical Analysis.



## Business problem Solution

* From the above analysis we found that the AQI will increase in upcoming year. And we know that	the higher AQI is harmful for humans as well as environment. We also know that PM 2.5, PM10, CO, NO2 are highly affected on AQI so we need to control it. We should take appropriate measures to reduce the AQI by more tree plantation and taking precautions for pollutants produced by industries.


## References
* https://paginas.fe.up.pt/~ec/files_0405/slides/02%20CRISP.pdf 
* https://en.wikipedia.org/wiki/Cross-industry_standard_process_for_data_mining


## Other References:
1.	Anand Kumar, Dr. Ashish Grag and Prof. Upender Pandel, 2011, A Study of Ambient Air Quality Status in Jaipur City (Rajasthan, India), Using Air Quality Index, Nature and Science, 9(6), 38 – 43.
2.	Sarella G and Khambete A K 2015. Ambient Air Quality Analysis using Air Quality Index
– A. Case Study of Vapi. International Journal for Innovation Research in Science & Technology. 1(10)
           
