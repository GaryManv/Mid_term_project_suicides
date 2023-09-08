# Mid_term_project_suicides

#### Dataset selection
The "Suicide Rates Overview 1985 to 2016" dataset was chosen because it intrigued all collaborators due to its interesting nature.<br> Upon initial examination, the data appeared to be effectively compiled, revealing interesting patterns.<br>  Furthermore, the prospect of mitigating the increasing trend in suicide rates was found to be motivating.<br><br>

#### Collaborative Work on GitHub
In our project, we're using GitHub to work together with classmates. To make things easier, we decided to keep two separate files for each stage of the project. Everyone works on their own version, and we update them based on what we learn from each other. When a project stage is finished, we'll keep the main file in the main folder and move the working files to an archive folder.

#### EDA
*  The dataset was consist of 27820 rows and 12 columns. There were 19456 nulls in "HDI for year" column. It's 70% from the total quantity.Taking into consideration the importance of HDI index it was repleaced with mean values.
*  Main statistical data didn't show significant outliers, except that 'suicides/100k pop maximum' of 224.97 seems a little bit high and suspishious.
*  Some columns are sourced from the others: 
   - columns 'country', 'year' = column 'country-year'
   - categorical column 'age' = categorical column 'generation' 
*  There are missing years in rows. Probably use of only countries with continues years will give more effective results? Question without answer at the moment. But list of that countries was created.
*  Visuals didn't show any interesting patterns

#### Modeling
*  Reshape the dataframe, pivoting columns values with categorical data into columns with 'suicides/100k pop' to make multivariable regression model
* Different attemnts with many, then 2, then 1 variable didn't get a linear model fitting to our data.All models fail the linear regression assumptions : normality and Homoscedasticity.


#### Vizaulizations (Tableau)
*  created 9 vizuals with different chart types and one dashboard with combined data about suicides 

#### Challenges
*  Developing a linear regression model to fit the dataset did not yield the anticipated outcomes.
The following attempts were processed:
- 1. The model with all variables shows strong multicollinearity problem.It did not meet the assumptions of linear regression regarding normality (Shapiro-Wilk test) and homoscedasticity (Breusch-Pagan test), as the residuals were found to deviate from a normal distribution.<br> Based on the correlation matrix, it was determined to remove columns related to age and gender ranges <BR>
    
- 2. The model with 2 independent variables shows better results ( R was 0.054) but still indicates multicollinearity or other numerical problem in the  OLS Regression Results. Again, the model didn't meet linear regression assumptions.<br>
 
- 3. The model with only one independent variable shows worse result (R=0).LR assumptions didn't apply to the model.<br>
    
- 4. Same as No3 with droped rows for a columns with 0 suicides per country (small quantity , just 13 over 697). No changes to results.
    
- 5. Model No. 2, which was considered the best among all models, incorporated a normalized 'gdp_per_capita' variable through logarithmic and Box-Cox transformations. This adjustment yielded slightly improved results (R=0.058). Notably, there were no warning notes in the OLS Regression Results report. However, despite the residual plots appearing closer to a normal distribution, the results of the Shapiro-Wilk test led to the rejection of linear regression assumptions.<br>
    
<b>In conclusion, the overall outcome indicates that we were unable to identify a linear regression model suitable for our dataset.</b>

- 6. Just a try for logaritmic model because of kinda logaritmic shape on the scatter plot.Didn't have time to go deeper.
    
- 7. Other challenges: understanding pushing and pulling files in GITHUB took a lot of time and trials
    
    
#### Files description
*  EDA_and_Modeling_GM.ipynb : includes analyses of main data, cleaning, dealing with missing values, simple visualizations and linear regression models
*  Suicide_overview_1985_to_2016.csv : main dataset taken from kaggle (https://www.kaggle.com/datasets/russellyates88/suicide-rates-overview-1985-to-2016). 
*  reshaped_suicide_overview_1985_to_2016.csv: reshaped dataset. That is to say : <br>
*  removed columns with identical meaning
*  grouping rows per country, year and gpd_per_capita
*  pivoting 'age' and 'sex' to many columns with names as values from 'age' and 'sex' and values corresponding to  "'suicides/100k pop'" for the row
    
*  Suicides_overview_per_country1985-2015.pdf: final Tableau dashboard in pdf format
*  Suicides_overview_per_country1985-2015.twbx: final Tableau file in twbx format
