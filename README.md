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



#### Questions arrising during the analysis (to keep it somewhere)
Is there correlation between the number of suicides and <br>
- geographical location (north VS south, more sunny VS more cloudy)
- religion in the country
- 