![My Project Thumbnail](https://github.com/Ade-Ogunbiyi/E-Commerce-Sales-and-Customer-Insights/blob/main/E-commerce%20Sales%20and%20Customers%20Insights.png)
## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Introduction](#introduction)
3. [Data Sources](#data-sources)
4. [Schema](#schema)
5. [Tools Used](#tools-used)
6. [SQL Functions Used](#sql-functions-used)
7. [Business Questions](#business-questions)
8. [Analysis Insights](#analysis-insights)
    - [1. Top-Selling Products](#1-top-selling-products)
    - [2. Customer Segmentation](#2-customer-segmentation)
    - [3. Order Frequency and Customer Loyalty](#3-order-frequency-and-customer-loyalty)
    - [4. Product Sales](#4-product-sales)
    - [5. Order Status Analysis](#5-order-status-analysis)
    - [6. Revenue Trends](#6-revenue-trends)
    - [7. Product Ratings](#7-product-ratings)
    - [8. Best Performing Categories](#8-best-performing-categories)
9. [Recommendations](#recommendations)
10. [Conclusion](#conclusion)
11. [Skills Gained and Approach](#skills-gained-and-approach)
12. [Leveraging Data Analysis Skills for Business Impact](#leveraging-data-analysis-skills-for-business-impact)

# E-commerce Sales and Customer Insights

## Executive Summary

This report dives into customer behavior, product performance, and overall satisfaction within a fictional e-commerce platform. Using SQL for data analysis, I was able to pinpoint insights that can boost customer satisfaction and refine sales strategies. The analysis shows that Apple AirPods Pro stands out as the top revenue-generating product, highlighting its high demand and popularity. Additionally, the report found a 25% order cancellation rate, signaling room for improving fulfillment processes. These findings aim to help stakeholders make informed decisions that foster revenue growth and improve customer retention.

## Introduction

In today’s fast-paced e-commerce landscape, understanding customer behavior and product performance is key to staying competitive. This report examines different aspects of sales data on the platform, using SQL to uncover meaningful insights. By identifying trends, challenges, and opportunities, the analysis provides strategic recommendations to boost customer satisfaction and enhance sales. A deeper understanding of customer behavior and product performance informs immediate decisions and supports long-term planning, helping the business stay proactive in meeting customer needs and adapting to market demands.

## Data Sources

The analysis utilized several datasets (tables) generated by ChatGPT for the fictitious e-commerce platform, which included:

- **Categories:** Provides product categories, helping identify high-performing product types and growth opportunities.
- **Customers:** Contains customer demographics, enabling segmentation by spending habits and purchase frequency for targeted marketing.
- **Order Items:** Details individual items in orders, supporting analysis of product popularity and sales performance.
- **Orders:** Includes order status and timestamps, revealing sales trends and fulfillment efficiency, including cancellation rates.
- **Product Reviews:** Offers customer ratings and feedback, highlighting areas for product improvement based on satisfaction levels.
- **Products:** Contains product information, allowing correlation of product features with sales and customer satisfaction.

## Schema

The schema diagram represents the connections among six tables in the e-commerce database: **Customers, Orders, Order_Items, Products, Product_Reviews,** and **Categories.**

![schema](https://github.com/Ade-Ogunbiyi/E-Commerce-Sales-and-Customer-Insights)

1. **Customers and Orders:** Each customer can place multiple orders, establishing a one-to-many relationship between the Customers and Orders tables through the `customer_id`.
2. **Orders and Order_Items:** An order can include one or more items, creating a one-to-many relationship between them via the `order_id`.
3. **Order_Items and Products:** The Order_Items table references the Products table, linking each item in an order to a specific product through the `product_id`.
4. **Products and Categories:** Every product is associated with a single category, resulting in a many-to-one relationship from Products to Categories via the `category_id`.
5. **Product_Reviews and Products:** The Product_Reviews table is connected to the Products table by the `product_id`, indicating a one-to-many relationship where each product can receive multiple reviews.
6. **Product_Reviews and Customers:** Product_Reviews connects to Customers through the `customer_id`, enabling each customer to submit multiple reviews.

This relational framework supports the analysis of customer behavior, order trends, product performance, and review patterns, laying the groundwork for data-driven insights.

## Tools Used

The analysis was conducted using:

**PostgreSQL:** PostgreSQL is a powerful open-source relational database management system that facilitates data querying and manipulation.
- **SQL:** Structured Query Language was employed to extract insights from the datasets.
- **ChatGPT:** Utilized to generate data and assist in the analysis process, providing valuable suggestions and insights.

## SQL Functions Used

The analysis leveraged various SQL functions, including:

- **SELECT:** To retrieve specific data from tables.
- **JOIN:** To combine data from multiple tables based on related columns.
- **GROUP BY:** To aggregate data for analysis.
- **COUNT():** To calculate the number of occurrences.
- **SUM():** To compute total revenue or sales figures.
- **AVG():** To determine average ratings.
- **Common Table Expressions (CTEs):** Used to create temporary result sets that can be referenced within a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement. CTEs help in organizing complex queries, improving readability, and enabling recursive queries.

## Business Questions

The following business questions guided the analysis:

1. Which products have generated the most revenue over the past year?
2. What are the different customer segments based on spending habits?
3. How frequently do customers place orders, and which customers are the most loyal?
4. Which products have generated the highest total sales?
5. How many orders are Shipped, Pending, or Canceled? What Percentage of Orders are Canceled?
6. What are the monthly sales trends over the last year?
7. Which products have the highest and lowest average ratings?
8. Which product categories are performing the best in terms of revenue?

## Analysis Insights

### 1. Top-Selling Products

- **Business Question:** Which products have generated the most revenue over the past year?
- **Insight:** Understanding which products are driving revenue helps prioritize inventory and marketing efforts.
- **Key Findings:**  
  Apple AirPods Pro leads with the highest total revenue of $11,261.22. This highlights its dominance in sales and suggests that it’s the most popular product in terms of revenue in the past year.

### 2. Customer Segmentation

- **Business Question:** What are the different customer segments based on spending habits?
- **Insight:** Segmenting customers allows targeted marketing strategies, enhancing customer retention.
- **Key Findings:**  
  97% of customers fall into the “Medium Spender” category, while only 3% are classified as “High Spenders”. This indicates that most of the customer base contributes to the total revenue with moderate purchases.

### 3. Order Frequency and Customer Loyalty

- **Business Question:** How frequently do customers place orders, and which customers are the most loyal?
- **Insight:** Analyzing order frequency helps identify loyal customers and potential churn risks.
- **Key Findings:**  
  Charles Williams has the highest order count with 103 orders, followed by Diana Richardson with 97 orders, reflecting their regular shopping habits.

### 4. Product Sales

- **Business Question:** Which products have generated the highest total sales?
- **Insight:** Identifying the product's highest overall sales helps to optimize marketing.
- **Key Findings:**  
  Canon EOS R5 Camera leads with total sales of $18,662.50, showing strong market demand.

### 5. Order Status Analysis

- **Business Question:** How many orders are Shipped, Pending, or Canceled? What Percentage of Orders are Canceled?
- **Insight:** Understanding order status helps in managing fulfillment and customer expectations.
- **Key Findings:**  
  33% of orders are pending, 33% are canceled, and 34% are shipped, signaling issues with order processing.

### 6. Revenue Trends

- **Business Question:** What are the monthly sales trends over the last year?
- **Insight:** Understanding revenue trends helps forecast future sales and manage inventory.
- **Key Findings:**  
  Sales nearly doubled from December 2023 to January 2024, likely driven by holiday shopping and seasonal promotions.

### 7. Product Ratings

- **Business Question:** Which products have the highest and lowest average ratings?
- **Insight:** Understanding product ratings helps improve product offerings and customer satisfaction.
- **Key Findings:**  
  Sony WH-1000XM4 Headphones have the highest average rating of 3.11, while several popular products like JBL Flip 5 Speaker have the lowest average rating of 2.90.

### 8. Best Performing Categories

- **Business Question:** Which product categories are performing the best in terms of revenue?
- **Insight:** Identifying top-performing categories helps in strategic decision-making regarding product focus.
- **Key Findings:**  
  Wearables and Appliances are the top revenue contributors, while Photography and Electronics require further strategic improvement.

## Recommendations

- **Enhance Customer Retention:** Implement targeted loyalty programs for “Medium Spenders” to drive higher spending.
- **Optimize Inventory Management:** Prioritize high-revenue products such as Apple AirPods Pro.
- **Improve Order Fulfillment:** Investigate reasons for cancellations and optimize fulfillment processes.
- **Targeted Marketing Campaigns:** Leverage customer segmentation for personalized marketing strategies.

## Conclusion

This analysis provides a comprehensive overview of customer behavior and product performance within the e-commerce platform. By focusing on customer satisfaction and optimizing fulfillment processes, the e-commerce platform can reduce cancellations, enhance loyalty, and increase revenue.

## Skills Gained and Approach

Through this project, I gained hands-on experience with data extraction, manipulation, and SQL-based analysis, improving my ability to derive actionable insights from complex datasets. This project also helped me fine-tune my approach to business questions and decision-making in an e-commerce context.

## Leveraging Data Analysis Skills for Business Impact

I can leverage my SQL expertise to address key business challenges, optimize sales performance, and provide insights that improve customer satisfaction and drive revenue growth for any e-commerce or retail business.

