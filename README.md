# Google-Data-Analytics-Capstone-2-How-Can-Bellabeat-A-Wellness-Technology-Company-Play-It-Smart-
Case Study from Google Data Analytics Certification
# INTRODUCTION

I have recently signed up for the Google Data Analyst Certificate course on Coursera. In this capstone project (project 2), I examine data from Bellabeat, a company in the wellness technology sector. The aim is to tackle a company-related issue using the methodology we learned in the program: Ask, Prepare, Process, Analyze, Share, and Act. This document serves as my response to one of the capstone projects included in the course. I utilized Microsoft Excel, SQL (via BigQuery), and Tableau Public throughout this project.

# ABOUT THE COMPANY

Established in 2013, Bellabeat is an innovative firm that designs health-oriented smart products aimed specifically at women. The company has experienced rapid growth and has effectively positioned itself as a tech-focused wellness brand for women. By gathering data on physical activity, sleep patterns, stress levels, and reproductive health, Bellabeat empowers women with insights into their health and habits. Through the analysis of data collected from their Fitness Tracker App, Bellabeat aspires to uncover further avenues for growth.

# COMPANY PRODUCTS:

## 1. Bellabeat App: 
The Bellabeat app provides users with health-related data concerning their activity, sleep, stress levels, menstrual cycle, and mindfulness practices. This information helps users better comprehend their current behaviors and make healthier choices. The app seamlessly integrates with Bellabeat’s range of smart wellness devices.

## 2. Leaf: 
This classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf connects to the Bellabeat app, enabling users to monitor their activity, sleep, and stress levels.

## 3. Time: 
This wellness watch merges the timeless design of a classic timepiece with advanced technology to track user activity, sleep, and stress. The Time watch syncs with the Bellabeat app, offering insights into daily wellness.

## 4. Spring:
A smart water bottle that tracks daily hydration to ensure users stay adequately hydrated throughout the day. The Spring bottle also connects to the Bellabeat app for hydration monitoring.

## 5. Bellabeat Membership: 
Bellabeat provides a subscription-based membership program that offers users continuous access to fully personalized advice on nutrition, activity, sleep, health and beauty, and mindfulness, tailored to their lifestyle and objectives.

# BUSINESS TASK
The objective is to analyze data on smart device usage to uncover new growth opportunities. Based on these insights, the founders seek high-level recommendations on how these trends can shape Bellabeat’s marketing strategy.

## STAKEHOLDERS FOR THIS PROJECT
**1. Urška Sršen**: Co-founder and Chief Creative Officer of Bellabeat.

**2. Sando Mur**: Mathematician and co-founder of Bellabeat, an essential member of the executive team.

**3. Bellabeat Marketing Analytics Team**: A team of data analysts dedicated to collecting, analyzing, and reporting data that guides Bellabeat’s marketing strategies.

# ASK
The goal is to analyze the usage data of smart devices to gain insights into how consumers utilize non-Bellabeat devices.

# PROCESSING THE DATA
The data for this project was sourced from public datasets provided by MÖBIUS on Kaggle. You can download it [here](insert link). This Kaggle dataset includes personal fitness tracker information from 30 Fitbit users. Thirty eligible Fitbit users consented to share their personal tracker data, which includes minute-by-minute outputs for physical activity, heart rate, and sleep monitoring. It encompasses details about daily activity, steps taken, and heart rate, useful for examining user habits.

An effective data source should meet the ROCCC criteria: Reliable, Original, Comprehensive, Current, and Cited.

**1. Reliable**: LOW — Limited reliability due to only 30 respondents; Fitbit has around 30 million users (Article release date: August 2023).

**2. Original**: LOW — Data is publicly available from Kaggle.

**3. Comprehensive**: MED — Parameters align with most of Bellabeat’s product features.

**4. Current: LOW** — The data is from 2016, which may render it outdated.

**5. Cited: LOW** — Data was collected by a third party.

### In summary, this dataset is considered low quality, and it is inadvisable to base business recommendations solely on it.

After reviewing the data, I utilized seven CSV files:

**1. dailyActivity_merged (Data cleaning and manipulation using Excel)**

**2. dailyCalories_merged (Data cleaning and manipulation using Excel)**

**3. dailyIntensities_merged (Data cleaning and manipulation using Excel)**

**4. dailySteps_merged (Data cleaning and manipulation using Excel)**

**5. heartrate_seconds_merged (Data cleaning and manipulation using SQL BigQuery)**

**6. sleepDay_merged (Data cleaning and manipulation using Excel)**

**7. weightLoginfo_merged (Data cleaning and manipulation using Excel)**

![blabla](https://github.com/user-attachments/assets/5cee4607-4f88-4402-9ad3-31c780279e31)

Summary table of data cleaning

### Summary of Data Cleaning
For data cleaning and manipulation in Microsoft Excel:

**1. ID String Count: I employed the =LEN() function in Excel to determine the total number of IDs.**

**2. Total ID Recorded: I copied all IDs into a new column, then used the Data tab to remove duplicates, resulting in the total recorded IDs for that dataset.**

**3. Format Issues: The selected files had formatting issues with date/time; I used the "Text to Columns" feature in Excel to separate date and time, changing the format to DMY.**

**4. Duplicates: Only two files contained duplicates; I used the Data tab to remove these.**

**5. Null Values + Empty Rows: I checked for NULL/BLANK values using the Filter feature in Data. If the filter revealed (blanks), it indicated the presence of blank values.**

**6. Inconsistent Data: Some files had issues with decimal points; I standardized this to two decimal places for all data.**

**7. Additional: I created a new table called "what_day" by combining the WEEKDAY formula with the IF formula to automatically generate day names using =IF(WEEKDAY(cells,1) = 1, ‘Sunday’, IF(WEEKDAY(cells,1) = 2, ‘Monday’, …)).**

### For data cleaning and manipulation in Google BigQuery SQL:

During the data file upload in BigQuery, I encountered an error. To resolve this, I added fields under “SCHEMA,” specified the Field name, and adjusted the Field Type (STRING for text, INTEGER for numbers, etc.).

**1. Split date and time into separate columns:**

![1](https://github.com/user-attachments/assets/14107a6f-5703-4885-a135-3be8c3aca087)

**2. Identify duplicates and create a table if duplicates are found:**

![2](https://github.com/user-attachments/assets/c7fb75ac-93ee-4b4e-8f37-0be00cfb95a1)

If the query above shows duplicates, use this query to create a new table without duplicates:

![3](https://github.com/user-attachments/assets/69372f6f-fa1b-4566-8283-588602779914)

**3. Find NULL values:**

![4](https://github.com/user-attachments/assets/3eae428f-a221-476c-b3d2-1cae6532ec22)

**4. Check the length of recorded IDs:**

![5](https://github.com/user-attachments/assets/b8bb41bb-8dfd-4712-952f-1c4d15c08ff7)

# ANALYZE THE DATA

In this stage, my data is primed for visualization. This part is focused on visualizing the insights we've uncovered and discussing our conclusions. I utilized BigQuery for processing and Tableau Public for visualization.

![dupdup](https://github.com/user-attachments/assets/0c7dc29b-61cc-44ff-bc53-8fe295f4f47f)

Bar Chart above represents average of distance (in kilometer) compare to day of users doing their workout. The most distance is in saturday then tuesday.

![khkh](https://github.com/user-attachments/assets/66ede828-a37d-49c4-8a05-1e189a20271f)

Bar Chart above represents average of steps compare to day. The most distance is in saturday. This chart result is connected to chart above because the most average steps take in saturday then tuesday, same result like the most average distance.

## Visualizing Peak Calories and Average Calories per User.

![qwqw](https://github.com/user-attachments/assets/16ff5054-de79-44ef-900b-4bf520908bbd)

This chart shows that ID number 6117666160 doing the most workout by calories but not often doing workout so the numbers of average is going down, but if we see ID number 8877689391 is stable doing hard workout and often so the number average is pretty high also.

## Percentage of Users

![xdxd](https://github.com/user-attachments/assets/089001fe-3483-4831-9cca-bdfdbb3fcf2f)

As seen from the pie chart above,

1. Percentage Sedentary minutes takes the biggest part at 81.33%.

2. This indicates that users are using the app to log daily activities such as daily commute, inactive movements (moving from one spot to another) or running errands.

3. App is rarely being used to track fitness (example: running) as per the minor percentage of fairly active activity (1.11%) and very active activity (1.74%). This is highly discouraging as FitBit app was developed to encourage fitness.

## Sleep Analysis User by Time

![fffff](https://github.com/user-attachments/assets/946d81cc-79bb-4867-99dd-68989f778464)

As seen from the pie chart above, that is comparison between Total Hour A Sleep and Total Hour in Bed, it’s normal the orange one is higher than blue one because people won’t immediately go sleep when they get in bed. Usually adult people sleep in range between 7 to 8 hours. The data shows that the result is fulfil the sleep needs for adult people but few users didn’t use BellaBeat in their sleep so this can be a suggestion to make wearable device that is comfortable enough so people can wear it in their sleep.


### Visualization Insights

**1. Average Distance Compared to Day:**
 The bar chart depicts the average distance (in kilometers) covered by users on different days. Saturdays show the highest distance, followed by Tuesdays.

**2. Average Steps Compared to Day:**
Another bar chart illustrates the average number of steps taken by users throughout the week, with Saturdays again leading in step count. This result aligns with the average distance data.

**3. Peak and Average Calories per User:**
This chart reveals that user ID 6117666160 burns the most calories through workouts but does not exercise frequently, leading to a lower average. In contrast, ID 8877689391 maintains a stable workout routine, resulting in a high average calorie burn.

**4. User Activity Percentage:**
The pie chart indicates that sedentary minutes constitute the largest segment at 81.33%, suggesting that users predominantly use the app for logging daily activities like commuting and minimal movements, rather than for tracking fitness workouts, which is concerning as the Fitbit app aims to promote fitness.

**5. Sleep Analysis:**
The pie chart comparing total hours of sleep versus total hours spent in bed illustrates that the orange segment (hours in bed) is higher than the blue segment (hours asleep). This is typical, as individuals usually take time to fall asleep. The data suggests that most users are meeting the recommended sleep duration, but some may not utilize the Bellabeat device for sleep tracking, indicating a potential area for improvement in comfort.

# ACT

It’s now time to summarize the main findings and propose recommendations for Bellabeat's stakeholders, allowing for data-driven decision-making for the company's future.

# Key Findings

1. Activity Peaks on Saturdays and Tuesdays: Most physical activity occurs on these days, which is reflected in both average distance covered and steps taken.

2. Fitness Tracking vs. Routine Use: Only a few users are utilizing the FitBit app for its intended fitness-tracking purpose. Many are logging daily routines instead. Bellabeat could launch a campaign encouraging users to leverage the app more for tracking workouts.
   
3. Sedentary Behavior Dominates: A significant 81.3% of recorded activity minutes are sedentary. This indicates users are primarily using the app to monitor daily activities like commuting or minor movements, rather than for active fitness tracking such as running or exercise.
   
4. Sleep Data: According to CDC guidelines, most users are getting sufficient sleep. However, a portion of users do not track their sleep, suggesting the need for a more comfortable device to be worn during sleep.

# My Recommendations as a Junior Data Analyst:

1. Promote Fitness-Tracking Functionality: Based on the analysis, I suggest a marketing campaign to encourage Bellabeat users to track their fitness activities more actively, rather than using the device as a fashionable accessory.
   
2. Design Comfortable and Stylish Products: To boost daily wearability, Bellabeat should focus on creating devices that are both aesthetically appealing and comfortable for continuous use, especially during sleep.
   
4. Address Sedentary Use: Users primarily track routine movements rather than physical exercise. Bellabeat should highlight underused fitness-tracking features by conducting research into competitors' functions, such as sleep, heart rate, and weight monitoring. This could position Bellabeat as a health ecosystem with interconnected devices, such as smartwatches, rings, and scales.
   
5. Target New Customer Segments: While most Fitbit users are working professionals with 9-to-6 jobs, Bellabeat can expand its user base by exploring the preferences of other groups. For example, introducing reminders to stand, hydrate, or move for users who are sedentary for extended periods could broaden appeal. At the same time, Bellabeat should continue supporting its current working-class audience through targeted marketing.
   
6. Enhance the App: Further app development could provide users with additional features like workout reminders, water intake alerts, and other healthy habit prompts.
   
# Additional Considerations:

The dataset used is not comprehensive enough (failing to meet the ROCCC standards), which limits the scope of our analysis. With only 33 users, the sample size is too small to provide actionable insights, making it necessary to gather more user data before drawing broader conclusions and implementing decisions.
