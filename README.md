
# Fragrance Sales Analysis Project

## Project Overview 📊

This project delves into the world of fragrance sales, uncovering key trends, pricing patterns, brand dominance, and consumer preferences. The analysis covers both men’s and women’s fragrances and uses a comprehensive set of Python-based data science tools to clean, explore, and visualize large datasets. The goal is to provide actionable insights for market trends, product positioning, and consumer behavior within the fragrance industry.

---

## Tools and Technologies 🛠️

- **Python**: The primary language for data manipulation and analysis.
- **Pandas**: Used extensively for data cleaning, structuring, and analysis.
- **Matplotlib/Seaborn**: Visualization libraries that help uncover trends and patterns in the data.
- **Jupyter Notebooks**: For documenting the data exploration process and organizing analysis workflows.
- **GitHub**: For version control, collaboration, and sharing code.

---

## Project Breakdown 🗂️

1. **Data Cleaning**: The raw dataset is prepped by addressing missing values, fixing inconsistencies, and ensuring the data is correctly formatted for analysis.
2. **Exploratory Data Analysis (EDA)**: Visualizations and descriptive statistics are used to explore key metrics such as price distributions, popular fragrance notes, and top brands.
3. **Sales Analysis**: Detailed analysis focusing on the performance of different categories, sales trends, and price positioning within the market.

---

## Visual Insights 📊

The following section highlights key insights derived from visualizing the fragrance sales data. Each graph presents a different aspect of the market, such as brand performance, pricing patterns, and consumer preferences. Python’s visualization tools like Matplotlib and Seaborn were used to create these insights.

### 1. Top Brands by Perfume Variations

![Top Brands by Perfume Variations](link-to-image-Brands_that_created_the_most_perfume_variations.png)

Some brands dominate the market with a wide variety of fragrance products. This bar chart showcases the top brands that have produced the most perfume variations, with leading brands such as Avon and Demeter Fragrance offering a diverse array of products to meet different consumer needs.

#### Code:
```python
# Code used to generate the graph
brand_counts = data['brand'].value_counts().head(10)
brand_counts.plot(kind='barh', title='Top Brands by Perfume Variations')
plt.xlabel('Number of Variations')
plt.ylabel('Brands')
plt.show()
---

### 2. Price Distribution by Perfume Type

![Price Distribution by Perfume Type](link-to-image-Price_Distribution_by_Perfume_Type.png)

Understanding how perfumes are priced across different categories is crucial for market positioning. This boxplot shows the price distribution for various types of perfumes such as Eau de Parfum, Eau de Toilette, and Cologne. Eau de Parfum typically commands a higher price range, while Cologne offers a more affordable option.

#### Code:
```python
# Example code for the boxplot of price distribution
sns.boxplot(x='type', y='price', data=data)
plt.title('Price Distribution by Perfume Type')
plt.show()
```

---

### 3. Most Popular Fragrance Notes

![Most Popular Notes](link-to-image-Most_Popular_Notes.png)

Fragrance notes are the backbone of any perfume. This scatter plot highlights the most commonly used fragrance notes across various perfumes. Popular notes such as Musk, Jasmine, and Amber appear prominently, showing their consistent use in a wide range of products.

#### Code:
```python
# Scatter plot of fragrance notes
popular_notes = data['fragrance_notes'].value_counts().head(10)
popular_notes.plot(kind='scatter', x='notes', y='count')
plt.title('Most Popular Fragrance Notes')
plt.show()
```

---

### 4. Total Sales for Different Perfume Categories

![Total sales for different perfume categories](link-to-image-Total_sales_for_different_perfume_categories.png)

This bar chart provides a breakdown of total sales across different perfume categories. Eau de Toilette leads the market in terms of sales volume, followed by Eau de Parfum and Perfume, showcasing their popularity among consumers.

#### Code:
```python
# Bar chart of sales by perfume category
sales_by_category = data.groupby('category')['sales'].sum().sort_values()
sales_by_category.plot(kind='bar', title='Total Sales for Different Perfume Categories')
plt.ylabel('Total Sales')
plt.show()
```

---

### 5. Perfume Launch Trends Over the Last 20 Years

![Trend of Perfumes Over Last 20 Years](link-to-image-Trend_of_Perfumes_Over_Last_20_Years.png)

This line chart shows the trend in the number of perfumes launched over the past two decades. A clear upward trend can be observed, particularly in the last 10 years, indicating growth and increased innovation in the fragrance market.

#### Code:
```python
# Line chart of perfume launches over time
launch_trend = data.groupby('launch_year')['perfume'].count()
launch_trend.plot(kind='line', title='Perfume Launch Trends Over the Last 20 Years')
plt.xlabel('Year')
plt.ylabel('Number of Launches')
plt.show()
```

---

### 6. Top 25 Men’s Perfumes by Number of Sales

![Top 25 Men Perfumes by Number of Sales](link-to-image-Top_25_Men_Perfumes_by_Sales.png)

This bar chart lists the top 25 men’s perfumes based on the number of sales. Brands like Calvin Klein, Versace, and Davidoff dominate the list, showing their strong presence in the men’s fragrance market.

#### Code:
```python
# Bar chart for top 25 men perfumes by sales
top_men_perfumes = data[data['gender'] == 'Men'].nlargest(25, 'sales')
top_men_perfumes.plot(kind='bar', x='perfume_name', y='sales', title='Top 25 Men Perfumes by Number of Sales')
plt.ylabel('Sales')
plt.show()
```

---

## Key Insights 🔍

1. **Top-Selling Brands**: Premium fragrance brands, especially those that utilize popular notes like Musk and Jasmine, dominate the market.
2. **Price Distribution**: Eau de Parfum is generally the most expensive, while Cologne and Eau de Toilette offer more affordable options.
3. **Sales Trends**: Eau de Toilette perfumes lead in sales, with steady growth in new perfume launches over the last 20 years.

---

## How to Run the Project 🚀

1. Clone the repository:
   ```bash
   git clone https://github.com/andrewhryn/fragrance-sales-analysis.git
   ```

2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebooks:
   ```bash
   jupyter notebook
   ```

---

## Future Work 📈

- **Predictive Models**: Implement machine learning models to forecast future sales trends.
- **Sentiment Analysis**: Incorporate customer reviews to understand consumer preferences better.
- **Interactive Dashboards**: Build Tableau or Power BI dashboards for more interactive exploration of the data.

---

## Contact 💬

Feel free to reach out for any inquiries!

- **GitHub**: [andrewhryn](https://github.com/andrewhryn)
- **LinkedIn**: [Andrii Hryn](https://www.linkedin.com/in/andrii-hryn/)
```
