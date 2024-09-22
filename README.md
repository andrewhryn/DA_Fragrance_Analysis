

# Fragrance Sales and Analysis Project 💼

## Project Overview 📊

This project dives into the world of fragrance sales, uncovering key insights such as trends, price distributions, brand dominance, and consumer preferences. The analysis covers both men’s and women’s fragrances, using Python-based data science tools to clean, explore, and visualize large datasets. The goal is to provide actionable insights into market trends, product positioning, and consumer behavior within the fragrance industry.


## Table of Contents 📚


1. [Project Overview](#project-overview-)  
2. [Tools and Technologies](#tools-and-technologies) 
3. [Step-by-Step Code Overview](#step-by-step-code-overview-)  
   - [1. Data Import and Initial Exploration](#1-data-import-and-initial-exploration-)  
   - [2. Data Cleaning: Handling Missing Values and Duplicates](#2-data-cleaning-handling-missing-values-and-duplicates-)  
   - [3. Data Transformation: Aggregating Sales Data](#3-data-transformation-aggregating-sales-data-)  
   - [4. Price Distribution: Boxplot for Perfume Types](#4-price-distribution-boxplot-for-perfume-types-)  
   - [5. Trend Analysis: Perfume Launch Trends Over Time](#5-trend-analysis-perfume-launch-trends-over-time-)  
   - [6. Identifying Popular Fragrance Notes](#6-identifying-popular-fragrance-notes-)  
   - [7. Visualizing Top-Selling Men’s Perfumes](#7-visualizing-top-selling-mens-perfumes-)  
4. [Graphical Insights](#graphical-insights-)  
5. [Summary](#summary-)  


---

## Project Overview 📊

This project dives into the world of fragrance sales, uncovering key insights such as trends, price distributions, brand dominance, and consumer preferences. The analysis covers both men’s and women’s fragrances, using Python-based data science tools to clean, explore, and visualize large datasets. The goal is to provide actionable insights into market trends, product positioning, and consumer behavior within the fragrance industry.

---

## Tools and Technologies 🛠️

- **Python**: The core language for data manipulation and analysis.  
- **Pandas**: A powerful library for data cleaning, structuring, and analysis.  
- **Matplotlib/Seaborn**: Visualization libraries used to create plots and graphs that reveal trends and patterns.  
- **Jupyter Notebooks**: A platform for documenting the data exploration process and organizing analysis workflows.  
- **GitHub**: For version control, collaboration, and code sharing.  

---

## Step-by-Step Code Overview 🧑‍💻

This section covers the key Python skills demonstrated in the project, focusing on data cleaning, aggregation, and visualization using Pandas, Matplotlib, and Seaborn. The full code can be found in the [GitHub repository](https://github.com/andrewhryn/Perfumes).

### 1. Data Import and Initial Exploration 📥

The first step was to load the fragrance sales dataset and perform an initial exploration to understand its structure. You can view the full code for this part [here](https://github.com/andrewhryn/Perfumes/blob/main/1_Data_cleaning.html).

```python
import pandas as pd

# Load dataset
data = pd.read_csv('fragrance_sales.csv')

# Display first few rows of the dataset
data.head()
```

**Explanation**:  
- **Skills**: Using Pandas to load and explore data.  
- **Purpose**: The `.head()` function provides a quick look at the dataset’s structure, helping to identify key columns and understand the overall data composition.

---

### 2. Data Cleaning: Handling Missing Values and Duplicates 🧹

Next, the dataset was cleaned by removing rows with missing values and eliminating duplicate records to ensure data accuracy. Full code for data cleaning can be accessed [here](https://github.com/andrewhryn/Perfumes/blob/main/1_Data_cleaning.html).

```python
# Remove rows with missing values in key columns
data.dropna(subset=['price', 'brand', 'category'], inplace=True)

# Drop duplicate entries
data.drop_duplicates(inplace=True)

# Ensure that 'price' is treated as a numeric data type
data['price'] = pd.to_numeric(data['price'], errors='coerce')
```

**Explanation**:  
- **Skills**: Cleaning data by handling missing values (`dropna()`) and removing duplicates (`drop_duplicates()`).  
- **Purpose**: These operations improve the quality of the data, ensuring that the analysis is reliable and accurate.

---

### 3. Data Transformation: Aggregating Sales Data 📊

After cleaning, the data was grouped by relevant categories to calculate total sales, providing insights into the most profitable product categories. The full code for this can be found [here](https://github.com/andrewhryn/Perfumes/blob/main/2_Data_Analysis.html).

```python
# Group data by category and calculate total sales
total_sales_by_category = data.groupby('category')['sales'].sum()

# Display the results
total_sales_by_category
```

**Explanation**:  
- **Skills**: Using `groupby()` and `sum()` to aggregate data.  
- **Purpose**: This aggregation helps to summarize sales by category, providing an understanding of which categories perform best.

---

### 4. Price Distribution: Boxplot for Perfume Types 💵

To visualize price variations across different perfume types, a boxplot was created. This helps compare the price range for types like Eau de Parfum and Eau de Toilette. Full code for this analysis is available [here](https://github.com/andrewhryn/Perfumes/blob/main/2_Data_Analysis.html).

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create a boxplot for price distribution by perfume type
sns.boxplot(x='type', y='price', data=data)
plt.title('Price Distribution by Perfume Type')
plt.xlabel('Type')
plt.ylabel('Price (USD)')
plt.show()
```

**Explanation**:  
- **Skills**: Creating visualizations using Seaborn’s boxplot.  
- **Purpose**: This plot provides a visual comparison of price ranges, making it easy to understand the pricing strategies of different perfume types.

---

### 5. Trend Analysis: Perfume Launch Trends Over Time 📈

Next, the dataset was grouped by launch year to analyze trends in perfume launches. A line chart visualizes the number of launches over time, showing market growth. The code for this step can be found [here](https://github.com/andrewhryn/Perfumes/blob/main/3_Sales_Data_cleaning.html).

```python
# Group by launch year to count the number of perfumes launched each year
launch_trend = data.groupby('launch_year')['perfume'].count()

# Plot the trend over time
launch_trend.plot(kind='line', title='Perfume Launch Trends Over Time')
plt.xlabel('Year')
plt.ylabel('Number of Perfumes Launched')
plt.show()
```

**Explanation**:  
- **Skills**: Performing time-series analysis using `groupby()` and line plots.  
- **Purpose**: This analysis highlights the growth of the fragrance market over time, showing an upward trend in new launches.

---

### 6. Identifying Popular Fragrance Notes 🌸

To identify the most commonly used fragrance notes, the data was analyzed to count the occurrences of each note. This bar chart visualizes the top fragrance notes. Full code for this section is available [here](https://github.com/andrewhryn/Perfumes/blob/main/4_Sales_Data_Analysis.html).

```python
# Count the occurrences of each fragrance note
popular_notes = data['fragrance_notes'].value_counts().head(10)

# Plot the most popular fragrance notes
popular_notes.plot(kind='bar', title='Most Popular Fragrance Notes')
plt.xlabel('Fragrance Notes')
plt.ylabel('Frequency')
plt.show()
```

**Explanation**:  
- **Skills**: Using `value_counts()` to rank fragrance notes.  
- **Purpose**: This reveals consumer preferences by identifying the most popular fragrance notes in perfumes.

---

### 7. Visualizing Top-Selling Men’s Perfumes 🚹

Lastly, the top 25 men’s perfumes were visualized in a bar chart, providing insights into the best-performing products in this category. Full code is available [here](https://github.com/andrewhryn/Perfumes/blob/main/4_Sales_Data_Analysis.html).

```python
# Filter the dataset for men's perfumes and find the top 25 by sales
top_men_perfumes = data[data['gender'] == 'Men'].nlargest(25, 'sales')

# Plot the top 25 men's perfumes by sales
top_men_perfumes.plot(kind='bar', x='perfume_name', y='sales', title='Top 25 Men’s Perfumes by Sales')
plt.xlabel('Perfume Name')
plt.ylabel('Sales')
plt.show()
```

**Explanation**:  
- **Skills**: Filtering and visualizing data to rank products.  
- **Purpose**: This chart helps to identify which men’s perfumes are leading in sales, providing insight into market success.

---

## Graphical Insights 📊

This section showcases the key visualizations created during the analysis of the fragrance sales data. Each graph was generated using Python libraries like Matplotlib and Seaborn, and they provide valuable insights into brand dominance, price distribution, consumer preferences, and market trends.

### 1. Most Popular Notes 🌟

This scatter plot shows the most frequently used fragrance notes in perfumes. Musk, Jasmine, and Amber are among the top fragrance notes, indicating their popularity among perfume brands.

![Most Popular Notes](https://github.com/andrewhryn/Perfumes/blob/main/Most%20Popular%20Notes.png)

```python
# Scatter plot for most popular fragrance notes
import matplotlib.pyplot as plt

popular_notes = data['fragrance_notes'].value_counts().head(10)
percent = (popular_notes / popular_notes.sum()) * 100
plt.scatter(percent, popular_notes)
for i, txt in enumerate(popular_notes.index):
    plt.annotate(txt, (percent[i], popular_notes[i]), fontsize=10)
plt.xlabel("Percent of all Perfumes")
plt.ylabel("Total of Perfumes")
plt.title("Most Popular Notes")
plt.show()
```

---

### 2. Brands that Created the Most Perfume Variations 🏆

This bar chart highlights the brands that have created the highest number of perfume variations. Musk leads the way, followed by Jasmine and Amber, showing their strong presence in the fragrance market.

![Brands that created the most perfume variations](https://github.com/andrewhryn/Perfumes/blob/main/Brands%20that%20created%20the%20most%20perfume%20variations.png)

```python
# Bar chart for brands with most perfume variations
brands_with_variations = data['brand'].value_counts().head(10)
brands_with_variations.plot(kind='barh', title='Brands that created the most perfume variations')
plt.xlabel('Total of Perfumes')
plt.ylabel('Brand')
plt.show()
```

---

### 3. Price Distribution by Perfume Type 💵

This boxplot shows the price distribution of different types of perfumes. It highlights how Eau de Parfum generally has the highest price range, while Eau de Toilette and Cologne are more affordable.

![Price Distribution by Perfume Type](https://github.com/andrewhryn/Perfumes/blob/main/Price%20Distribution%20by%20Perfume%20Type.png)

```python
# Boxplot for price distribution by perfume type
import seaborn as sns

sns.boxplot(x='type', y='price', data=data)
plt.title('Price Distribution by Perfume Type')
plt.xlabel('Type')
plt.ylabel('Price (USD)')
plt.show()
```

---

### 4. Top 25 Men’s Perfumes by Number of Sales 🚹

This bar chart shows the top 25 men’s perfumes ranked by the number of sales. Calvin Klein, Versace, and Davidoff are among the most popular brands in men’s fragrance.

![Top 25 Men Perfumes by Number of Sales](https://github.com/andrewhryn/Perfumes/blob/main/Top%2025%20Men%20Perfumes%20by%20number%20of%20sales.png)

```python
# Bar chart for top 25 men's perfumes by sales
top_men_perfumes = data[data['gender'] == 'Men'].nlargest(25, 'sales')
top_men_perfumes.plot(kind='bar', x='perfume_name', y='sales', title='Top 25 Men’s Perfumes by Sales')
plt.xlabel('Perfume Name')
plt.ylabel('Sales')
plt.show()
```

---

### 5. Trend of Perfumes Over the Last 20 Years 📈

This line chart shows the upward trend in the number of perfumes launched over the past two decades. The data reveals a steady increase in perfume launches since the early 2000s.

![Trend of Perfumes Over Last 20 Years](https://github.com/andrewhryn/Perfumes/blob/main/Trend%20of%20Perfumes%20Over%20Last%2020%20Years.png)

```python
# Line chart for perfume launches over time
launch_trend = data.groupby('launch_year')['perfume'].count()
launch_trend.plot(kind='line', title='Trend of Perfumes Over Last 20 Years')
plt.xlabel('Launch Year')
plt.ylabel('Total of Perfumes')
plt.show()
```

---

### 6. Total Sales for Different Perfume Categories 📊

This bar chart provides a breakdown of the total sales for different perfume categories. Eau de Toilette leads the market in terms of sales, followed by Eau de Parfum and Cologne.

![Total Sales for Different Perfume Categories](https://github.com/andrewhryn/Perfumes/blob/main/Total%20sales%20for%20different%20perfume%20categories.png)

```python
# Bar chart for total sales across different perfume categories
total_sales = data.groupby('type')['sales'].sum()
total_sales.plot(kind='bar', title='Total sales for different perfume categories')
plt.xlabel('Perfume Type')
plt.ylabel('Number of Sales')
plt.show()
```

---

## Summary 📝

This project provides a detailed analysis of the fragrance market using Python's data science capabilities. By cleaning, structuring, and visualizing the data, we identified key insights into product pricing, consumer preferences, and brand dominance. The data was sourced from the following:

- **Perfume dataset**: Web scraped from [Fragrantica](https://www.fragrantica.com/) and analyzed by [this GitHub repository](https://github.com/rdemarqui/perfume_recommender).  
- **Sales dataset**: Web scraped sales data from eBay (2024), available on [Kaggle](https://www.kaggle.com/code/muhammadaashirirshad/perfume-e-commerce-analysis-2024).

### Key Findings:
- **Brand Dominance**: Brands like Avon and Demeter Fragrance dominate the market with a wide variety of products.  
- **Price Distribution**: Eau de Parfum commands higher prices, while Eau de Toilette and Cologne offer more affordable options.  
- **Consumer Preferences**: Popular fragrance notes such as Musk, Jasmine, and Amber are consistently in demand.  
- **Market Growth**: The fragrance market has seen significant growth, with a steady increase in new perfume launches over the last 20 years.  
- **Top Performers**: Calvin Klein, Versace, and Davidoff lead the men’s fragrance market in terms of sales.

This project highlights the power of data science in providing insights into market trends, pricing strategies, and consumer behavior.

---

```

This version is fully updated with emojis and hyperlinks, making it clean, engaging, and easy to navigate. You can now copy it into your GitHub README. Let me know if you need any further adjustments!
