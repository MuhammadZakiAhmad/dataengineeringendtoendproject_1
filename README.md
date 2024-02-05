**End-to-End Azure Data Engineering Project**

Technologies Used:
**Azure Data Lake Gen 2** for data storage.
**Azure Data Factory** for work flow orchestration.
**Azure Databricks** for Data Transformations.
**Azure Synapse Analytics** for providing an interface for BI platforms.
**Azure Key Vault** for storage of secrets and as a best practice.
**Azure Active Directory** for access, authorization and provision purposes.

![image](https://github.com/MuhammadZakiAhmad/dataengineeringendtoendproject_1/assets/110293196/bffde6b6-5b4d-452b-945a-72a6390d4b23)




**Abstract**

This comprehensive project showcases a complete Azure data engineering solution, commencing with a local SQL database and culminating in automated Power BI reporting. The initiative aims to impart knowledge about fundamental data engineering practices, with a particular focus on ETL pipeline techniques. The expertise gained here is especially valuable for small to medium-sized enterprises looking to seamlessly transition their local data to the cloud.

**Introduction**

The project leverages the AdventureWorks dataset provided by Microsoft as its foundation. It commences by establishing an on-premises Microsoft SQL server on a personal computer and subsequently importing the dataset using Microsoft SQL Server Management Studio.

**Project Phases**

**1. Data Ingestion**

The initial phase of the project involves seamless data ingestion from the on-premises SQL server to Azure SQL, facilitated by Azure Data Factory. This process encompasses the following key steps:

    Self-Hosted Integration Runtime: Installation of a Self-Hosted Integration Runtime to bridge the on-premises and Azure environments.
    Connection Establishment: Establishment of a robust connection between Azure Data Factory and the local SQL Server.
    Copy Pipeline Configuration: Configuration of a copy pipeline to proficiently transfer all tables from the local SQL server to Azure Data Lake's designated "bronze" folder.

**2. Data Transformation**

Following successful data ingestion into the "bronze" folder, the project adheres to the medallion data lake architecture (bronze, silver, gold) for effective data transformation. Azure Databricks, harnessing PySpark, plays a pivotal role in these transformative processes. Data, initially stored in the parquet format within the "bronze" folder, undergoes conversion to the delta format as it progresses through the "silver" and "gold" layers. These transformations are meticulously executed through Databricks notebooks, encompassing the following phases:

    Storage Mounting: Mounting of the necessary storage for data access.
    Bronze to Silver Transformation: Transformation of data from the "bronze" to the "silver" layer.
    Silver to Gold Transformation: Further transformation of data from the "silver" to the "gold" layer.

**3. Data Loading**

The loaded data from the "gold" folder is efficiently loaded into the Business Intelligence reporting application, Power BI, utilizing Azure Synapse. This phase involves:

    Azure Storage Linkage: Creation of a seamless linkage from Azure Storage (Gold Folder) to Azure Synapse.
    Stored Procedure Implementation: Implementation of stored procedures to extract table information as a SQL view.
    SQL Database Storage: Storage of views within a server-less SQL Database in Azure Synapse.

**4. Data Reporting**

In the data reporting phase, Power BI establishes a direct connection to the cloud pipeline using DirectQuery, ensuring dynamic updates to the database. A comprehensive Power BI report is meticulously developed to visualize the AdventureWorks dataset, encompassing crucial aspects such as sales, product information, and customer demographics.

**5. Final Pipeline Test**

To validate the end-to-end pipeline's integrity, two new customers are thoughtfully introduced into the local SQL database server. A successful test execution triggers the pipeline update, dynamically reflecting the new data in the Power BI report. This verification process ensures that the total number of customers increases from 849 to 851.

**Improvements:**
1. Using Incremental load for new rows of Data.
2. More powerful and Interactive Power BI report 

This project serves though uses many technologies for a relatively small data engineering task, it really well exhibits a standard data engineering workflow and at the same manifesting Azure Cloud powerful data handling capabilities.
