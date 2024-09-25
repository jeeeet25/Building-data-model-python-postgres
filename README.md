# Wealth Account Database Project

## Project Overview
This project involves creating a PostgreSQL database to store and manage wealth account data, with information sourced from three CSV files. The goal is to create three tables for country, account data, and series information, then insert cleaned data from CSV files into the respective tables.

### Datasets
- **Wealth-AccountData.csv**: Contains wealth account data for various countries over several years.
- **Wealth-AccountsCountry.csv**: Contains metadata about countries, including names, codes, and currency units.
- **Wealth-AccountSeries.csv**: Contains information on different series and indicators related to wealth accounts.

## Prerequisites
- Python 3.x
- PostgreSQL
- Required Libraries: `pandas`, `psycopg2`

## Project Files
1. **Wealth-AccountData.csv**: Contains country-level wealth data.
2. **Wealth-AccountsCountry.csv**: Metadata for countries.
3. **Wealth-AccountSeries.csv**: Information on series and indicators.
4. **wealthMain**: Script to clean data, create PostgreSQL tables, and insert data.

## Steps
1. **Data Loading and Cleaning**
   - Read the CSV files using `pandas` and clean the data by selecting relevant columns:
     - `Wealth-AccountData.csv`: Select country name, code, series name, and data for years 1995, 2000, 2005, 2010, and 2014.
     - `Wealth-AccountsCountry.csv`: Select code, table name, short name, long name, and currency unit.
     - `Wealth-AccountSeries.csv`: Select code, topic, indicator name, and long definition.
   
2. **PostgreSQL Database Setup**
   - Connect to PostgreSQL and create a new database named `wealth`.
   - Create three tables:
     1. **accountscountry**: Stores country-level metadata.
     2. **accountsdata**: Stores wealth account data for each country over several years.
     3. **accountseries**: Stores series and indicator information.

3. **Data Insertion**
   - Insert cleaned data from the three CSV files into the respective tables.

## Running the Script
1. Ensure PostgreSQL is running locally.
2. Modify the connection settings in the script if needed:
   ```python
   conn = psycopg2.connect("host=127.0.0.1 dbname=wealth user=postgres password=root")
   ```
3. Run the script to load the data and insert it into the database.

## Sample Queries
After successfully inserting the data, you can query the tables using PostgreSQL to explore the data.

Example:
```sql
SELECT * FROM accountsdata WHERE year_2014 > 1000;
```

## Future Enhancements
- Add additional error handling for database connections.
- Expand the dataset to include more years.
- Create indexes to improve query performance.

---

This README provides a basic overview of the project and instructions on how to load and manage wealth account data using PostgreSQL.
