Railway Ticket Data Exploratory Data Analysis (EDA) 🚆
Project Overview 🌟
This repository contains an Exploratory Data Analysis (EDA) project conducted on a railway ticket dataset. The project aims to uncover patterns, trends, and insights related to train ticket purchases, travel durations, delays, and other key features. The analysis leverages Python libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Plotly to perform data cleaning, feature engineering, and visualization.

The notebook (EDA_Project.ipynb) provides a comprehensive analysis of railway ticket transactions, focusing on relationships between purchase times, travel durations, ticket types, railcard usage, and journey outcomes (e.g., delays and cancellations). This project serves as a valuable resource for understanding passenger behavior and operational performance in the railway system.

Dataset Description 📊
The dataset (railway.csv) contains 31,653 records of railway ticket transactions with 18 columns. Each record represents a ticket purchase and includes details about the transaction, journey, and outcome. Below is a summary of the key columns:

Transaction_ID: Unique identifier for each transaction.
Date_Purchase, Time_Purchase: Date and time of ticket purchase.
Purchase_Type: Method of purchase (Online or Station).
Payment_Method: Payment type (e.g., Credit Card, Contactless).
Railcard: Type of railcard used (e.g., Adult, Disabled, or NaN for none).
Ticket_Class: Class of travel (Standard or First Class).
Ticket_Type: Type of ticket (e.g., Advance, Off-Peak).
Price: Ticket price in GBP.
Departure_Station, Arrival_Destination: Journey start and end stations.
Journey_Date, Departure_Time, Arrival_Time: Scheduled journey details.
Actual_Arrival_Time: Actual arrival time of the train.
Journey_Status: Status of the journey (On Time, Delayed, Cancelled).
Delay_Reason: Reason for delay (if applicable).
Refund_Request: Whether a refund was requested (Yes/No).
The dataset covers transactions from December 2023 to April 2024 and includes journeys across various UK stations, such as London Paddington, Liverpool Lime Street, and York.

Objectives 🎯
The primary objectives of this EDA project are:

Data Cleaning: Handle missing values, inconsistent formats, and erroneous entries to ensure data quality.
Feature Engineering: Create new features (e.g., travel duration, purchase hour, delay minutes) to facilitate analysis.
Pattern Identification: Explore relationships between ticket prices, travel durations, purchase times, and journey outcomes.
Visualization: Generate interactive and static visualizations to communicate insights effectively.
Correlation Analysis: Investigate correlations between numerical features to understand dependencies.
Methodology 🛠️
The analysis is structured into three main code cells in the Jupyter Notebook:

Data Loading and Initial Exploration:
The dataset is loaded using Pandas from railway.csv.
A preliminary view of the data is displayed to understand its structure and content.
Interactive Scatterplot Analysis:
Data Cleaning: Missing values in Actual_Arrival_Time and Delay_Reason are handled based on Journey_Status. For example, cancelled journeys are marked as "Journey Cancelled," and on-time journeys with missing delay reasons are assigned "No Delay."
Feature Engineering:
Travel_Duration: Calculated as the difference between Arrival_Time and Departure_Time (in hours), with adjustments for overnight journeys.
Purchase_Hour: Extracted from Time_Purchase as a fractional hour for precise temporal analysis.
Visualization: An interactive scatterplot is created using Plotly Express, plotting Purchase_Hour against Travel_Duration, colored by Railcard. Hover data includes transaction details, journey status, and price. The plot is customized with a clean layout, axis lines, and a pastel color scheme.
Correlation Matrix Analysis:
Data Cleaning: Missing Railcard values are filled with "others," and Actual_Arrival_Time for cancelled journeys is set to "Train cancelled." Missing Delay_Reason for on-time journeys is set to "No delay."
Feature Engineering:
Scheduled_Duration and Actual_Duration: Calculated in minutes from time differences.
Delay_Minutes: Difference between actual and scheduled durations.
Binary features: Is_Delayed, Is_Cancelled, Is_First_Class, Is_Advance for categorical analysis.
Purchase_Hour: Extracted as an integer hour from Time_Purchase.
Visualization: A correlation matrix heatmap is generated using Seaborn, showing relationships between numerical features like Price, Scheduled_Duration, Delay_Minutes, and binary indicators. The heatmap uses a coolwarm color scheme with annotations for clarity.
Key Insights 🔍
Purchase Patterns: Tickets purchased at different hours show varying travel durations, with potential peaks during morning and evening rush hours.
Railcard Usage: The scatterplot reveals how railcard holders (e.g., Adult, Disabled) differ in their travel durations and purchase times, indicating possible demographic or behavioral differences.
Delays and Cancellations: The correlation matrix highlights relationships between delays, cancellations, and other features. For instance, higher prices may correlate with longer scheduled durations, and delays may be weakly correlated with specific ticket types.
Ticket Type and Class: Advance tickets and First Class tickets may have distinct patterns in pricing and journey outcomes, as seen in the correlation analysis.
Operational Insights: Common delay reasons (e.g., Signal Failure) and the frequency of cancellations provide insights into railway operational challenges.
Visualizations 📈
1.Interactive Scatterplot:
Displays Purchase_Hour vs. Travel_Duration, colored by Railcard.
Hover information includes Transaction_ID, Journey_Status, Price, and more.
Useful for exploring individual transactions and identifying clusters of railcard users.
2.Correlation Matrix Heatmap:
Shows correlations between numerical features like Price, Delay_Minutes, and binary indicators.
Helps identify strong and weak relationships, such as between ticket price and journey duration.

Requirements 🖥️
To run the notebook, ensure you have the following Python libraries installed:
pandas
numpy
matplotlib
seaborn
plotly
You can install them using pip:
pip install pandas numpy matplotlib seaborn plotly
Additionally, you need the dataset file railway.csv in the same directory as the notebook.

How to Run 🚀
1.Clone the Repository:
git clone https://github.com/Gurava-Reddy12345/EDA-On-UK_TRAIN_RIDS.git
cd EDA-On-UK_TRAIN_RIDS
2.Install Dependencies: Ensure the required libraries are installed (see Requirements section).
3.Place the Dataset: Copy the railway.csv file into the project directory.
4.Run the Notebook: Open the EDA_Project.ipynb notebook in Jupyter:
jupyter notebook EDA_Project.ipynb
Execute the cells sequentially to load the data, generate visualizations, and perform the analysis.
5.View Outputs:
The first cell displays the raw dataset.
The second cell generates an interactive scatterplot (viewable in a Jupyter environment or saved as HTML).
The third cell produces a static correlation matrix heatmap.
Files in the Repository 📁
EDA_Project.ipynb: Jupyter Notebook containing the EDA code and visualizations.
railway.csv: Dataset file (not included in the repository; users must provide their own copy).
README.md: This file, providing an overview and instructions.

Future Work 🔮
Advanced Visualizations: Incorporate additional plots, such as box plots for price distributions by ticket type or bar charts for delay reasons.
Statistical Analysis: Perform hypothesis testing to validate observed patterns (e.g., differences in delays by ticket type).
Predictive Modeling: Build machine learning models to predict delays or cancellations based on features like purchase time and ticket type.
Geospatial Analysis: Map departure and arrival stations to analyze geographic patterns in delays or pricing.
Contributing 🤝
Contributions are welcome! If you have suggestions for improving the analysis, visualizations, or code, please:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Commit your changes (git commit -m "Add new feature").
Push to the branch (git push origin feature-branch).
Open a pull request.
License 📜
This project is licensed under the MIT License. See the  file for details.

Contact 📬
For questions or feedback, please contact [lokireddyguravareddy93@gmail.com] or open an issue on GitHub.
