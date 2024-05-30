# FH MTM Data Project Group 1
**Computergestützte Datenanalyse 2B - Group 1**

## Project Assignment

1. **Select a Dataset**
   - Choose a dataset of your choice with a minimum of 50,000 records and at least 8 attributes/features, one of which must be a time stamp. **[5 points]**

   Dataset open source: https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data/data
   
   This dataset offers a comprehensive analysis of e-commerce sales profitability. It includes detailed information on various sales channels such as Shiprocket and INCREFF, along with financial data related to expenses and profits. The dataset features columns containing SKU codes, design numbers, stock levels, product categories, sizes, and colors. Additionally, it includes MRPs (Maximum Retail Prices) from multiple stores including Ajio, Amazon (regular and FBA), Flipkart, Limeroad, Myntra, and Paytm. Key financial parameters such as the amount paid by customers, rate per piece for each transaction, and transactional details like sale dates, months, categories, fulfillment status, quantity, currency, and gross amounts are also included. This dataset is essential for anyone looking to analyze the profitability of e-commerce sales in the current market landscape.

2. **Data Preprocessing**
    - Handle Missing Values

        Decide on a strategy to handle missing data, such as filling with mean/median or dropping rows/columns with significant missing values.

        - Remove rows with null values in specific columns - ['Courier Status', 'currency', 'Amount', 'ship-city', 'ship-state', 'ship-postal-code', 'ship-country']
        - Remove columns with a large number of null value - ['promotion-ids', 'fulfilled-by', 'Unnamed: 22']
        - Remove columns with only one values - ['Sales Channel ', 'currency', 'ship-country']

    - Data Cleaning

        Convert data types where necessary (e.g., Date column to datetime type).

        - Convert the date an order into date format
        - Change the status of an order into category as there are fixed values
        - Change the Fulfilment of an order into category after is only distribution via Merchant or Amazon possible
        - Change the Fulfilment of an order into category as there is only Standard or Expedited
        - Change the Category of an order into category as there are fixed types of goods
        - Change the Size of an order into category as there are fixed clothing sizes for the goods
        - Change the Courier Status of an order into category as there is only Shipped, Unshipped or Canceled possible
        - Change the ship-postal-code of an order into object as the values are postal codes
        - Change the B2B information into bool as the values are either false or true

    - Feature Engineering
    
        Create new features if necessary, such as extracting month or year from the Date column.

        - Day of the Week and Sepeation of Year & Month
            Extract the day of the week from the Date column to see if there are patterns related to specific days (e.g., higher sales on weekends).
        - Day of the Month
            Extract the day of the month to check for patterns related to specific days (e.g., end-of-month sales spikes).
        - Is Weekend
            Create a binary feature indicating whether a date falls on a weekend in order to see if there are patterns on weekends.
        - Region
            Segment the values in 'ship-state' into six regions of india to recoginze patterns on a higher level
        - Order Size
            Calculate the total order size by multiplying Qty with the Amount (if each row represents a line item, otherwise directly use Amount).
        - Price per Item
            Calculate the price per item if Qty and Amount represent total quantity and total amount.

2. **Data Analysis**
   - Perform analysis on this dataset using the following methods:
     - A classification method. **[5 points]**
        Objective: Predict a categorical outcome, such as the Status of an order (Shipped, Cancelled, etc.).
        Method: Use algorithms like Logistic Regression, Decision Trees, or Random Forest.

     - A clustering method. **[5 points]**
        Objective: Identify distinct groups within the dataset, such as customer segments based on purchase behavior.
        Method: Use K-Means Clustering or Hierarchical Clustering.

     - A time series method. **[5 points]**
        Objective: Analyze trends and patterns over time, such as sales over months.
        Method: Use ARIMA, Seasonal Decomposition, or other time series models.

3. **Visualization**
   - Visualize the results using tailored visualization techniques as described by Nussbaumer Knaflic. **[3 points]**

4. **Summary Report**
   - Write a brief summary (2 - 3 pages) in the style of a scientific paper. This summary should cover your research, methods, and results. **[7 points]**

5. **Submission**
   - Upload the following:
     - Your dataset.
     - Calculations (as Jupyter Notebooks).
     - The summary report (as PDF).