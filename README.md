# sleep-health-lifestyle
# (ongoing project)
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
Initially a simple linear model including only numerical variables was fit.

_This project is still ongoing; more visuals as well as more complex models are being produced and fit to the data._
