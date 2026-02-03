# Feature Engineering Projects

This repository contains multiple feature engineering projects completed as part of a data science and machine learning coursework. The projects focus on transforming large-scale transactional data into meaningful features suitable for predictive modeling, with an emphasis on real-world datasets, APIs, and distributed data processing using PySpark.

---

## Complex Feature Challenge

This was a team-based feature engineering project built on a large transactional dataset containing weekly sales data from convenience stores across the United States. The objective was to design and integrate a complex, external-data-driven feature that could improve downstream sales prediction models.

### Feature Description

I developed a socioeconomic feature based on county-level unemployment statistics:

* Retrieved unemployment data at the census tract level using the **U.S. Census Bureau API**.
* Aggregated tract-level data to compute the **median number of unemployed individuals per county**.
* Used a geolocation-to-county lookup API to map each store’s latitude and longitude to its corresponding **county FIPS code**.
* Joined the aggregated unemployment data with the store metadata using the county FIPS code.
* Linked the enriched store-level dataset to the weekly target dataset using **store ID**, ensuring each store-week record included relevant unemployment context.

### Technologies and Tools

* **Python** for data processing and API integration
* **PySpark** for scalable data aggregation and joins on large datasets
* **U.S. Census API** for socioeconomic data retrieval
* **Geolocation / FIPS mapping API** for spatial data enrichment
* **Distributed DataFrames** for efficient feature computation

This feature captures local economic conditions and provides a macroeconomic signal that may influence consumer purchasing behavior.

---

## Easy Feature Challenge

This was a separate team-based project focused on creating a simpler, statistically derived feature using only internal transactional data. The goal was to engineer a feature that was computationally efficient while still providing meaningful insight into sales behavior.

### Feature Description

I created a variability-based feature representing the **weekly standard deviation of quantities sold per product (GTIN) at each store**:

* Grouped transactional data by **store ID**, **GTIN**, and **week**.
* Calculated the standard deviation of quantities sold over time.
* Interpreted higher standard deviation values as indicators of volatile or inconsistent demand.
* Interpreted lower standard deviation values as indicators of stable, predictable sales patterns.

### Technologies and Tools

* **Python**
* **PySpark DataFrames** for grouping and aggregation
* **Statistical feature engineering techniques**

This feature provides a compact summary of demand stability that can be leveraged by forecasting and regression models.

---

## PySpark UDFs Lesson

As part of a team-led class lesson, we taught the use of **User Defined Functions (UDFs)** in PySpark. The lesson focused on both implementation and performance considerations in distributed computing environments.

### Topics Covered

* How PySpark UDFs work and when they are appropriate
* Differences between **Python UDFs**, **Pandas UDFs**, and built-in Spark SQL functions
* Performance and serialization overhead associated with UDFs
* Best practices for avoiding UDFs when native Spark functions are available

### Technologies and Tools

* **PySpark**
* **Spark SQL**
* **Distributed computing concepts**

This lesson emphasized writing efficient, scalable Spark code and understanding the trade-offs involved in extending Spark with custom logic.

---

## Author

Alec Day
