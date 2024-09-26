# Project Overview

This project aims to gain valuable insights into customer experiences with British Airways by utilizing web scraping techniques to collect reviews from Skytrax. The initial phase involved scraping extensive review data, focusing on sentiments and themes associated with the airline's services. After acquiring the dataset, I performed thorough data cleaning to address inconsistencies and prepare the data for analysis.

Using Python, I applied sentiment analysis and topic modeling to uncover key patterns and insights from the reviews, highlighting both strengths and areas for improvement in customer service. The findings were then visualized through word clouds and charts to present a clear overview of customer sentiment.

In the second phase, I trained a machine learning model to predict customer booking behavior based on various features in the dataset. This involved exploring and preparing the dataset, selecting appropriate algorithms, and conducting cross-validation to evaluate model performance. The outcomes of this analysis were summarized in a concise PowerPoint slide, showcasing actionable insights and strategies for enhancing customer engagement and satisfaction.

## Objectives

The objectives of this project are to analyze customer reviews of British Airways to identify key themes and sentiments, predict customer booking behavior using machine learning, and provide actionable insights that can enhance the airline's services and improve overall customer satisfaction.

## Tools and Technologies Used

The project utilized `Python`, `Beautiful Soup`, and `Requests` for web scraping, `Visual Studio Code` along with `Pandas` and `NumPy` for data analysis, `Matplotlib` and `Seaborn` for visualizations, `Scikit-learn` for training predictive models, and `Microsoft PowerPoint` for presenting findings.

# Task 1: Web Scraping to Gain Company Insights

## 1.1 Data Collection

For the data collection phase, I scraped customer review data from the Skytrax website, specifically targeting British Airways reviews. Using Python, I employed the `Requests` library to retrieve the HTML content of multiple review pages and parsed it with `Beautiful Soup` to extract the text reviews. The code iterated over a specified number of pages, collecting the review text from each page and appending it to a list. This allowed me to gather a comprehensive dataset of reviews, ensuring that all the feedback was stored in a structured format using `Pandas` for further analysis. The data at this stage was still raw, containing unprocessed text that would later undergo cleaning and transformation for sentiment analysis and topic modeling.

The code file can be found [here](https://drive.google.com/file/d/1x9LGWede1TsUIyksEE5TirPgOl4e_f_o/view?usp=sharing)

## 1.2 Data Cleaning and Preparation

During the data cleaning phase, the raw reviews were processed to ensure they were in a usable format for analysis. Key cleaning tasks included removing unnecessary text such as `"✅ Trip Verified"` and `"Not Verified,"` stripping leading characters like `'|'` and `spaces`, and eliminating extra whitespace. Additionally, HTML entities present in the reviews were handled by parsing the content with `Beautiful Soup`. Once the reviews were cleaned, they were saved into a CSV file using `Pandas` for further processing. This step ensured the data was properly structured, making it ready for sentiment analysis and other text-based analyses.


