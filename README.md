

# Fragrance Analysis: Insights into the Perfume Industry with Data 🔬
![Banner](https://github.com/user-attachments/assets/906ab57d-d12b-42a6-9cf3-1329c62a1a4e)


[![GitHub](https://img.shields.io/badge/GitHub-Andrew%20H-FFD700?logo=github&logoColor=white&style=for-the-badge)](https://github.com/andrewhryn)
![Python](https://img.shields.io/badge/Python-3.8%2B-FFD700?logo=python&logoColor=white&style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-1.2.0-FFD700?logo=pandas&logoColor=white&style=for-the-badge)
![Matplotlib](https://img.shields.io/badge/Matplotlib-2023-FFD700?logo=matplotlib&logoColor=black&style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-0.11.2-FFD700?logo=seaborn&logoColor=white&style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-FFD700?logo=jupyter&logoColor=white&style=for-the-badge)

## Project Overview 📊

This project dives into the world of fragrance sales, uncovering key insights such as trends, price distributions, brand dominance, and consumer preferences. The analysis covers both men’s and women’s fragrances, using Python-based data science tools to clean, explore, and visualize large datasets. The goal is to provide actionable insights into market trends, product positioning, and consumer behavior within the fragrance industry.


## Table of Contents 📚


- [Fragrance Analysis: Insights into the Perfume Industry with Data 🔬](#fragrance-analysis-insights-into-the-perfume-industry-with-data-)
- [Project Overview 📊](#project-overview-)
- [Tools and Technologies 🛠️](#tools-and-technologies-)
- [Step-by-Step Code Overview 🧑‍💻](#step-by-step-code-overview-)
  - [1. Data Import and Initial Exploration 📥](#1-data-import-and-initial-exploration-)
  - [2. Data Cleaning: Handling Missing Values and Duplicates 🧹](#2-data-cleaning-handling-missing-values-and-duplicates-)
  - [3. Data Transformation: Aggregating Sales Data 📊](#3-data-transformation-aggregating-sales-data-)
- [Graphical Insights 📊](#graphical-insights-)
  - [1. Most Popular Notes 🌟](#1-most-popular-notes-)
  - [2. Brands that Created the Most Perfume Variations 🏆](#2-brands-that-created-the-most-perfume-variations-)
  - [3. Price Distribution by Perfume Type 💵](#3-price-distribution-by-perfume-type-)
  - [4. Top 25 Men’s Perfumes by Number of Sales 🚹](#4-top-25-mens-perfumes-by-number-of-sales-)
  - [5. Trend of Perfumes Over the Last 20 Years 📈](#5-trend-of-perfumes-over-the-last-20-years-)
  - [6. Total Sales for Different Perfume Categories 📊](#6-total-sales-for-different-perfume-categories-)
- [Key Findings 🔑](#key-findings-)
- [References 📝](#references-)

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

## Graphical Insights 📊

This section showcases the key visualizations created during the analysis of the fragrance sales data. Each graph was generated using Python libraries like Matplotlib and Seaborn, and they provide valuable insights into brand dominance, price distribution, consumer preferences, and market trends.

### 1. Most Popular Notes 🌟

This scatter plot shows the most frequently used fragrance notes in perfumes. Musk, Jasmine, and Amber are among the top fragrance notes, indicating their popularity among perfume brands.

![Most Popular Notes](https://github.com/user-attachments/assets/b1e31e18-e2f8-4b78-835c-02459b0df45e)

```python
# Scatter plot for most popular fragrance notes

sns.scatterplot(data=notes, x='percent_of_all', y='count', palette='magma', hue='percent_of_all')
plt.legend().remove()
plt.xlabel('Percent of all Perfumes')
plt.ylabel('Total of Perfumes')
plt.title('Most Popular Notes')

#Made using ChatGPT
for i in range(len(notes)):
    plt.text(notes['percent_of_all'].iloc[i], 
             notes['count'].iloc[i], 
             notes['notes_str'].iloc[i], 
             fontsize=10, ha='right')
```

![Most Popular Notes (Barplot)](https://github.com/user-attachments/assets/a3cec17d-aae1-49b0-9d08-af6df312e142)

```python

#Building Barplot 

sns.barplot(data=top10_notes, x='count', y='notes_str', palette='magma')
sns.despine()

plt.title('Most Popular Notes')
plt.ylabel('')
plt.xlabel('Total of Perfumes')
```

---

### 2. Brands that Created the Most Perfume Variations 🏆

This bar chart highlights the brands that have created the highest number of perfume variations. Musk leads the way, followed by Jasmine and Amber, showing their strong presence in the fragrance market.

![Brands that created the most perfume variations](https://github.com/user-attachments/assets/06b6b381-2d77-4ce8-b10e-d566fde474dc)

```python
#Building Barplot 

sns.barplot(data=top10_size, x='perfume', y='brand', palette='magma')
sns.despine()

plt.title('Brands that created the most perfume variations')
plt.ylabel('')
plt.xlabel('Total of Perfumes')
```

---

### 3. Price Distribution by Perfume Type 💵

This boxplot shows the price distribution of different types of perfumes. It highlights how Eau de Parfum generally has the highest price range, while Eau de Toilette and Cologne are more affordable.

![Price Distribution by Perfume Type](https://github.com/user-attachments/assets/8457d053-d000-42ec-941d-b5fd2b74a096)

```python
sns.boxplot(data=med_category, y='type_cleaned', x='price', palette='magma')

plt.ylabel('')
plt.title('Price Distribution by Perfume Type')
plt.xlabel('Price (USD)')

```

---

### 4. Top 25 Men’s Perfumes by Number of Sales 🚹

This bar chart shows the top 25 men’s perfumes ranked by the number of sales. Calvin Klein, Versace, and Davidoff are among the most popular brands in men’s fragrance.

![Top 25 Men Perfumes by number of sales](https://github.com/user-attachments/assets/e4883e7e-76c5-4873-bcf6-588e823f4f7e)


```python
sns.barplot(data=top_brand, x='sold', y='brand', palette='magma')
sns.despine()

plt.title('Top 25 Men Perfumes by number of sales')
plt.ylabel('')
plt.xlabel('Number of Sales')

```

---

### 5. Trend of Perfumes Over the Last 20 Years 📈

This line chart shows the upward trend in the number of perfumes launched over the past two decades. The data reveals a steady increase in perfume launches since the early 2000s.

![Trend of Perfumes Over Last 20 Years](https://github.com/user-attachments/assets/eb98974f-1c1f-44e8-9558-9dae4ebb6ce3)

```python

sns.lineplot(data=year, x='launch_year', y='total', color='red')
plt.xticks(rotation=45)
sns.despine()

plt.xlabel('Launch Year')
plt.ylabel('Total of Perfumes')
plt.title('Trend of Pefumes Over Last 20 Years')
```

---

### 6. Total Sales for Different Perfume Categories 📊

This bar chart provides a breakdown of the total sales for different perfume categories. Eau de Toilette leads the market in terms of sales, followed by Eau de Parfum and Cologne.

![Total sales for different perfume categories](https://github.com/user-attachments/assets/09e43495-c415-420f-8f73-40a09d8d7fa0)


```python
sns.barplot(data=top_category, x='type_cleaned', y='sold', palette='magma')
sns.despine()

plt.title('Total sales for different perfume categories')
plt.xlabel('')
plt.ylabel('Number of Sales')

plt.figtext(0.5, -0.2, """Typical fragrance concentrations for each type:
1. Perfume (Parfum): 20% - 40%
2. Eau de Parfum: 15% - 20%
3. Eau de Toilette: 5% - 15%
4. Cologne (Eau de Cologne): 2% - 4%""",
            ha="center", fontsize=10)
```

---


### Key Findings 🔑:
- **Brand Dominance**: Brands like Avon and Demeter Fragrance dominate the market with a wide variety of products.  
- **Price Distribution**: Eau de Parfum commands higher prices, while Eau de Toilette and Cologne offer more affordable options.  
- **Consumer Preferences**: Popular fragrance notes such as Musk, Jasmine, and Amber are consistently in demand.  
- **Market Growth**: The fragrance market has seen significant growth, with a steady increase in new perfume launches over the last 20 years.  
- **Top Performers**: Calvin Klein, Versace, and Davidoff lead the men’s fragrance market in terms of sales.

---

## References 📝

- **Perfume dataset**: Web scraped from [Fragrantica](https://www.fragrantica.com/) and analyzed by [this GitHub repository](https://github.com/rdemarqui/perfume_recommender).  
- **Sales dataset**: Web scraped sales data from eBay (2024), available on [Kaggle](https://www.kaggle.com/code/muhammadaashirirshad/perfume-e-commerce-analysis-2024).

