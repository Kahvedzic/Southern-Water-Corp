# Southern Water Corp | Python |Jupyter Notebook

<img width="542" alt="Screenshot 2024-10-21 at 2 14 41 PM" src="https://github.com/user-attachments/assets/c6b7d284-1f03-4bac-90c0-b1342a75951d">


# Project Background

Southern Water Corp. is an Israeli water desalination company that sells fresh water for
three customer segments: Residential, Public, and Private. Since the demand for
agricultural and residential use is rising, Southern Water Corp. needed to maximize the
availability of its three desalination plants. In this analysis we will analyze the correlation of PUMP FAILURE (1 or 0) in order to view the implications of pump failures and predict when the next pump failure will occur. 

Insights and recommendations are provided on the following key areas:

* Indicate whether the variable PUMP FAILURE (1 or 0) are failing (1) or behaving normal (0).
* Potential outliers when PUMP FAILURE = 1 (Failure) or PUMP FAILURE = 0 (Normal Behaviour).
* Iterate through dataframe by plotting every variable individually to analyze which variables were most significant to pump failure (1 or 0) for a more streamlined analysis.
* Pump failures over a rolling time period to analyze how the variables move with respect to pump failure.
* Analyze variable correlations against PUMP FAILURE (1 or 0).
* Create OLS regression model that models the PUMP FAILURE(Y-Variable) against all independaent variables.
* Analysis of coefficients to better understand the variables displaying the largest rate of change with respect to PUMP FAILURE.
* Lastly, validate predictions using our regressive model.

Full in-depth project can be found [here](https://github.com/Kahvedzic/Southern-Water-Corp/blob/main/Southern%20Water%20Corp.ipynb) 

Project files can be found [here](https://github.com/Kahvedzic/Southern-Water-Corp/tree/main/Project_Files)

Below consists of major key highlights of entire project.

# Data Structure & Initial Checks

 Overview of the 2 datasets used in analysis:

<img width="1212" alt="Screenshot 2024-10-21 at 2 18 33 PM" src="https://github.com/user-attachments/assets/c11eba14-7d4e-4955-bbcf-5dd0d32e7c5a">


Prior to beginning of analysis, familiarization with the datasets was used for quality control.

# Executive Summary

Overview of findings:

After interpreting correlation coefficients and the use of the linear regression model we created, below is our assessment of the quality of our model. From 9/12/2014 to 10/12/2014, we tested our model with respect to the VOLUMETRIC FLOW METER 2, PUMP EFFICIENY, and HORSE POWER. Our model has performed signficantly well and our test predictions were a success.

<img width="1443" alt="Screenshot 2024-10-21 at 3 07 55 PM" src="https://github.com/user-attachments/assets/4fa0eb78-38dd-4d25-afbc-c88e74921040">




<img width="1253" alt="Screenshot 2024-10-21 at 3 06 10 PM" src="https://github.com/user-attachments/assets/9f6bca16-b9fd-4edf-bf0f-af4da27f7367">


# Insights Deep Dive

Filtered Dataframes with Box Plots - Seeking Potential Outliers:

* It is very likely we will see differences in the overall populations of Pre-Failure vs. Post Failure. To visualise this difference, we separated our datasets, filtering for when the Pump Failure is = 0 or when the Pump Failure =1 and see what trends emerge.
* Using the dataframe_raw dataset, created two boxplots specifically for when the Pump has failed (i.e. Pump Failure = 1) and 0 (Pump is in normal operations).
* Analysis will showcase there are many outliers that exist in our dataset.

<img width="1248" alt="Screenshot 2024-10-21 at 3 23 21 PM" src="https://github.com/user-attachments/assets/239db970-b736-4812-82a8-e0f87f94390d">

<img width="1250" alt="Screenshot 2024-10-21 at 3 23 35 PM" src="https://github.com/user-attachments/assets/7dddee14-c0a4-4300-8452-28a9ea0e745f">



Filtered Dataframes with Box Plots - Outliers Removed:

* As we all know, outliers can easily skew our analysis and we might want to remove them.
* Using the df_raw dataset, below is the result of the calculation of removing the outliers skewing our analysis.
* We see data was removed when PUMP FAILURE = 1.

<img width="1251" alt="Screenshot 2024-10-21 at 4 00 56 PM" src="https://github.com/user-attachments/assets/63bfc52b-972e-4fdc-93c3-8594a157bc40">




Plot and Examine Each Column:

* As you might recall from the earlier plot we had made with the line plot; it was hard to see which variables were the most significant with respect to PUMP FAILURE when all the variables are plotted together.
* This is common when variables are at different scales, the trends can be more challenging to interpret.
* This is why we are going to ITERATE through the dataframe and plot each individual variable out and compare this with the PUMP FAILURE for a more streamlined analysis.

<img width="1457" alt="Screenshot 2024-10-21 at 3 48 55 PM" src="https://github.com/user-attachments/assets/ea7cefda-6d34-4e5c-b0e3-1296b8e9a7c3">

<img width="1461" alt="Screenshot 2024-10-21 at 3 49 45 PM" src="https://github.com/user-attachments/assets/cf93fcb8-6e4e-4548-99aa-ffb5fb17feb3">

<img width="1451" alt="Screenshot 2024-10-21 at 4 04 02 PM" src="https://github.com/user-attachments/assets/3845354f-bfcd-4771-9bed-8c0e3bdf86b7">

<img width="1453" alt="Screenshot 2024-10-21 at 3 50 34 PM" src="https://github.com/user-attachments/assets/e7787428-7776-4fcb-88c3-87f0c62e16d4">



Create a Plot for Pump Failures Over a Rolling Time Period:

* In these next few steps we'll be seeking to better understand how we make use of Pythons powerful inferential statistics and plotting libraries to zoom in on periods of interest that we'd like to examinate further.
* We'll ensure to set the secondary axes as the Pump Failure Variable so we can observe how the variables move with respect to Pump Failure.

<img width="1465" alt="Screenshot 2024-10-21 at 3 57 38 PM" src="https://github.com/user-attachments/assets/cbc2628c-fce3-4475-925e-48ed6f59f98e">

<img width="1459" alt="Screenshot 2024-10-21 at 4 05 50 PM" src="https://github.com/user-attachments/assets/a72593de-9385-4f25-a3d5-65797d10185b">

<img width="1460" alt="Screenshot 2024-10-21 at 3 58 34 PM" src="https://github.com/user-attachments/assets/b125c45c-13f7-4a1a-8db8-4b77a53c80f9">

<img width="1458" alt="Screenshot 2024-10-21 at 3 59 08 PM" src="https://github.com/user-attachments/assets/74762f2e-e187-46d9-abc1-19ea7c8c4c24">

# Conclusion 

We've identified the variables displaying the largest absolute rate of change with respect to PUMP FAILURE.

These 3 variables showcased the strongest relationship with respect to PUMP FAILURE.

- Volumetric Flow Meter
- Pump Efficiency 
- Horse Power

Using the regressive model we created proved to be a success in validating our prediction in viewing the implications when PUMP FAILURE = 1 (Failure).

Full in-depth project can be found again [here](https://colab.research.google.com/drive/1rctNKRh_YetzRpKLH8qhnl6chTQEFSnr#scrollTo=twpkMSnAacwf)

Project files can be found again [here](https://github.com/Kahvedzic/Southern-Water-Corp/tree/main/Project_Files)

# Amar Kahvedzic | Southern Water Corp Analysis | Python 
# Thank you



















  

















