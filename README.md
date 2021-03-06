
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
   * grade

* house **size**
   * family size
   * above average compared to the neighborhood?

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

  * housing price is highly sensitive to the variation of house interior area
  * house grading system in King county accounts for each house's age
  * time length after house renovation to sold year determines house condition 
  * house tour correlates to house amenities, design and maintenance, e.g. pool, basement, floors and renovation (condition)
  * house selling price affected by its latitude (north to Vancouver and south to Portland, OR) ; instead, its longitude has no effect 
  * winter holiday season attracts more tours and greater discount on houses located further away from Seattle city  
  * lot size weights more on selling price than house interior area
  * house price goes down from middle of summer through fall (end of fiscal year) till January of following year
  * house price gradually ramps up from begining of spring through begining of summer

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
  
Top15 influential features:

    - house tour
    
    - house amenities
    
    - house interior area 
    
    - time length from renovation to sold year that also correlates with condition to-date
    
    - house multi-layer design, basement (down to ground level) at bottom and floors (up to roof) on top

![Model](./image/mod2_model_final_submit_alt_qq.png)
![Model](./image/mod2_model_final_submit_alt_homo.png)
![Model](./image/mod2_model_final_submit_alt_qqhist.png)
![Model](./image/mod2_model_final_submit_alt_Top15_coefs.png)

  - **alternative** model (after p-Value selection):
  
Top15 influential features: same aas above

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

## Question 1: What are influential factors on frequencies of house tour? Season matters!
  - season
  - grade (evaluation, house age/built year)
  - condition (maintenance/renovation)
  - location (closer or further away from Seattle city, Vancouver CA or Portland OR)
  - house age (built year)
  - house amenities (waterfront, lot)
  - design (floor plan, with or without basement)
  - price
  
    * grade : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, **higher graded** houses attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p1.png)
  
    * condition : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, **well-maintained** and/or **renovated** houses attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p2.png)
  
    * latitude (N/S) : interior area vs. price 
    
    Over *Thanksgiving and Xmas* holiday seasons, houses located at **northern of Seattle** attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p3.png)
  
    * longitude (E/W) : interior area vs. price
    
    Over *Thanksgiving and Xmas* holiday seasons, houses located at **eastern of Seattle** attract more guests, visitors and buyers for tours.
    
    ![EDAQ1](./image/mod2_EDAQ1-p4.png)
  
    * renovation : interior area vs. price
    
    Surprizingly, renovated houses are likely to be **older** than those without renovation, so that they are **not** as attractive as new ones. Moreover, owing to housing maintenance expense, renovated houses are a bit more pricey than those without additional cost.  
    
    ![EDAQ1](./image/mod2_EDAQ1-p5.png)
    
    ![EDAQ1](./image/mod2_EDAQ1-p11.png)
  
    * basement : interior area vs. price
    
    Houses with basements are more pricey (because of larger living area) than without. Therefore, they are **not** quite attrative. 
    
    ![EDAQ1](./image/mod2_EDAQ1-p6.png)
  
    * house age : age vs. price
    
    owing to the growing population, that accompany with more and more business migration from other cities into Seattle, with years, the need of building more houses for the younger generation of immigrants increases, accordingly. Since the space close to Seattle becomes limited, these newer houses were built radially away from Seattle. Hence, they are closer to either Vancouver, Canada or Idaho, USA. The weather is thus colder and drier.            
    
      - latitude
      
      Houses in suburban areas around **northern of Seattle** are likely younger than those inside Seattle city. Newer houses are likely to attract higher condition score and better grade based on the King county grading scale, so that, relatively, they tend to be more pricey than older ones, which were built earlier and closer to Seattle. Despite that, most newer houses were sold at a much cheaper price than older ones, because these younger houses are likely located in the suburban area, i.e. closer to Vancouver or Idaho, and the daily commute might take residents substantial amount of time.   
      
      ![EDAQ1](./image/mod2_EDAQ1-p7.png)
      
      Likewise, houses located at **eastern of Seattle** tend to be younger. 
      
      - longitude
      ![EDAQ1](./image/mod2_EDAQ1-p8.png)
      
    * house age : age vs. interior area 
    
      Despite the bigger living area of younger houses than older ones' in the same area, these houses are still affordable due to where they were built. Taking the traffic time spent on the daily commute into consideration, houses in suburban area might be able to be sold at lower price than those. On the other hand, houses that were were constructed further and further away from Seattle city were likely smaller among same-age houses distributed across various areas.         
    
      - latitude   
      
      ![EDAQ1](./image/mod2_EDAQ1-p9.png)
      
      - longitude
      
      ![EDAQ1](./image/mod2_EDAQ1-p10.png)
      
### Analysis:
Outliers were removed prior to exploratory data analysis. Generally speaking, we have been aware of the fact that the housing price is primarily influenced by its interior area. Therefore, we categorized data into various groups such as house sold seasons and frequencies of house tour. We would like to see how significantly the house selling price varies with interior area under different season and frequency tours.    

### Recommendations:
Different seasons make impact on house selling price and the willingness of joining house tours as well. We also noticed the house condition, location and age (built-year/grading) also affect house buyers to participate in house tours. Three recommendations are listed as follows:

  - house maintenance (condition score)
  - house location
  - house age (built-year related grade scale)
  - house amenities (pool)

### Future Work:
To quantify our observations, a list of future work are needed. 

  - relate condition score to time lenth spanned from renovation to house sold year (house maintenance)
  - relate zipcode to city name (house location)
  - relate house age to grading scale
  
## Question 2: What are influential factors on house buyers' decision-making behaviors? House itself! 
 
### Analysis: same as above

### Recommendations:

  - House design (floor plan)
  - House condition (renovation/maintenance)

### Future Work: same as above

---------------------------------------------------------------------------------------------------------------------------------------
