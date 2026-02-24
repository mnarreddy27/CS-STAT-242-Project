 ## CS/STAT 242 Project 


This project analyzes the frisk.csv dataset to explore the nature of NYPD stops and the scrutiny of the New York City police department's policy of stop and frisk. 
The main controversy was racial profiling and unfair targeting by the police.
The objective is to dive deeper and see what specific variables affected police stops the most by exploring multiple variables, and see if there was truly evidence of racias bias in NYPD police stops.

## About the Dataset

The dataset includes recordings of NYPD stops for a fifteeen month period in 1998-1999.
The variables contained are:
- precint: NYC precint indicator, with values 1, 2, . . . , 75.
- eth: Ethnicity indicator, with 1 denoting Black, 2 denoting Hispanic, and 3 denoting White.
- popl: The total population of a particular ethnicity in a given precint.
- crime: Crime category indicator, with 1 denoting violent crimes, 2 denoting weapons crimes, 3 denoting property crimes, and 4 denoting drug crimes.
- stops: Number of police stops for a specific crime category among individuals of a particular ethnicity in a given precint.
- past: The total number of past arrests for a specific crime category among individuals of a particular ethnicity in a given precint.

Later added to the dataset after manipulation:

- black, hispanic, white: These are a one-hot encoding of the column eth. For example, if eth was 1 the three values would be 1,0,0 respectvively.
- If eth was 2 the three values would be 0,1,0 respectively. If eth was 3 the three values would be 0,0,1 respectively. 
- logstops: the logarithmic value of number of police stops for a specific crime category among individuals of a particular ethnicity in a given precint.
- logpopl:  the logarithmic value of the total population of a particular ethnicity in a given precint.
- logpast: the logarithmic value of the total number of past arrests for a specific crime category among individuals of a particular ethnicity in a given precint.

Other smaller dataframes were created from frisk.csv and briefly used.


## Project Structure
The project undertakes these steps:

- Data Cleaning and Manipulation
- Visualization
- Modeling and Model Analysis
- Exploratory Data Analysis
- K-Fold Cross Validation
- Conclusion

## Key Findings
 Out of the 5 models derived to predict total number of police stops, the one that was deemed the best by cross-validation to predict stops was stops vs (population size + past arrests + black ethnicity + hispanic ethnicity).
  The coefficient of black gives the change in the number of stops if that ethnicity were a black instead of a white, for the same population size and past arrests. The same goes for the hispanic coefficient.
  The white ethnicity isn't an input as the goal is to see how the other two ethnicities compare to white as a baseline. The idea is if the hispanic and black coefficients were close to zero, there would be no evidence of
  police bias in the dataset. Ultimately, after running the regression and getting the coefficients, they were significantly larger than zero which indicates heavy raciasl bias in police stops. When population size and past
  arrests are controlled, black and hispanic people were stopped much more often than white people. 


## Technologies Used
- Python
- pandas
- numpy
- matplotlib 
- statsmodels.formula.api
- Jupyter Notebook

