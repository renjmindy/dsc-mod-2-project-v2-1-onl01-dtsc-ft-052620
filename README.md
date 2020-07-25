
# Seattle Housing Project: Motivation

I would like to utilize this data to study house buyers' decision-making behaviors, e.g. customer purchase behavior modeling. 

**What're major factors that make impact on house buyers' behaviors?**

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

Coordinates of Seattle WA: 47°36′35″N 122°19′59″W

https://en.wikipedia.org/wiki/History_of_Seattle


![Motivation](./image/mod2_motivation_p.png)
![Motivation](./image/mod2_motivation_p.png)

---------------------------------------------------------------------------------------------------------------------------------------

# Visualizations & EDA

## Question: What are influential factors on house price?

![EDA](./image/mod2_EDA_p1.png)
![EDA](./image/mod2_EDA_p2.png)

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

## Model Quality/Approach

* 

('price_log', 2.3346),           ('sqft_above_log', 4.43337),   ('AvgAreaPerRm_log', 2.37103), ('llr2_log', 1.58674),         ('zipcode_yrbuilt_log', 2.21872),
('floors_20', 2.43847),          ('floors_25', 1.04713),        ('floors_30', 1.27247),        ('floors_35', 1.00371),        ('waterfront_1', 1.49368),
('view_1', 1.03778),             ('view_2', 1.09457),           ('view_3', 1.07601),           ('view_4', 1.55319),           ('hasbasement_1', 2.37835),
('hasbiggerllratio_1', 2.11377), ('hasreno4sale_10', 1.04711),  ('hasreno4sale_20', 1.03756),  ('hasreno4sale_50', 1.00923),  ('hasreno4sale_60', 1.00697),
('hasreno4sale_70', 1.00438),    ('yrmo_sold_201411', 1.08528), ('yrmo_sold_201412', 1.08196), ('yrmo_sold_201501', 1.05476), ('yrmo_sold_201503', 1.10304),
('yrmo_sold_201504', 1.11949),   ('yrmo_sold_201505', 1.0369),  ('condition_2', 1.02501),      ('condition_4', 1.41291),      ('condition_5', 1.23033),
('grade_3', 1.3182),             ('grade_4', 1.0235)

*

                            OLS Regression Results                            
==============================================================================
Dep. Variable:              price_log   R-squared:                       0.589
Model:                            OLS   Adj. R-squared:                  0.588
Method:                 Least Squares   F-statistic:                     797.1
Date:                Sat, 25 Jul 2020   Prob (F-statistic):               0.00
Time:                        04:17:55   Log-Likelihood:                -16872.
No. Observations:               17277   AIC:                         3.381e+04
Df Residuals:                   17245   BIC:                         3.406e+04
Df Model:                          31                                         
Covariance Type:            nonrobust                                         
=======================================================================================
                          coef    std err          t      P>|t|      [0.025      0.975]
---------------------------------------------------------------------------------------
Intercept              -0.3222      0.012    -26.943      0.000      -0.346      -0.299
sqft_above_log          0.6270      0.009     68.578      0.000       0.609       0.645
AvgAreaPerRm_log        0.1257      0.008     16.745      0.000       0.111       0.140
llr2_log                0.2106      0.006     35.320      0.000       0.199       0.222
zipcode_yrbuilt_log     0.1141      0.007     15.513      0.000       0.100       0.129
floors_20               0.1592      0.015     10.825      0.000       0.130       0.188
floors_25               0.2668      0.059      4.551      0.000       0.152       0.382
floors_30               0.4645      0.033     13.900      0.000       0.399       0.530
floors_35               0.6094      0.244      2.501      0.012       0.132       1.087
waterfront_1            0.6323      0.072      8.758      0.000       0.491       0.774
view_1                  0.3299      0.041      8.071      0.000       0.250       0.410
view_2                  0.2906      0.025     11.850      0.000       0.243       0.339
view_3                  0.4257      0.034     12.706      0.000       0.360       0.491
view_4                  0.7104      0.049     14.427      0.000       0.614       0.807
hasbasement_1           0.4985      0.012     41.050      0.000       0.475       0.522
hasbiggerllratio_1     -0.1485      0.011    -14.143      0.000      -0.169      -0.128
hasreno4sale_10         0.4315      0.050      8.658      0.000       0.334       0.529
hasreno4sale_20         0.2978      0.056      5.323      0.000       0.188       0.407
hasreno4sale_50        -0.2786      0.114     -2.440      0.015      -0.502      -0.055
hasreno4sale_60        -0.3106      0.157     -1.985      0.047      -0.617      -0.004
hasreno4sale_70        -0.4785      0.228     -2.100      0.036      -0.925      -0.032
yrmo_sold_201411       -0.0369      0.020     -1.829      0.067      -0.076       0.003
yrmo_sold_201412       -0.0467      0.020     -2.359      0.018      -0.086      -0.008
yrmo_sold_201501       -0.0543      0.024     -2.275      0.023      -0.101      -0.008
yrmo_sold_201503        0.0889      0.018      5.018      0.000       0.054       0.124
yrmo_sold_201504        0.1408      0.017      8.527      0.000       0.108       0.173
yrmo_sold_201505        0.1355      0.029      4.628      0.000       0.078       0.193
condition_2            -0.3475      0.056     -6.216      0.000      -0.457      -0.238
condition_4             0.0687      0.012      5.597      0.000       0.045       0.093
condition_5             0.2781      0.020     14.200      0.000       0.240       0.316
grade_3                 0.0575      0.013      4.433      0.000       0.032       0.083
grade_4                 0.2264      0.076      2.993      0.003       0.078       0.375
==============================================================================
Omnibus:                       18.421   Durbin-Watson:                   2.003
Prob(Omnibus):                  0.000   Jarque-Bera (JB):               18.443
Skew:                          -0.080   Prob(JB):                     9.89e-05
Kurtosis:                       3.014   Cond. No.                         74.6
==============================================================================

Warnings:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
