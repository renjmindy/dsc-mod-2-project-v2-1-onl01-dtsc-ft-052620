
# Seattle Housing Project: Motivation

I would like to utilize this data to study house buyers' decision-making behaviors, e.g. customer purchase behavior modeling.

![Motivation](./image/Seattle_Zipcode.png)


**What're major factors that may make impact on house buyers' behaviors?**

* house **location**
   * weather factor
   * maintenance cost
   * daily commute time, road condition and traffic safety
   * neighborhood quality, e.g. ethics, religion, immigration backgrounds, political parties, education level, salary range, career/occupation and ages
   * school district for kid education
   * community life, convenience and entertainment, e.g. close to national state park, fishing, dairy food farms and so on
   * crime rate

* house **condition**
   * when it was built
   * has it ever been renovated?
   * with or without basement?

* house **size**
   * family size
   * above average compared to the neighborhood?
   * house tour evaluation: reliability of votes, e.g. are voters all buyers? or they are simply house tourists?

* house **price**
   * buyer's economic capability
   * buyer's health condition
   * buyer's age range or generation
   * buyer's intension to be a landlord of the house (monthly rental fee)
   * annual tax payment
   * renovation/maintenance expanses included?
   * loan option for specific groups
   * discount deal/offer for specific groups and seasons
   
https://en.wikipedia.org/wiki/Seattle

https://en.wikipedia.org/wiki/History_of_Seattle

- **selective** model (after p-Value selection):

![Motivation](./image/mod2_motivation_final_submit_alt.png)

- **alternative** model (after p-Value selection):

![Motivation](./image/mod2_motivation_final_submit.png)

---------------------------------------------------------------------------------------------------------------------------------------

## Model Quality/Approach

* Multiple Linear Regression Models:

  - **selective** model (before p-Value selection):
  
  final features:

    1. **'sqft_above_log'** (Top15): house interior area

    2. 'AvgAreaPerRm_log': room size (bathrooms and bedrooms both included)

    3. **'lat_seattle_diff_log'** (Top15): latitudinal coordinate difference from Seattle city's (47°36′35″N) 

    4. 'long_seattle_diff_log': longitudinal coordinate difference from Seattle city's (122°19′59″W)

    5. 'yrgrade_built_log': linear combination of house built year and its grade  

    6. **'floors'** (Top15): house design (multiple levels above house basement)

    7. **'waterfront'** (Top15): pool outside house 
         
    8. **'view'** (Top15): house tour 

    9. **'condition'** (Top15): house maintenance and/or renovation construction 

    10. **'hasbasement'** (Top15): with or without basement (ground level)

    11. 'hasbiggerllratio': ratio of liviing area to lot's compared to that obtained by averaging over 15 nearest neighbors'

    12. 'hasreno4sale': difference between house sold year and the year that house renovation happened

    13. 'hasinSeattle': check whether house located in Seattle city or not, depending on house's zipcode 

    14. 'yrmo_sold': house sold year and month combined

![Model](./image/mod2_model_final_submit_alt_All_coefs.png)

   - **selective** model (after p-Value selection):

![Model](./image/modelSummary_final_submit_alt_1.png)
![Model](./image/modelSummary_final_submit_alt_2.png)

![Model](./image/mod2_model_final_submit_alt_vifs.png)
![Model](./image/mod2_model_final_submit_alt_coefs.png)

* Multiple Linear Regression Models:

  - **alternative** model (before p-Value selection):
  
  final features:
 
    1. **'sqft_above_log'** (Top15): house interior area

    2. 'AvgAreaPerRm_log': room size (bathrooms and bedrooms both included)

    3. **'zipcode_lat_log'** (Top15): house zipcode divided by latitudinal coordinate

    4. 'zipcode_long_log': house zipcode divided by longitudinal coordinate 

    5. 'yrgrade_built_log': linear combination of house built year and its grade  

    6. **'floors'** (Top15): house design (multiple levels above house basement)

    7. **'waterfront'** (Top15): pool outside house 
         
    8. **'view'** (Top15): house tour 

    9. **'condition'** (Top15): house maintenance and/or renovation construction 

    10. **'hasbasement'** (Top15): with or without basement (ground level)

    11. 'hasbiggerllratio': ratio of liviing area to lot's compared to that obtained by averaging over 15 nearest neighbors'

    12. 'hasreno4sale': difference between house sold year and the year that house renovation happened

    13. 'yrmo_sold': house sold year and month combined 

![Model](./image/mod2_model_final_submit_All_coefs.png)

  - **alternative** model (after p-Value selection):
  
![Model](./image/modelSummary_final_submit_1.png)
![Model](./image/modelSummary_final_submit_2.png)

![Model](./image/mod2_model_final_submit_All_vifs.png)
![Model](./image/mod2_model_final_submit_Sel_coefs.png)

* Normality Check: Q-Q Plots & homoscedasticity

To check for the normality assumption, you can obtain error terms (residuals) from the model and draw Q-Q plot against a standard normal distribution as shown below. While the residuals do not seem to match up perfectly with the red line, there seem to be no super clear deviations from the red line. So you can assume that you're OK for the normality assumption. Moreover, homoscedasticity indicates that a dependent variable's variability is equal across values of the independent variable. A scatter plot is good way to check whether the data are homoscedastic (meaning the residuals are equal across the regression line).

  - **selective** model (after p-Value selection):

![Model](./image/mod2_model_final_submit_alt_qq.png)
![Model](./image/mod2_model_final_submit_alt_homo.png)
![Model](./image/mod2_model_final_submit_alt_qqhist.png)
![Model](./image/mod2_model_final_submit_alt_Top15_coefs.png)

  - **alternative** model (after p-Value selection):

![Model](./image/mod2_model_final_submit_qq.png)
![Model](./image/mod2_model_final_submit_homo.png)
![Model](./image/mod2_model_final_submit_qqhist.png)
![Model](./image/mod2_model_final_submit_Top15_coefs.png)

---------------------------------------------------------------------------------------------------------------------------------------

# Visualizations & EDA

## Question: What are influential factors on house price?

![EDA](./image/mod2_EDA_final_submit_p1.png)
![EDA](./image/mod2_EDA_final_submit_p2.png)
![EDA](./image/mod2_EDA_final_submit_p3.png)
![EDA](./image/mod2_EDA_final_submit_p4.png)

## Question 1: What are influential factors on house tours? 
  - season
  - grade (evaluation)
  - condition
  - location
  - house age
  - house amenities (basement, lot)
  - maintenance (renovation)
  - price
  
    * grade : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, **higher graded** houses attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p1.png)
  
    * condition : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, **well-maintained** houses attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p2.png)
  
    * latitude (N/S) : interior area vs. price 
    
    Over *Thanksgiving and Xmas* holiday seasons, houses located at **northern of Seattle** attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p3.png)
  
    * longitude (E/W) : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, houses located at **eastern of Seattle** attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p4.png)
  
    * renovation : interior area vs. price
    
    Renovated houses are **older** than those without renovation, so that they are **not** as attractive as new ones. Moreover, owing to maintenance expense, renovated houses are a bit more pricey than those without additional cost.  
    
    ![EDAQ1](./image/mod2_EDAQ1-p5.png)
    
    ![EDAQ1](./image/mod2_EDAQ1-p11.png)
  
    * basement : interior area vs. price
    
    Houses with basements are more pricey (because of larger living area) than without. Therefore, they are **not** quite attrative. 
    
    ![EDAQ1](./image/mod2_EDAQ1-p6.png)
  
    * house age : age vs. price
    
    owing to the growing population, that accompany with more and more business migration from other cities into Seattle, with years, the need of building more houses for the younger generation of immigrants increases, accordingly. Since the space close to Seattle becomes limited, these newer houses were built radially away from Seattle. Hence, they are closer to either Vancouver, Canada or Idaho, USA. The weather is thus colder and drier.            
    
      - latitude
      
      Houses located at **northern of Seattle** are younger. Newer houses are likely to attract higher condition score and better grade based on the King county grading scale, so that, relatively, they tend to be more pricey than older ones, which were built earlier and closer to Seattle. Despite that, most newer houses were sold at a much cheaper price than older ones, because these younger houses are likely located in the suburban area, i.e. closer to Vancouver or Idaho, and the daily commute might take residents substantial amount of time.   
      
      ![EDAQ1](./image/mod2_EDAQ1-p7.png)
      
      Houses located at **eastern of Seattle** are younger. 
      
      - longitude
      ![EDAQ1](./image/mod2_EDAQ1-p8.png)
      
    * house age : age vs. interior area 
    
      Generally speaking, younger houses tend to be bigger, but they are still sold at lower prices, because they are located in suburban districts.
    
      - latitude   
      
      ![EDAQ1](./image/mod2_EDAQ1-p9.png)
      
      - longitude
      
      ![EDAQ1](./image/mod2_EDAQ1-p10.png)
      
### Analysis:

### Recommendations:

### Future Work:
  
## Question 2: What are influential factors on house buyers' decision-making behaviors?
  - view
  - purchase, i.e. house sold months (season)
   
### Analysis:

### Recommendations:

### Future Work:

---------------------------------------------------------------------------------------------------------------------------------------

