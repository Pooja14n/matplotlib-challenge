# matplotlib-challenge

![pexels-rfstudio-3825458](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/1e068394-c783-4ef9-9a69-00b5a1ecf857)

Pymaceuticals, Inc., a new pharmaceutical company that specializes in anti-cancer medications recently screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer. 

As a senior data analyst at the company, the executive team needs help with generating all of the tables and figures needed for the technical report of the clinical study and have asked for a top-level summary of the study results. Access has been given to the complete data from their most recent animal study. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

# Requirements
Pandas, Jupyter Notebook and Matplotlib to create a report that includes data as elaborated below. And, a report with at least three observations or inferences that can be made from the figures and tables that are generated based on the 2 datasets proveded.

# Prepare the Data
1. Run the provided package dependency and data imports, and then merge the `mouse_metadata` and `study_results` DataFrames into a single DataFrame.

2. Display the number of unique mice IDs in the data, and then check for any mouse ID with duplicate time points. Display the data associated with that mouse ID, and then create a new DataFrame where this data is removed. Use this cleaned DataFrame for the remaining steps.
![1](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/5aca198e-199e-4d6c-a63f-9f702e5ee60b)

3. Display the updated number of unique mice IDs.

# Generate Summary Statistics
Create a DataFrame of summary statistics. 
The summary statistics should include:

  a. A row for each drug regimen. These regimen names should be contained in the index column.
![4](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/a0df9ec1-2808-448e-8329-d5831f3ad6a9)

  b. A column for each of the following statistics: mean, median, variance, standard deviation, and SEM of the tumor volume.
![5](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/ff30f539-2ae9-4613-8111-3c207db3285d)

# Create Bar Charts and Pie Charts
1. Generate two bar charts. Both charts should be identical and show the total total number of rows (Mouse ID/Timepoints) for each drug regimen throughout the study.

  a. Create the first bar chart with the Pandas DataFrame.plot() method.
![6](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/449f063a-b315-497e-838f-2845c442d990)

  b. Create the second bar chart with Matplotlib's pyplot methods.
![7](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/5bca0180-505d-4dab-89d0-96d6bbaf03c5)

2. Generate two pie charts. Both charts should be identical and show the distribution of female versus male mice in the study.

  a. Create the first pie chart with the Pandas DataFrame.plot() method.
![8](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/c2b1f239-011e-4261-99c7-324b7b5095a1)

  b. Create the second pie chart with Matplotlib's pyplot methods.
![9](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/ff507db4-21e2-4b60-b040-1f2efaca96e5)

# Calculate Quartiles, Find Outliers, and Create a Box Plot
1. Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, calculate the quartiles and IQR, and determine if there are any potential outliers across all four treatment regimens. Use the following substeps:

  a. Create a grouped DataFrame that shows the last (greatest) time point for each mouse. Merge this grouped DataFrame with the original cleaned DataFrame.
![10](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/e832ef09-4bb6-4141-8590-200dae560ab8)

  b. Create a list that holds the treatment names as well as a second, empty list to hold the tumor volume data.

  c. Loop through each drug in the treatment list, locating the rows in the merged DataFrame that correspond to each treatment. Append the resulting final tumor volumes for each drug to the empty list.

  d. Determine outliers by using the upper and lower bounds, and then print the results.
![11](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/93603e83-4a6d-4284-bb84-fee72a2a4826)

2. Using Matplotlib, generate a box plot that shows the distribution of the final tumor volume for all the mice in each treatment group. Highlight any potential outliers in the plot by changing their color and style. All four box plots should be within the same figure.
![12](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/ee05d14b-185b-4c73-9ba8-dc34c41325dd)

# Create a Line Plot and a Scatter Plot
1. Select a single mouse that was treated with Capomulin, and generate a line plot of tumor volume versus time point for that mouse.
![13](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/c2f62b3e-dd59-4e82-a900-8e232adca5fc)

2. Generate a scatter plot of mouse weight versus average observed tumor volume for the entire Capomulin treatment regimen.
![14](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/394300ae-601b-44ef-ae9e-13ad09a1df3a)

# Calculate Correlation and Regression
1. Calculate the correlation coefficient and linear regression model between mouse weight and average observed tumor volume for the entire Capomulin treatment regimen.

2. Plot the linear regression model on top of the previous scatter plot.
![15](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/65561dae-ecbc-438c-801d-f7cfda76195a)

# Note
Initial steps carried out prior to coding are:

1. Dependencies and Setup:
  a. `import matplotlib.pyplot as plt`
  b. `import pandas as pd`
  c. `import scipy.stats as st`
  d. `from scipy.stats import sem`
  e. `from scipy.stats import linregress`
  f. `import numpy as np`
2. Study data files:
  a. `mouse_metadata_path = "data/Mouse_metadata.csv"`
  b. `study_results_path = "data/Study_results.csv"`
3. Read the mouse data and the study results: 
  a. `mouse_metadata = pd.read_csv(mouse_metadata_path)`
  b. `study_results = pd.read_csv(study_results_path)`
4. Combine the data into a single DataFrame:
    `combined_df = pd.merge(mouse_metadata, study_results, how='right')`
5. Display the data table for preview;
    `combined_df = combined_df[['Mouse ID', 'Timepoint', 'Tumor Volume (mm3)', 'Metastatic Sites','Drug Regimen', 'Sex', 'Age_months', 'Weight (g)']]`
   combined_df.head()

# References
Referred to various class activity exercises, got support from Assistant Instructor, other peers, and websites for: Pandas Documentation, Stack Overflow, Matplotlib Documentation.

# Files submitted including this README File
1. Folder -> Pymaceuticals
   a. data folder -> two Datasets provded for the analysis: a. Mouse_metadata.csv b. Study_results.csv
   b. Jupyter Notebook that contains the main script to run for analysis and the report that includes a written description of at least three observations based on the data -> pymaceuticals_starter.ipynb
