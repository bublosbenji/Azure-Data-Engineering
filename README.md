# Data Ingestion and Transformation from HTTP to Data Lake Storage for Analytics

##### This project orchestrates a concise data pipeline within Azure, starting with data ingestion from GitHub via Azure Data Factory. The raw data is stored in Azure Data Lake Storage Gen2, while Azure Key Vault secures sensitive credentials. Transformation tasks are executed in Azure Databricks, the cleansed data is prepared for Synapse Analytics. This workflow embodies a secure, integrated data journey from source to insight.
### I'm aware that Synapse Analytics alone can accomplish all these steps; my goal was to enhance my understanding of various Azure services!

### Architecture Diagram
![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/c92656aa-a8ab-4ebd-a900-18788b1ed645)

### Step 1: Data Ingestion from GitHub to Azure Data Factory
##### Data source: https://raw.githubusercontent.com/bublosbenji/Exploratory-Data-Analysis/main/merged_sales_data.csv
We establish an Azure Data Factory (ADF) instance in the Azure Portal to facilitate data ingestion from a GitHub repository. We configure a data pipeline within ADF using the Copy Data tool, specifying GitHub as the source and Azure Data Lake Storage Gen2 as the sink, and connect to GitHub via a Git-linked service.

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/f4c9b98f-4187-40ce-9e95-809a7d275d82)

### Step 2: Store Data in Azure Data Lake Storage
Once a Data Lake Storage account is created, with a designated container for data, the ADF pipeline is executed, transferring the data from GitHub into the storage container.

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/c2b74769-1e22-4f83-ad92-846df69ebc1a)

### Step 3: Secure with Azure Key Vault
Next, we set up Azure Key Vault to secure sensitive information, storing critical credentials needed across the workflow.

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/8d019fe4-b7b4-454d-8db6-5e26fb584569)

### Step 4: Data Transformation in Azure Databricks
In Azure Databricks, we prepare a workspace and mount the Data Lake Storage using the secured credentials from Key Vault. A Databricks notebook is then employed to read the raw data, apply necessary transformations, and output the cleaned data back to Data Lake Storage. (Databricks Notebook is uploaded)

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/415850c1-d1ac-441b-bd92-22c967016b52)

### Step 5: Connect Cleaned data from Data Lake Storage to Synapse Analytics
To analyze cleansed data from Azure Data Lake Storage Gen2 using SQL, set up an Azure Synapse Analytics workspace and create a SQL on-demand pool. Then, with the necessary permissions established, utilize Azure Synapse Studio to run SQL queries directly on the data lake files using the on-demand query feature.

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/898f1101-7048-49fe-9872-e0b1be970e92)

### Resource groups

![image](https://github.com/bublosbenji/Azure-Data-Engineering/assets/126903986/d811052e-3a99-4ac5-a9b7-0090ac19dd0d)



