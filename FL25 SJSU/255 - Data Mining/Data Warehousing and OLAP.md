
## What is a Data Warehouse?
~ a library
data comes from many different places:
- online stores
- cash registers
- customer support logs
- marketing campaigns

all of this data is usually messy and scattered
**data warehouse** collects, cleans, organizes, and stores it in a way that makes it **easy to ask questions**

Database vs Data Warehouse
- SCOPE
	- database may handle daily changes, while time horizon of datawarehouse is much larger (ex: annual reports, etc.)
- Volatile vs Nonvolatile
	- Warehouse is WORM
	- database may be changed more often

Attributes of a Data Warehouse

1. Subject oriented --> keeps information about broad parts? (sales, marketing, customers, etc.)
2. Integrated --> data from many sources is made consistent
3. Time-variant --> keeps historical data
4. Non-volatile --> once data is loaded, it doesn't usually change

## Data Cube and OLAP

Cube organizes data in **multidimensional arrays** for fast querying

ex: sales cube with dimensions:
- **product** (laptop, phone, tablet)
- **time** (day, month, quarter, year)
- **location** (city, region, country)

### OLAP Operations
= Online Analytical Processing --> fast dimensional queries

Key Operations:
- Roll-up (Aggregation): Move up hierarchy
	- city --> region --> country
	- sum sales by region
- Drill-down (Disaggregation): Move down hierarchy
- Slice: Fix one dimension
- Dice: Select subcube (multiple dimensions fixed)
	- ex: select cube of **phones** from **Q1 2025**
- Pivot (rotate): re-orient the cube to view from different dimensions

Sample Queries:

**Roll-up**
```
SELECT Location.Region, SUM(Fact_Sales.Amount)
FROM db
JOIN
```

**Drill Down**

```
...
WHERE Product.Name = "Phone" ...
```


Presentation: Diabetes Prediction with KNN + ECT + Random Tree

issues:
- KNN trained on WHOLE dataset
- Will KNN amplify the class imbalance?
	- YES
		- 500 negative cases, 250 positive cases
			- even more skewed to identify the negative cases?
			- majority is non-diabetic, so neighbors are more likely to be non-diabetic --> filling values from non-diabetic to a potentially diabetic patient