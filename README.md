# Customer-Review-Analysis-for-British-Airways
In this project, web scraping techniques were employed using Python libraries such as BeautifulSoup, Requests, and Pandas to collect and analyze customer reviews for British Airways.

1. Web Scraping with BeautifulSoup and Pandas
The process can be broken down into several key steps:

- Importing Libraries: The project began by importing the necessary libraries and modules, including BeautifulSoup for HTML parsing, Requests for making HTTP requests, and Pandas for data manipulation.  
- Defining the Data Source: The data source was specified as the URL containing British Airways reviews. Additionally, a limit of 1000 reviews was set for the analysis. 
- Iterative Scraping: Utilizing a for loop, URLs were created to collect links from paginated data. The HTML content from these pages was retrieved.
- Data Parsing: BeautifulSoup was used to parse the HTML content to extract relevant information, such as review text, ratings, and other details.
- Data Conversion: The extracted data was converted into a Pandas DataFrame to facilitate further analysis.
- Data Saving: Finally, the cleaned data was saved as a CSV file (BA_reviews.csv) for future analysis.
  
2. Data Cleaning and Preprocessing
After scraping the data, the following data cleaning steps were performed:

- Loading Data: The CSV file was read using Pandas, and the DataFrame was named "reviews". The data was then explored using the `.head()`, `.shape`, and `.info` .
- Handling Null Values: Null values in the dataset were identified using the `.isnull().sum()` method.
- Dropping Irrelevant Columns: To streamline the data, irrelevant columns were dropped using the `.drop` method.
- Text Cleaning: The reviews column was cleaned using Python's `re` module to remove specific patterns from each review. The cleaned reviews were stored in a new column called "clean_reviews" using the `.apply` and `lambda` functions with `re.sub`.
- Sentiment Analysis: The sentiment polarity of each cleaned review was calculated using TextBlob, and these sentiment scores were stored in a new 'sentiment' column within the 'reviews' DataFrame to enable sentiment-based analysis.
- Categorization: Reviews were categorized into specific categories based on predefined category keywords (e.g., 'service', 'food', etc.) found in the review text. Reviews were labeled accordingly or as 'other' if no match was found. This categorization allowed for the organization and summarization of reviews by different aspects mentioned in the text.

3. Analyzing the Data
The analysis phase involved the following steps:

- Grouping by Category: Reviews were grouped based on the 'category' column.
- Sentiment Labeling: Sentiment labels (positive or negative) were assigned to reviews based on sentiment scores using a lambda function.
- Counting Sentiment Labels: The counts of each sentiment label were calculated using `value_counts()`.
- Calculating Sentiment Percentage: The percentage of positive and negative sentiment was determined using the `.get` method.
- Counting Reviews by Category: A new 'count' column was created and assigned a value of 1. The DataFrame was then grouped by the 'category' column, and the 'count' column was summed to reveal which category had the highest number of reviews.
- Pivoting Data: Reviews were categorized by sentiment (positive or negative) and category, creating a pivot table that summarized sentiment counts for each category. Missing values were filled with zeros, ensuring complete sentiment counts.
- Converting Pivot Table to DataFrame: The pivot table was converted into a Pandas DataFrame for further analysis and visualization.
- Sorting Data: Categories were sorted by the total number of reviews, with the category having the highest number coming first
- Saving the Result: The final DataFrame was saved as a CSV file (cleaned_reviews_analysis.csv) for reference.
  
This project demonstrates proficiency in web scraping, data preprocessing, sentiment analysis, and data visualization, resulting in valuable insights into sentiment and review categories for British Airways.
