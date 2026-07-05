# celebal_delta-lake-assignment-7
# Delta Lake Incremental Data Processing (SCD Type 1)

## Purpose
The purpose of this project is to implement a complete end-to-end data engineering pipeline utilizing PySpark and Delta Lake on the Azure Databricks platform. This project illustrates how to manage initial ingestion of master data for the first time to Operation (using Delta tables). It also demonstrates how to clean data and perform atomic `MERGE` operations to process batch changes using a Slowly Changing Dimension (SCD) Type 1 methodology.

## Structure of the Data Processing Workflow
1. **Load Initial Data**: Extracted from the Superstore raw data, create an initial target Delta table containing a list of customer master fields (`Customer_ID`, `Customer_Name`, `Segment`, `Country`, `City`, `State`). 
2. **Data Cleansing**: Data Cleansing referred to applying constraints to deduplicate the primary key column and manage structural NULLS. 
3. **Incremental Batch Processing**: Staged a simulated incremental dataset that contained a mix of existing customer updates (as well as complete new customer records, i.e., inserts). 
4. **SCD Type 1 Merge**: Executed a single atomic Delta Lake `MERGE` transaction to bring all of the new customer modification changes into the master Delta table without creating duplicate key records. 
5. **Audit and Validation**: Validated the accuracy of the data by verifying all of the rows that were upserted and by obtaining transaction history log metadata from the Delta engine.
