# Data Science Job Simulation Project (British Airways) - FORAGE

## Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Tools and Technologies Used](#tools-and-technologies-used)
- [Task 1: Web Scraping to Gain Company Insights](#task-1-web-scraping-to-gain-company-insights)
- [Task 2: Predicting Customer Buying Behavior](#task-2-predicting-customer-buying-behavior)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Key Metrics Measured](#key-metrics-measured)
- [Visualizations](#visualizations)
- [Results](#results)
- [Limitations](#limitations)
- [Recommendations](#recommendations)
- [References](#references)


## Project Overview

This project aims to gain valuable insights into customer experiences with British Airways by utilizing web scraping techniques to collect reviews from Skytrax. The initial phase involved scraping extensive review data, focusing on sentiments and themes associated with the airline's services. After acquiring the dataset, I performed thorough data cleaning to address inconsistencies and prepare the data for analysis.

Using Python, I applied sentiment analysis and topic modeling to uncover key patterns and insights from the reviews, highlighting both strengths and areas for improvement in customer service. The findings were then visualized through word clouds and charts to present a clear overview of customer sentiment.

In the second phase, I trained a machine learning model to predict customer booking behavior based on various features in the dataset. This involved exploring and preparing the dataset, selecting appropriate algorithms, and conducting cross-validation to evaluate model performance. The outcomes of this analysis were summarized in a concise PowerPoint slide, showcasing actionable insights and strategies for enhancing customer engagement and satisfaction.

## Objectives

The objectives of this project are to analyze customer reviews of British Airways to identify key themes and sentiments, predict customer booking behavior using machine learning, and provide actionable insights that can enhance the airline's services and improve overall customer satisfaction.

## Tools and Technologies Used

The project utilized `Python`, `Beautiful Soup`, and `Requests` for web scraping, `Visual Studio Code` along with `Pandas` and `NumPy` for data analysis, `Matplotlib` and `Seaborn` for visualizations, `Scikit-learn` for training predictive models, and `Microsoft PowerPoint` for presenting findings.

## Task 1: Web Scraping to Gain Company Insights

### 1.1 Data Collection

For the data collection phase, I scraped customer review data from the Skytrax website, specifically targeting British Airways reviews. Using Python, I employed the `Requests` library to retrieve the HTML content of multiple review pages and parsed it with `Beautiful Soup` to extract the text reviews. The code iterated over a specified number of pages, collecting the review text from each page and appending it to a list. This allowed me to gather a comprehensive dataset of reviews, ensuring that all the feedback was stored in a structured format using `Pandas` for further analysis. The data at this stage was still raw, containing unprocessed text that would later undergo cleaning and transformation for sentiment analysis and topic modeling.

The code file can be found [here](https://drive.google.com/file/d/1x9LGWede1TsUIyksEE5TirPgOl4e_f_o/view?usp=sharing)

### 1.2 Data Cleaning and Preparation

During the data cleaning phase, the raw reviews were processed to ensure they were in a usable format for analysis. Key cleaning tasks included removing unnecessary text such as `"✅ Trip Verified"` and `"Not Verified,"` stripping leading characters like `'|'` and `spaces`, and eliminating extra whitespace. Additionally, HTML entities present in the reviews were handled by parsing the content with `Beautiful Soup`. Once the reviews were cleaned, they were saved into a CSV file using `Pandas` for further processing. This step ensured the data was properly structured, making it ready for sentiment analysis and other text-based analyses.

### 1.3 Data Analysis

In the data analysis stage, sentiment analysis and topic modeling were performed to extract meaningful insights from the cleaned reviews.

For sentiment analysis, the `TextBlob` library was used to compute the sentiment polarity of each review, quantifying whether the sentiment was positive, negative, or neutral. The overall sentiment distribution was then analyzed to understand customer feedback trends.

Topic modeling was conducted using `spaCy` for tokenization and lemmatization, followed by the creation of a dictionary and corpus using `Gensim`. An `LDA (Latent Dirichlet Allocation)` model was trained to identify recurring themes within the reviews, revealing key topics discussed by customers. This analysis helped uncover the main concerns and praises of British Airways' services.

### 1.4 Visualizations

In this stage, various visualizations were created to enhance the presentation of insights gained from the analysis. A `word cloud` was generated to highlight the most frequently mentioned words in the reviews, providing a visual representation of recurring themes. The word cloud helps in identifying key topics at a glance.

![output](https://github.com/user-attachments/assets/eb181891-7c79-4563-9f75-3eb7e2999ff5)


Next, topic modeling results from the LDA model were visualized using `pyLDAvis`, which provides an `interactive HTML-based interface` to explore the relationships between topics and words. The visualization file was saved in an HTML format to allow for easy exploration of the topics.

<img width="1470" alt="Screenshot 2024-09-25 at 10 39 57 PM" src="https://github.com/user-attachments/assets/2cdc3e56-9300-4910-99e5-fc1c7ca46196">


Additionally, a `sentiment distribution histogram` was plotted to display the range of sentiment scores across all reviews, showing the overall tone of customer feedback. This helped to pinpoint whether customer reviews were generally positive, negative, or neutral.

![sentiment score distribution](https://github.com/user-attachments/assets/4c887854-32a1-45ad-a7e6-593ae038c8ad)


Finally, a `bar chart` was used to illustrate the frequency of the top 20 most common words across all topics, offering insight into the most relevant terms in customer discussions.

![plot](https://github.com/user-attachments/assets/06fdf27c-46a2-4d66-a010-bbd01e55963a)

### 1.5 Presentation

**Key Topics:**
The analysis revealed that the most frequently discussed topics in the reviews included `"service,"` `"seat,"` `"crew,"` and `"staff."` These terms were highlighted in both the topic modeling and word frequency visualizations, indicating that customer experiences with the airline staff and the quality of seating and service were the dominant themes of discussion.

**Sentiment Analysis:**
Out of **1000 reviews**, **546** were classified as `positive`, **437** as `negative`, and **17** as `neutral`. This demonstrates a clear polarization, with the majority of reviews falling into either positive or negative categories, indicating strong customer opinions about their experiences with British Airways.

The presentation file can be found [here](https://docs.google.com/presentation/d/10xXlqFvIZ-zLSIfnq2XenNParniw63sN/edit?usp=sharing&ouid=103100026359202502665&rtpof=true&sd=true)



## Task 2: Predicting Customer Buying Behavior

### 2.1 Exploratory Data Analysis

The data exploration process began by downloading the dataset using `gdown` from a Google Drive link and loading it into a pandas DataFrame. After successfully loading the dataset, the first few rows were previewed using `head()`, and the structure of the dataset was examined using `info()` to understand the columns, data types, and any missing values.

Next, the flight_day column, which originally contained day names like "Mon" or "Tue," was mapped to numeric values for easier processing. Each day was assigned a corresponding number (e.g., "Mon" = 1, "Tue" = 2). After mapping, the unique values were checked to confirm the correct conversion of the data.

This initial exploration provided an overview of the dataset and allowed us to clean and prepare it for further analysis.

The code file can be found [here](https://drive.google.com/file/d/1JlsMseYqTzTDnNRcB9L-EOar1DJkxhd0/view?usp=sharing)

### 2.2 Data Preparation for Modeling

In this step, we began by loading the dataset using the appropriate encoding (`ISO-8859-1`) to ensure special characters are handled correctly. After loading the data into a pandas DataFrame, we performed initial data inspection using the `head()` function to verify the data structure.

Next, we conducted several visualizations to understand the distributions of key variables:

- **Number of Passengers:** A count plot was generated to explore how frequently different values occur in the `num_passengers` column.

  ![image](https://github.com/user-attachments/assets/d571a195-b1da-429b-a58c-22e4177b69a6)

- **Sales Channel:** Another count plot was created to examine the distribution of booking sources, showing which sales channels customers used.

  ![image](https://github.com/user-attachments/assets/be23fede-260c-4ac9-a5d2-2588e835a568)

- **Trip Type:** We explored whether customers preferred one-way or round-trip journeys by plotting the distribution of `trip_type`.

  ![image](https://github.com/user-attachments/assets/565efabd-06a8-4cc5-850a-2b5e4530fe4e)

- **Extra Baggage Requests:** Finally, we plotted the distribution of customers who requested extra baggage to analyze this preference.

![image](https://github.com/user-attachments/assets/06614bce-17fb-4cbe-ae8f-7e98d43a66c1)


These visualizations helped in understanding the dataset’s characteristics and guided us toward making decisions for the next stages of data cleaning and preparation for modeling.

### 2.3 Correlation Matrix

In this step, we focused on understanding the relationships between numeric features in the dataset. We began by selecting only the numeric columns from the DataFrame using `select_dtypes(include=['float64', 'int64'])`.

To visualize the correlations among these features, we plotted a heatmap using Seaborn’s `heatmap()` function. This graphical representation helps identify how closely related different variables are, with correlation coefficients annotated within the cells for clarity. The `coolwarm` color map was applied to highlight both positive and negative correlations.

![image](https://github.com/user-attachments/assets/d8b99c23-1391-40d7-a735-188e68813930)


The resulting correlation matrix provides insights into which features are strongly related, assisting in feature selection and modeling decisions moving forward.

### 2.4 Machine Learning Model Training

In this phase, we prepared the dataset for training a machine learning model aimed at predicting booking completion. We started by converting categorical variables into dummy variables using `pd.get_dummies()`, which facilitates the modeling process by making these features numerical.

Next, we defined our features (X) and target variable (y) by dropping the `booking_complete` column from the dataset. To evaluate the model's performance effectively, we split the dataset into training and testing sets, with 70% of the data allocated for training and 30% for testing, using `train_test_split()` from scikit-learn.

After preparing the data, we initialized a **Random Forest** Classifier and trained the model using the training data. We then made predictions on the test set and evaluated the model's performance by calculating accuracy and generating a classification report, which provides a detailed breakdown of the model's predictive performance across different classes.


### Model Evaluation

In the Model Evaluation phase, we focused on assessing the performance of the trained machine learning model, specifically the Random Forest Classifier. We began by retrieving the feature importances from the model, which indicates how valuable each feature is in making predictions.

To gain insights into the most influential features, we sorted the feature importances and selected the top 15 most important features. Using Seaborn, we created a bar plot to visualize these importances, allowing us to easily identify which features contribute the most to the model's predictions.

![image](https://github.com/user-attachments/assets/1b0560a6-f452-4de3-a83b-e0fc04ede53f)

The plot enhances interpretability by clearly displaying the importance scores alongside the feature names, providing valuable insights for further analysis and decision-making in the context of booking completion.

### Evaluation and Result Summary
The evaluation of the machine learning model revealed several key insights:

- **Most Important Variable:** The most significant variable in the model was purchase_lead, which represents the time between the purchase date and the departure date. This indicates that understanding how far in advance customers make their bookings plays a crucial role in predicting booking completion.
- **Significant Flight Information:** Variables related to flight details, such as flight time and duration, also showed significant influence on the model's predictions. This suggests that customers' choices and behaviors are closely linked to the specifics of their flights.
- **Booking Origin:** Interestingly, the booking origin of the customer did not appear to be an important factor in the model. This insight could prompt further investigation into customer demographics and preferences that may better capture their behavior.
- **Model Performance:** The model achieved an accuracy of approximately 0.7 (Precision) but only 0.003 (Recall), indicating that while it can correctly identify a majority of booking completions, it struggles to accurately capture the true positives. This suggests that the model requires further improvement to enhance its predictive capabilities.

### Recommendations

To enhance the model's performance, it is advisable to consider adding more customer-centric features. Incorporating additional data points, such as customer demographics, past purchasing behavior, or preferences, could provide a more comprehensive view and potentially improve the model's predictive accuracy.

The presentation file can be found [here](https://docs.google.com/presentation/d/1PhKAJgonZP8kSGeXfbL1yHy-LUZiTFdd/edit#slide=id.p1)

