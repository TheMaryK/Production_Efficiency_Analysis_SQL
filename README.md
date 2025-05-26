# Production_Efficiency_Analysis_SQL

## Introduction

I analyzed soda manufacturing productivity across batches to identify key drivers of downtime and operator efficiency. By transforming and normalizing the data, I created SQL queries that revealed which products are prone to delays, which operators perform best, and what factors most affect productivity. These insights help reduce bottlenecks and improve batch planning.

## Problem Statement


## Dataset Description

This project is based on a manufacturing dataset from a soda production company. The dataset is structured into four interrelated tables, capturing details about production output, downtime incidents, products, and downtime causes.

1. Line Productivity
   
- Type: Fact Table
- Description: Contains details for each batch of soda produced on the manufacturing line.
- Key Fields: Date(when the batch was produced), Product, Batch(unique batch identifier), Operator(name of the machine operator), Start Time / End Time(time the batch started and ended 
              production).

2. Products
   
- Type: Dimension Table
- Description: Contains information about each soda product.
- Key Fields: Product, Flavor of the soda (e.g., Cola, Lemon), Size(volume), Min batch time (minimum expected production time for a batch, ideal scenario without downtime).

3. Line Downtime

- Type: Fact Table
- Description: Captures downtime information for each batch, segmented by multiple downtime factors.
- Key Fields: Batch, Downtime Factor(the type of issue that caused delay), Downtime Minutes(time lost due to the downtime factor).

4. Downtime Factors

- Type: Dimension Table
- Description: Provides details on each unique downtime factor, including whether it was due to operator error.
- Key Fields: Factor(unique ID for each downtime cause), Description(explanation of the downtime factor), Operator Error(indicating whether the issue was caused by the operator)

## Data Preparation Summary

Before importing into SQL Server:
- Dates and times were cleaned and reformatted for compatibility.
- Downtime data was reshaped from wide to long format for normalization(pivoted columns into rows).
- Nulls and headers were fixed using Power Query.
- Relationships among tables were identified and prepared for ERD modeling.

## Task

1. Identify common downtime causes.
2. Pinpoint operators inadequacies.
3. Determine time windows with frequent delays.

## Findings

High Downtime	
Low Operator 
Inefficient Products	
Poor Scheduling	
Operator-caused Issues

## Recommendations

1. Target common downtime causes for process improvement
2. Flag products that consistently take longer to produce than expected.
3. Improve scheduling for time windows with frequent delays.
4. Operators needs more training or support.
