# sleep-health-lifestyle
(ongoing project)

Data source: Laksika Tharmalingham
https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset

## Dataset overview
The Sleep Health and Lifestyle Dataset comprises 400 rows and 13 columns, covering a wide range of variables related to sleep and daily habits. It includes details such as gender, age, occupation, sleep duration, quality of sleep, physical activity level, stress levels, BMI category, blood pressure, heart rate, daily steps, and the presence or absence of sleep disorders.

Dataset Columns:
Person ID: An identifier for each individual.
Gender: The gender of the person (Male/Female).
Age: The age of the person in years.
Occupation: The occupation or profession of the person.
**Sleep Duration (hours)**: The number of hours the person sleeps per day.
**Quality of Sleep (scale: 1-10)**: A subjective rating of the quality of sleep, ranging from 1 to 10.
Physical Activity Level (minutes/day): The number of minutes the person engages in physical activity daily.
Stress Level (scale: 1-10): A subjective rating of the stress level experienced by the person, ranging from 1 to 10.
BMI Category: The BMI category of the person (e.g., Underweight, Normal, Overweight).
Blood Pressure (systolic/diastolic): The blood pressure measurement of the person, indicated as systolic pressure over diastolic pressure.
Heart Rate (bpm): The resting heart rate of the person in beats per minute.
Daily Steps: The number of steps the person takes per day.
Sleep Disorder: The presence or absence of a sleep disorder in the person (None, Insomnia, Sleep Apnea).

It is of interest to explore which explanatory variables are associated with sleep quality and sleep duration.

The mean nightly sleep duration for the whole dataset is 7.1 hours, and the mean sleep quality rating is 7.3.

## Data cleaning
The dataset was already very clean. The 'Sleep Disorder' column contained n/a values for observations with no sleep disorder, which were filled with strings instead.

## Exploratory Data Analysis
A correlation heatmap of the numerical variables in the dataset was produced. The highest correlations were found between Sleep Duration and Quality of Sleep (0.88), and Physical Activity Level and Daily Steps (0.77). Coupled with the context of the data, we can confirm that these pairs of variables display multicollinearity and hence should not be used together in formal analysis. There are also strong correlations present between other pairs of variabes, notably Quality of Sleep and Stress Level (-0.9) and Quality of Sleep and Heart Rate (-0.66). 

Using some of the other pairs of variables with moderate correlations, plots were produced to further explore relationships, i.e. Quality of Sleep and Mean Daily Steps. Histograms and boxplots were produced to visualise spread of stress level within occupoations. Certain occupations such as Salesperson and Lawyer have very few observations within the dataset - it may be difficult to draw statistically significant conclusions for these occupations.

## Formal Analysis
The response variable in the formal analysis is Duration of Sleep, rather than Sleep Quality. This is because Sleep Quality was a subjective score given by the observations themselves, so the more objective measure Sleep Duration was preferred. For the same reason, Daily Steps was chosen instead of Physcial Activity Level as the predictor for representing fitness level.Quality of Sleep will also be discounted at this point due to its high correlation (-0.9) with Stress Level, as well as its subjective nature (another rating given by the participants). Only one variable from each of these pairs will be used in the model to avoid complications due to mulitcollinearity.

Initially a multiple linear model including all variables was fit. Looking at the model summary, it seems all variables are statistically significant, and there is no evidence to suggest any of the variables should be dropped, although some levels of the Occupation variable have p-values higher than 0.05. The multiple regression model has an adjusted R<sup>2</sup> value of 0.857. The model satisfies some of the model assumptions such as Normality and absence of multicollinearity, but violates assumptions of linearity and homoscedasticity. Therefore, the next model to fit will be a non-linear model. 

_This project is still ongoing; more visuals as well as more complex models are being produced and fit to the data._
