# Southern Water Corp Using Python (Jupyter Notebook)

<img width="542" alt="Screenshot 2024-10-21 at 2 14 41 PM" src="https://github.com/user-attachments/assets/c6b7d284-1f03-4bac-90c0-b1342a75951d">


# Project Background

Souther Water Corp. is an Israeli water desalination company that sells fresh water for
three customer segments: Residential, Public, and Private. Since the demand for
agricultural and residential use is rising, Southern Water Corp. needed to maximize the
availability of its three desalination plants. In this analysis we will analyze the correlation in PUMP FAILURE (1 or 0) in order to minimize pump failures and predict when and why the next pump failure will occur. 

Insights and recommendations are provided on the following key areas:

* Indicate whether the variable PUMP FAILURE (1 or 0) are failing (1) or behaving normal (0).
* Potential outliers when PUMP FAILURE = 1 (Failure) or PUMP FAILURE = 0 (Normal Behaviour).
* Iterate through dataframe by plotting every variable individually to analyze which variables were most significant to pump failure (1 or 0) for a more streamlined analysis.
* Pump failures over a rolling time period to analyze how the variables move with respect to pump failure.
* Analyze variable correlations against PUMP FAILURE (1 or 0).
* Create OLS regression model that models the PUMP FAILURE(Y-Variable) against all independaent variables.
* Analysis of coefficients to better understand the variables displaying the largest rate of change with respect to PUMP FAILURE.
* Lastly, validate predictions using our regressive model.

The analysis using Python to clean, organize, and prepare data to create the insights we need can also be found [here](https://github.com/Kahvedzic/Southern-Water-Corp/blob/main/Southern%20Water%20Corp.ipynb)

Project files can also be found [here](https://github.com/Kahvedzic/Southern-Water-Corp/tree/main/Project_Files)

# Data Structure & Initial Checks

 Overview of the 2 datasets used in analysis:

<img width="1212" alt="Screenshot 2024-10-21 at 2 18 33 PM" src="https://github.com/user-attachments/assets/c11eba14-7d4e-4955-bbcf-5dd0d32e7c5a">


Prior to beginning of analysis, familiarization with the datasets was used for quality control.

# Executive Summary

Overview of findings

After interpreting correlation coefficients and the use of the linear regression model we created, below is our assessment of the quality of our model. From 9/12/2014 to 10/12/2014, we tested our model with respect to the VOLUMETRIC FLOW METER 2, PUMP EFFICIENY, and HORSE POWER. Our model has performed signficantly well and our test predictions were a success.

<img width="1443" alt="Screenshot 2024-10-21 at 3 07 55 PM" src="https://github.com/user-attachments/assets/4fa0eb78-38dd-4d25-afbc-c88e74921040">




<img width="1253" alt="Screenshot 2024-10-21 at 3 06 10 PM" src="https://github.com/user-attachments/assets/9f6bca16-b9fd-4edf-bf0f-af4da27f7367">


# Insights Deep Dive

Filtered Dataframes with Box Plots

* It is very likely we will see differences in the overall populations of Pre-Failure vs. Post Failure. To visualise this difference, we should separate our datasets, filtering for when the Pump Failure is = 0 or when the Pump Failure =1 and see what trends emerge.
* This will require subsetting our dataframes
* Using the dataframe_raw dataset, create two boxplots specifically for when the Pump has failed (i.e. Pump Failure = 1) and 0 (Pump is in normal operations)

<img width="1248" alt="Screenshot 2024-10-21 at 3 23 21 PM" src="https://github.com/user-attachments/assets/239db970-b736-4812-82a8-e0f87f94390d">

<img width="1250" alt="Screenshot 2024-10-21 at 3 23 35 PM" src="https://github.com/user-attachments/assets/7dddee14-c0a4-4300-8452-28a9ea0e745f">
















