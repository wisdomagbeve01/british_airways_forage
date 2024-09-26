# Table of Contents

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


Next, topic modeling results from the LDA model were visualized using `pyLDAvis`, which provides an interactive HTML-based interface to explore the relationships between topics and words. The visualization file was saved in an HTML format to allow for easy exploration of the topics.

<img width="1470" alt="Screenshot 2024-09-25 at 10 39 57 PM" src="https://github.com/user-attachments/assets/2cdc3e56-9300-4910-99e5-fc1c7ca46196">

The interactive HTML-based interface can be found [here](file:///Users/khobyskills/Downloads/VS%20Codes/lda_visualization.html#topic=0&lambda=1&term=)

Additionally, a sentiment distribution histogram was plotted to display the range of sentiment scores across all reviews, showing the overall tone of customer feedback. This helped to pinpoint whether customer reviews were generally positive, negative, or neutral.

Finally, a bar chart was used to illustrate the frequency of the top 20 most common words across all topics, offering insight into the most relevant terms in customer discussions.
