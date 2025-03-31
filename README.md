# 1. Project Overview 
Recommendation systems enhance user experiences across e-commerce, streaming, and social media by analyzing historical data to predict relevant content, products, or services. Businesses depend on these systems to boost engagement, satisfaction, and conversions while balancing accuracy, diversity, and scalability. This project applies data-driven techniques to build a personalized recommendation system that efficiently delivers relevant suggestions based on user behavior.

# 2. Objective 
Develop a scalable recommendation system that leverages user interactions to generate personalized suggestions, improve engagement, and optimize business performance. By utilizing historical data and ensuring real-time efficiency, the system will enhance user experience while handling large datasets effectively.

# 3. Project Phases Using the CRISP-DM Methodology
The CRISP-DM framework is a structured approach used to analyze e-commerce data, turning raw information into actionable insights. It guides the process from identifying business challenges to deploying data-driven solutions.

   ## Business Understanding

The goal is to enhance e-commerce platforms by providing personalized recommendations that drive user engagement and increase conversion rates. By analyzing implicit feedback data, the system can predict users' interests based on their past interactions.

  ## Data Understanding

The dataset consists of three files:

**- events.csv :** contains user interactions (views, add-to-carts, transactions). It has 2756101 rows with 4 columns.

Event: This file logs user interactions with items on the e-commerce platform. It includes:

timestamp: When the event occurred

visitorid: A unique identifier for each user
rows
event: The type of interaction (view, addtocart, transaction)

itemid: The unique identifier for the item. There are 235061 unique items in this dataset.

**- item_properties_part1.csv & item_properties_part2.csv :** these files describe item attributes. it contains over 20 million rows and 4 columns, namely; itemid, property, timestamp and value.

**- category_tree.csv :** describes the product hierarchy. it has 1669 rows with 2 columns. That is; the Parentid and the Categoryid.

  ## Data Preparation

This stage outlines the data preparation steps taken to clean, process, and merge the datasets used in the e-commerce recommendation system. The goal of this stage is to ensure data consistency, remove noise, and create a structured dataset ready for feature engineering.

EDA was conducted separately for each dataset to understand data distribution, identify inconsistencies, and derive key insights.

🔹 Events Data (events.csv)
Data Types Check: The dataset had timestamp which was converted to the datetime format, visitorid (int), event (categorical), itemid (int), and transactionid (float, with NaNs since visitors whho did not make any transaction will definetly have no transaction ID).

Duplicates: 406 duplicated rows were detected and dropped. 

Missing values: No missing values were detected in this dataset.

Event Distribution:

<img width="448" alt="image" src="https://github.com/user-attachments/assets/235b6b70-066c-48be-b472-51e6e92cb169" />

The majority of interactions were view events, followed by add-to-cart and then transactions.

Missing Values:
transactionid had missing values for non-transaction events, which was expected. This is because only users who made transactions will be entitled to have a transactionid.

User Behavior Analysis:
A large portion of users had only view events , while some progressed to cart additions and transactions.

🔹 Item Properties (item_properties_part1.csv & item_properties_part2.csv)
Concatenation: Since both files had the same number of columns and identical column names, we concatenated them into a single dataset.

Duplicates and Missing Values: No missing nor duplicates were detected.

Property column: The unique values in this column inluded "available" and "category" whiles the other unique values were numbers. Their corresponding values were put in a different column known as value. In order to make the analysis easier, available and category where mapped with their actual value from the value column.

Value Column Handling:
Numerical values were prefixed with "n", requiring transformation back into numerical format.
Text values were hashed and stemmed, preventing direct interpretation.

Missing Data:
Some items lacked category information, which was resolved using the category tree dataset.

  ## Modeling

  ## Evaluation

  ## Deployment

  ## Tools & Technologies
•	Programming: Python (Pandas, NumPy, Scikit-learn, TensorFlow Recommenders, Surprise)

•	Machine Learning: Collaborative & Content-Based Filtering, Hybrid Models

•	Visualization: Matplotlib, Seaborn.

•	Version Control: Git & GitHub

