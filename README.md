
Project Overview

To analyze and predict the relationship between pharmaceutical drug usage and associated side effects in patients with various medical conditions. The project aims to monitor and visualize how certain drugs impact health conditions over time using intuitive indicators (e.g., arrow drop up/down icons) to signify trends in side effects or condition severity.
 
Tools Used 

Programming Languages : Python, Machine learning 
Database: SQL  
Spreadsheet Software: Excel  

About Dataset

Data contains details of various drugs (used for conditions like Acne, Cancer,
Heart Disease, etc. ) and their side effects
Drugs detail URLs were collected from following dataset Major Column Descriptors:
generic_name:
The chemical name of the drug (not brand name) drug_classes:
The drug belongs to which drug class, i.e a drug class is a set of medications and other compounds that have a similar chemical structure, the same mechanism of action (i.e. binding to the same biological target), a related mode of action, and/or are used to treat the same disease. brand_names: brand names in which the drugs are being sold or available in the market. activity:
Activity is based on recent site visitor activity relative to other medications in the list. Data was gathered from https://www.drugs.com rx_otc:
Rx-to-OTC switch is the transfer of proven prescription drugs to nonprescription, where
OTC (Over-the-counter) = Medication that can be purchased without a medical prescription
Rx = Prescription Needed
Rx/OTC = Prescription or Over-the-counter.
pregnancy_category:
A	= Adequate and well-controlled studies have failed to demonstrate a risk to the fetus in the first trimester of pregnancy (and there is no evidence of risk in later trimesters).
B	= Animal reproduction studies have failed to demonstrate a risk to the fetus and there are no adequate and well-controlled studies in pregnant women. C = Animal reproduction studies have shown an adverse effect on the fetus and there are no adequate and well-controlled studies in humans, but potential benefits may warrant use in pregnant women despite potential risks. D = There is positive evidence of human fetal risk based on adverse reaction data from investigational or marketing experience or studies in humans, but potential benefits may warrant use in pregnant women despite potential risks. X = Studies in animals or humans have demonstrated fetal abnormalities and/or there is positive evidence of human fetal risk based on adverse reaction data from investigational or marketing experience, and the risks involved in use in pregnant women clearly outweigh potential benefits.
N = FDA has not classified the drug. csa:
Controlled Substances Act (CSA) Schedule
M = The drug has multiple schedules. The schedule may depend on the exact dosage form or strength of the medication.
U = CSA Schedule is unknown.
N = Is not subject to the Controlled Substances Act.
1	= Has a high potential for abuse. Has no currently accepted medical use in treatment in the United States. There is a lack of accepted safety for use under medical supervision.
2	= Has a high potential for abuse. Has a currently accepted medical use in treatment in the United States or a currently accepted medical use with severe restrictions. Abuse may lead to severe psychological or physical dependence. 3 = Has a potential for abuse less than those in schedules 1 and 2. Has a currently accepted medical use in treatment in the United States. Abuse may lead to moderate or low physical dependence or high psychological dependence.
4	= Has a low potential for abuse relative to those in schedule 3. It has a currently accepted medical use in treatment in the United States. Abuse may lead to limited physical dependence or psychological dependence relative to those in schedule 3.
5	= Has a low potential for abuse relative to those in schedule 4. Has a currently accepted medical use in treatment in the United States. Abuse may lead to limited physical dependence or psychological dependence relative to those in schedule 4.
alcohol:
X = Interacts with Alcohol.
rating:
For ratings, users were asked how effective they found the medicine while considering positive/adverse effects and ease of use (1 = not effective, 10 = most effective).
All other columns are self-explanatory.                                                                                                       
Example: You can get the basic idea how you can create a project from here
Here's a beginner-friendly guide to performing data analytics on a dataset involving Drugs, Side Effects, and Medical Conditions. The project will involve exploratory data analysis (EDA) using Python with the specified columns.


Project Title:

Exploratory Data Analysis on Drugs, Side Effects, and Medical Conditions 1. Objective
The goal is to analyze the relationships between drugs, their side effects, and the medical conditions they treat, as well as to explore the ratings and reviews associated with these drugs.
2. Dataset Overview
The dataset contains the following columns:
●	drug_name: Name of the drug.
●	medical_condition: The condition the drug is used to treat.
●	side_effects: Common side effects of the drug.
●	generic_name: The generic name of the drug.
●	drug_classes: The class of the drug (e.g., antibiotic, antihistamine).
●	brand_names: Brand names under which the drug is sold.
●	activity: The activity of the drug (e.g., active, inactive).
●	rx_otc: Indicates if the drug is prescription (Rx) or over-the-counter (OTC).
●	pregnancy_category: The drug's pregnancy risk category.
●	csa: Controlled Substances Act schedule, if applicable.
●	alcohol: Interactions with alcohol.
●	related_drugs: Other drugs related to the primary drug.
●	medical_condition_description: A brief description of the medical
condition.
●	rating: Average user rating of the drug.
●	no_of_reviews: Number of user reviews.
●	drug_link: URL link to more information about the drug.
●	medical_condition_url: URL link to more information about the medical
condition.
3.	Tools Required
●	Python: The primary programming language for data analysis.
●	Pandas: For data manipulation and analysis.
●	Matplotlib/Seaborn: For data visualization.
●	Jupyter Notebook: To write and run Python code.
4.	Step-by-Step Guide
Step 1: Import Libraries                                                                                    import pandas as pd                                           import matplotlib.pyplot as plt                             import seaborn as sns
Step 2: Load the Dataset                                                                                                                      # Load your dataset df = pd.read_csv('path_to_your_dataset.csv')
# Display the first few rows of the dataset df.head()
Step 3: Data Cleaning
●	Check for missing values:
# Check for missing values df.isnull().sum()
●	Handle missing values:
	○	Drop or fill missing values depending on the context.
# Example: Drop rows with missing values df_cleaned = df.dropna()
# Or fill missing values with a placeholder df_filled = df.fillna('Unknown')
Step 4: Basic Data Exploration ● Summary statistics:
# Summary statistics
df.describe()
●	Distribution of Ratings:
# Distribution of drug ratings plt.figure(figsize=(10, 6)) sns.histplot(df['rating'], bins=10, kde=True) plt.title('Distribution of Drug Ratings') plt.xlabel('Rating') plt.ylabel('Frequency') plt.show()
Step 5: Analyzing Relationships ● Top Drugs by Condition:
# Count the most common drugs for each medical condition top_drugs = df.groupby('medical_condition')['drug_name'].value_counts().nla rgest(10) print(top_drugs)
●	Side Effects Analysis:
# Analyzing the most common side effects side_effects = df['side_effects'].value_counts().head(10) print(side_effects)
●	Drug Ratings by Class:
# Boxplot of ratings by drug class plt.figure(figsize=(12, 8)) sns.boxplot(x='drug_classes', y='rating', data=df) plt.xticks(rotation=90) plt.title('Drug Ratings by Class') plt.show()
Step 6: Conclusion
●	Summarize findings:
	○	Identify any trends or patterns in the data.
○	Discuss how certain drug classes or conditions are associated with specific side effects or ratings.
5.	Next Steps
●	Advanced Analysis: Perform more sophisticated statistical tests or machine learning techniques.
●	Reporting: Create a report or presentation to share the findings.
6.	Example Output

●	Distribution of Drug Ratings:
○	A histogram showing how drug ratings are distributed, with peaks at certain rating values.
●	Top Drugs for a Condition:
○	A list or bar chart showing the most commonly prescribed drugs for a particular condition.
●	Side Effects Analysis:
○	A list of the most common side effects reported in the dataset.
By following this guide, a beginner can start exploring and analyzing the dataset effectively. Let me know if you need further assistance!

