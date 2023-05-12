# Obtain League of Legends Professional Match Data using Azure Data Factory
### Why this project?
* As a League of Legends fan, it is always fascinating to me to be able to predict which team is going to win.
* Having match data automatically updated, ready to be used would make prediction easier.

### How this project works?
This project utilize Azure Data Factory’s comprehensive set of data integration solutions both outside and inside Azure environment:
* Pulling League of Legends professional tournaments data from Google Drive
* Transforming and loading data to Azure SQL database for query
* Sending email notifications whenever an update has been made inside ADF

### Data Flow Diagram
![image](https://github.com/kazerurouni/is4900-project/assets/117042809/e3789d45-e511-4bf5-886f-d0b96155c550)

### Deploying Resources
First you need to create an Azure Data Factory as well a SQL database. Microsoft Learn's quickstarts can be found in these links: 
* Create Azure Data Factory (follow the "Create a data factory" section only): https://learn.microsoft.com/en-us/azure/data-factory/v1/data-factory-build-your-first-pipeline-using-editor 
* Create SQL Database: https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal
