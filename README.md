# global_superstore_assignment_SLIIT

# Global Superstore – Sales & Returns Analysis (Power BI)

## 1. Project Overview

This project focuses on analyzing the sales and returns performance of **Global Superstore**, a fictional multinational retail business.

The main objective is to analyze sales, product quantities, profits, customer performance, and product returns to identify meaningful business insights.

Microsoft Power BI is used to transform raw data, build a relational data model, create DAX measures, and develop an interactive business intelligence dashboard.

## 2. Business Objectives

The project aims to:

- Analyze the total number of returned orders.
- Calculate the total quantity of products sold.
- Evaluate overall business profit.
- Identify the top 10 customers based on profit.
- Analyze product quantities across different countries and regions.
- Provide useful business insights through interactive visualizations.

## 3. Dataset Information

**Dataset Name:** Global Superstore 2016  
**Source File:** `global_superstore_2016.xlsx`

The Excel workbook contains three sheets:

| Sheet | Description |
|---|---|
| Orders | Contains sales transactions, customer details, product information, order dates, shipping details, sales, quantity, discounts, and profit. |
| Returns | Contains information about returned orders. |
| People | Contains regional sales manager information. |

## 4. Product Categories and Sub-Categories

The Global Superstore dataset contains three main product categories and 17 sub-categories.

### 4.1 Furniture

Products related to office and home furniture.

- Bookcases
- Chairs
- Furnishings
- Tables

### 4.2 Office Supplies

Products used for office work and daily office activities.

- Appliances
- Art
- Binders
- Envelopes
- Fasteners
- Labels
- Paper
- Storage
- Supplies

### 4.3 Technology

Technology-related products and electronic equipment.

- Accessories
- Copiers
- Machines
- Phones

### Category Summary

| Main Category | Number of Sub-Categories |
|---|---:|
| Furniture | 4 |
| Office Supplies | 9 |
| Technology | 4 |
| **Total** | **17** |

**Note:** These are the product categories available in the provided Global Superstore 2016 dataset. Groceries, clothing, and footwear are not included.

## 5. Main Data Fields

### Orders
- Row ID
- Order ID
- Order Date
- Ship Date
- Ship Mode
- Customer ID
- Customer Name
- Segment
- Country
- City
- State
- Region
- Product ID
- Category
- Sub-Category
- Product Name
- Sales
- Quantity
- Discount
- Profit
- Shipping Cost
- Order Priority

### Returns
- Returned
- Order ID
- Market

### People
- Person
- Region

## 6. Tools and Technologies

- **Microsoft Power BI Desktop** – Report development and data visualization.
- **Power Query Editor** – Data cleaning and transformation.
- **DAX (Data Analysis Expressions)** – Creating calculated measures.
- **Microsoft Excel** – Source data storage.

## 7. Data Preparation and Transformation

The three Excel sheets were imported into Power BI.

The following data preparation steps were performed using Power Query Editor:

1. Imported the Orders, Returns, and People sheets.
2. Promoted the first row to column headers where necessary.
3. Changed `Order Date` and `Ship Date` columns to the Date data type.
4. Changed `Sales`, `Profit`, and `Shipping Cost` columns to Decimal Number.
5. Reviewed the data types of the remaining columns.
6. Checked the data to ensure it was suitable for reporting.

## 8. Data Model and Relationships

Relationships were created between the three tables to build a connected data model.

### Relationships

| Primary Table | Related Table | Relationship Column |
|---|---|---|
| Orders | Returns | Order ID |
| People | Orders | Region |

### Relationship Structure

```text
       People
          |
        Region
          |
          v
        Orders
          |
        Order ID
          |
          v
        Returns
```

These relationships allow data from the three tables to be used together in the report.

## 9. DAX Measures

Three DAX measures were created to calculate the main business metrics.

### 9.1 Total Returns

Counts the distinct number of returned orders.

```dax
Total Returns =
DISTINCTCOUNT(Returns[Order ID])
```

### 9.2 Total Quantity

Calculates the total quantity of products sold.

```dax
Total Quantity =
SUM(Orders[Quantity])
```

### 9.3 Total Profit

Calculates the overall profit generated from sales.

```dax
Total Profit =
SUM(Orders[Profit])
```

## 10. Power BI Dashboard

An interactive Power BI report was developed to present the main business metrics and insights.

### Dashboard Components

**1. Report Title**
- Provides a clear title for the report.

**2. Slicer**
- Allows users to filter the report based on the selected dimension.

**3. Total Returns**
- Displays the total number of returned orders.

**4. Top 10 Customers by Profit**
- Uses a bar chart to identify the ten customers generating the highest profit.
- Helps identify the most profitable customers.

**5. Total Quantity by Country and Region**
- Uses a map visualization to display the distribution of product quantities across countries and regions.
- Helps understand geographical sales distribution.

## 11. Expected Business Insights

The dashboard helps business users:

- Monitor product return performance.
- Understand overall sales profitability.
- Identify high-value customers.
- Compare product quantities across geographical regions.
- Explore business performance using interactive filters.

These insights can support better business planning and decision-making.

 
**Dataset:** Global Superstore 2016  
**Source Format:** Excel (`.xlsx`)  
**Report Format:** Power BI (`.pbix`)
