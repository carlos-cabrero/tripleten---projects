# Instacart - Ecommerce Store


## Project Overview
 
For this project, you will be working with Instacart data.

Instacart is a grocery delivery platform where customers can place an order and have it delivered, similar to Uber Eats and DoorDash. This particular dataset was publicly released (materials in English) by Instacart in 2017 for a Kaggle competition (materials in English). The actual data can be downloaded directly from the Kaggle competition page.

The dataset provided to you has been modified from the original. We reduced the size of the dataset to make your computations faster and introduced missing values and duplicates. We were careful to preserve the distributions of the original data when making these changes.

Your mission is to clean the data and prepare a report that provides insights into the shopping habits of Instacart customers. After answering each question, write a brief explanation of your findings in a markdown cell of your Jupyter notebook.

This project will require you to create visualizations that communicate your results. Make sure that any chart you create has a title, labeled axes, and a legend if necessary; and include `plt.show()` at the end of each cell with a chart.

## Data Description

**Data Dictionary**  
There are five tables in the dataset, and you will need to use all of them for data preprocessing and exploratory data analysis. Below is a data dictionary that lists the columns of each table and describes the data they contain.

**instacart_orders.csv**: Each row corresponds to an order placed in the Instacart app.
- `'order_id'`: A unique ID number that identifies each order.
- `'user_id'`: A unique ID number that identifies each customer account.
- `'order_number'`: The number of times this customer has placed an order.
- `'order_dow'`: The day of the week the order was placed (0 if Sunday).
- `'order_hour_of_day'`: The hour of the day the order was placed.
- `'days_since_prior_order'`: The number of days since this customer placed their previous order.

**products.csv**: Each row corresponds to a unique product that customers can purchase.
- `'product_id'`: A unique ID number that identifies each product.
- `'product_name'`: The name of the product.
- `'aisle_id'`: A unique ID number that identifies each grocery aisle category.
- `'department_id'`: A unique ID number that identifies each grocery department.

**order_products.csv**: Each row corresponds to an item ordered in an order.
- `'order_id'`: A unique ID number that identifies each order.
- `'product_id'`: A unique ID number that identifies each product.
- `'add_to_cart_order'`: The sequential order in which each item was added to the cart.
- `'reordered'`: 0 if the customer has never ordered this product before, 1 if they have.

**aisles.csv**
- `'aisle_id'`: A unique ID number that identifies each grocery aisle category.
- `'aisle'`: The name of the aisle.

**departments.csv**
- `'department_id'`: A unique ID number that identifies each grocery department.
- `'department'`: The name of the department.


## Instructions for Completing the Project


**Step 1**: Open the data files (/datasets/instacart_orders.csv, /datasets/products.csv, /datasets/aisles.csv, /datasets/departments.csv, and /datasets/order_products.csv) and take a general look at the content of each table.

Note that the files have a non-standard format, so you will need to set certain arguments in `pd.read_csv()` to read the data correctly. Look at the CSV files to get an idea of what those arguments should be.

Keep in mind that `order_products.csv` contains many rows of data. When a DataFrame has too many rows, `info()` will not print the non-null counts by default. If you want to print the non-null counts, include `show_counts=True` when calling `info()`.

**Step 2**: Preprocess the data as follows:

- Verify and correct data types (e.g., ensure that the ID columns are integers).
- Identify and fill in missing values.
- Identify and remove duplicate values.
- Make sure to explain what types of missing and duplicate values you found, how you filled in or removed them, and why you used those methods. Why do you think these missing and duplicate values may have been present in the dataset?

**Step 3**: Once the data is processed and ready, perform the following analysis:

**[A]** (must complete all to pass)
- Verify that the values in the 'order_hour_of_day' and 'order_dow' columns of the orders table are reasonable (i.e., 'order_hour_of_day' ranges from 0 to 23, and 'order_dow' ranges from 0 to 6).
- Create a chart showing the number of people placing orders depending on the time of day.
- Create a chart showing which day of the week people do their shopping.
- Create a chart showing the time people wait until placing their next order, and comment on the minimum and maximum values.

**[B]** (must complete all to pass)
- Are there any differences in the distributions of 'order_hour_of_day' on Wednesdays and Saturdays? Plot histograms of both days on the same chart and describe the differences you observe.
- Plot the distribution of the number of orders customers place (e.g., how many customers placed only one order, how many placed only two, only three, etc.).
- What are the top 20 most frequently ordered products (show their ID and name)?

**[C]** (must complete all to pass)
- How many items do people typically buy in an order? What does the distribution look like?
- What are the top 20 most frequently reordered items (show their names and product IDs)?
- For each product, what proportion of its orders are reorders (create a table with columns for product ID, product name, and the proportion of times it was reordered)?
- What is the proportion of ordered products that are reordered for each customer?
- What are the top 20 items that people add to their carts first (show product IDs, product names, and the number of times they were the first item added to the cart)?


## Libraries
- Pandas version: 1.4.4
- Matplotlib version: 3.7.1
